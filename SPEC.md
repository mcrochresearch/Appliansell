# Appliansell — Appliance POS & Web Shop Specification

## 1. Overview

Appliansell is a dual-channel retail platform for appliance retailers. It combines a **Point-of-Sale (POS)** system for in-store sales staff with a **customer-facing web shop**, backed by a shared inventory and order management layer.

---

## 2. Goals

- Unify in-store and online sales under a single inventory source of truth.
- Enable sales staff to process transactions quickly and accurately.
- Let customers browse, compare, and purchase appliances online.
- Provide managers with real-time sales and inventory reporting.

---

## 3. Personas

| Persona | Description |
|---|---|
| **Sales Associate** | In-store staff who process walk-in sales via the POS terminal. |
| **Store Manager** | Oversees staff, approves discounts/returns, views reports. |
| **Online Customer** | Browses and purchases via the web shop; may pick up in-store or request delivery. |
| **Admin** | Manages product catalog, pricing, user accounts, and system configuration. |

---

## 4. System Architecture

```
┌─────────────────────┐     ┌──────────────────────┐
│     POS Terminal     │     │      Web Shop (SPA)   │
│  (React + Electron)  │     │       (Next.js)        │
└────────┬────────────┘     └──────────┬─────────────┘
         │                             │
         └──────────────┬──────────────┘
                        │ REST / GraphQL API
               ┌────────▼────────────┐
               │    Backend Service   │
               │  (Node.js / Express) │
               └────────┬────────────┘
                        │
          ┌─────────────┼──────────────┐
          │             │              │
   ┌──────▼──────┐ ┌────▼────┐ ┌──────▼──────┐
   │  PostgreSQL  │ │  Redis  │ │   Storage   │
   │  (primary)   │ │ (cache/ │ │ (S3/images) │
   │              │ │ session)│ │             │
   └─────────────┘ └─────────┘ └─────────────┘
```

---

## 5. POS System

### 5.1 Product Lookup

- Search by SKU, barcode scan, or product name.
- Display product name, category, price, stock level, and warranty options.
- Show alternate compatible models when the searched item is out of stock.

### 5.2 Cart / Transaction

- Add, remove, and adjust quantity of line items.
- Apply item-level or cart-level discounts (requires manager PIN for discounts > 15%).
- Display running subtotal, tax breakdown, and total.
- Support split payments (cash + card, multiple cards).
- Hold and recall transactions.

### 5.3 Payment Processing

| Method | Notes |
|---|---|
| Cash | Automatic change calculation displayed. |
| Credit / Debit card | Integrated card reader via Stripe Terminal SDK. |
| Store credit | Validated against customer account balance. |
| Financing | Third-party financing (e.g., Synchrony) via iframe handoff. |

### 5.4 Customer Management

- Look up customer by phone number, email, or loyalty card scan.
- Create a new customer profile inline during checkout.
- Attach purchase to customer for warranty tracking and return eligibility.
- View customer purchase history and store credit balance.

### 5.5 Receipts

- Print thermal receipt via CUPS-connected printer.
- Email digital receipt (PDF) on request.
- Receipt includes: itemized list, taxes, payment method, return policy, and warranty details.

### 5.6 Returns & Exchanges

- Look up original transaction by receipt number or customer account.
- Validate return window per product category (default 30 days; appliances up to 90 days with manager approval).
- Issue refund to original payment method or as store credit.
- Log restocking notes and reason code.

### 5.7 Inventory Adjustments

- Receive new stock: scan or enter items, update quantities.
- Mark items as damaged/floor model with price override.
- Low-stock alerts shown in POS dashboard (configurable threshold per SKU).

### 5.8 End-of-Day

- Z-report: total sales by payment method, number of transactions, refunds, net revenue.
- Cash drawer reconciliation with variance flagging.
- Automatic report emailed to store manager.

### 5.9 Offline Mode

- POS caches product catalog and recent customer data locally (IndexedDB / SQLite).
- Accepts cash transactions offline; queues card transactions for retry on reconnection.
- Displays banner warning when operating offline.

---

## 6. Web Shop

### 6.1 Homepage

- Hero banner (manually managed via Admin CMS).
- Featured product carousels: "New Arrivals", "On Sale", "Top Rated".
- Category shortcuts: Refrigerators, Washers & Dryers, Dishwashers, Ovens & Ranges, Microwaves, Small Appliances.
- Newsletter signup.

### 6.2 Product Catalog

- Category and sub-category browsing with breadcrumb navigation.
- Filter sidebar:
  - Brand
  - Price range (slider)
  - Energy Star rating
  - Color / finish
  - Capacity / size
  - Availability (in stock / available to order)
- Sort: Relevance, Price (asc/desc), Rating, Newest.
- Grid and list view toggle.
- Pagination (default 24 products per page) with infinite scroll option.

### 6.3 Product Detail Page

- High-resolution image gallery (main + thumbnails, zoom on hover).
- Product name, brand, model number, SKU.
- Current price, strike-through original price when on sale.
- Star rating and review count (links to review section).
- Key specs displayed as a highlights list.
- Full specification table (expandable).
- Warranty information.
- Add to Cart button with quantity selector.
- "Add to Wish List" (requires login).
- Delivery options:
  - Home delivery (estimated date by ZIP code)
  - In-store pickup (show store stock levels)
- Frequently bought together / accessory upsells.
- Customer reviews section (write review requires verified purchase).

### 6.4 Shopping Cart

- Persistent cart (saved to account if logged in, cookie if guest).
- Display: item thumbnail, name, quantity stepper, unit price, line total.
- Remove item and save-for-later options.
- Promo code field.
- Order summary: subtotal, estimated shipping, estimated tax, total.
- Proceed to checkout CTA.

### 6.5 Checkout

Multi-step, with progress indicator:

1. **Contact** — Email, phone. Guest or account login prompt.
2. **Delivery** — Address entry with USPS validation; delivery vs. pickup selection.
3. **Delivery Date** — Time-slot picker for scheduled delivery (if applicable).
4. **Payment** — Stripe Elements (card), Apple Pay / Google Pay, store credit.
5. **Review** — Full order summary before placing.
6. **Confirmation** — Order number, estimated delivery, email confirmation sent.

### 6.6 User Accounts

- Register / login (email + password, OAuth via Google).
- Dashboard sections:
  - Order history with status and tracking links.
  - Wish list.
  - Address book.
  - Saved payment methods.
  - Store credit balance.
  - Loyalty points summary.
- Password reset via email link.
- Account deletion (GDPR / CCPA compliant soft-delete).

### 6.7 Search

- Global search bar with autocomplete suggestions (product names, categories, brands).
- Results page inherits catalog filter/sort UI.
- Zero-results page suggests similar categories and top sellers.

### 6.8 Delivery & Fulfillment

| Fulfillment Type | Description |
|---|---|
| Standard home delivery | Carrier-based shipping; tracking number provided. |
| White-glove delivery | Scheduled time slot, in-home delivery and setup. |
| In-store pickup | Customer notified by email when order is ready. |
| Curbside pickup | Customer checks in via web; staff brings order out. |

### 6.9 Promotions & Discounts

- Percentage or fixed-amount promo codes.
- Automatic cart-level promotions (e.g., "10% off when you buy a washer + dryer").
- Seasonal sale tags on product cards.
- Loyalty points earned per dollar spent; redeemable as store credit.

---

## 7. Shared Services

### 7.1 Product Catalog Service

- Central source for all product data consumed by both POS and web shop.
- CRUD via Admin dashboard.
- Supports bulk import via CSV.
- Product attributes: name, brand, model number, SKU, category, description, specs (key-value pairs), images, price, sale price, weight, dimensions, energy rating, warranty terms, tags.

### 7.2 Inventory Service

- Real-time stock counts per location (store + warehouse).
- Reservation system: stock reserved on cart add (15-minute TTL), committed on order completion.
- Webhook events: `stock.low`, `stock.depleted`, `stock.replenished`.

### 7.3 Order Management Service

- Unified order model for POS and web shop orders.
- Order states: `pending` → `confirmed` → `processing` → `ready` / `shipped` → `delivered` → `completed`.
- Cancellation and partial refund support.
- Order timeline/audit log.

### 7.4 Customer Service

- Single customer record across channels.
- Loyalty points ledger.
- Communication preferences (email, SMS).

### 7.5 Notification Service

- Email: order confirmation, shipping updates, return confirmation, low-stock alert (admin).
- SMS (optional, opt-in): order ready for pickup, delivery window reminder.
- Push notifications: web shop PWA (opt-in).

---

## 8. Admin Dashboard

- **Product Management**: Create/edit/archive products, manage categories and brands, bulk pricing updates.
- **Inventory**: Adjust stock counts, transfer stock between locations, view reorder suggestions.
- **Orders**: View all orders, update status, initiate refunds.
- **Customers**: Search, view history, manage store credit, merge duplicate accounts.
- **Promotions**: Create/schedule/expire promo codes and automatic promotions.
- **Reports**:
  - Sales by date range, category, or product.
  - Inventory turnover.
  - Top customers.
  - Refund and return rates.
  - Web shop conversion funnel.
- **User Management**: Invite staff, assign roles (Admin, Manager, Sales Associate, Warehouse).
- **CMS**: Edit homepage banners, featured collections, static pages (FAQ, Return Policy, Contact).
- **Configuration**: Tax rates by region, store locations, delivery zones, receipt templates.

---

## 9. Roles & Permissions

| Permission | Admin | Manager | Sales Associate | Warehouse |
|---|---|---|---|---|
| View products | ✓ | ✓ | ✓ | ✓ |
| Edit products | ✓ | ✓ | | |
| Process sales | ✓ | ✓ | ✓ | |
| Apply discount > 15% | ✓ | ✓ | | |
| Process returns | ✓ | ✓ | ✓ (≤30 days) | |
| Approve returns > 30 days | ✓ | ✓ | | |
| View all reports | ✓ | ✓ | | |
| Adjust inventory | ✓ | ✓ | | ✓ |
| Manage users | ✓ | | | |
| Edit CMS | ✓ | ✓ | | |

---

## 10. Non-Functional Requirements

| Area | Requirement |
|---|---|
| **Performance** | Web shop LCP < 2.5 s on 4G. POS transaction completion < 3 s. API p95 response < 300 ms. |
| **Availability** | 99.9% uptime for web shop and API. POS offline mode ensures no sales lost during outages. |
| **Scalability** | Horizontal scaling for API and web shop. DB read replicas for reporting queries. |
| **Security** | PCI-DSS compliance for payment flows. OWASP Top 10 mitigations. Role-based access control. Audit log for all sensitive actions. |
| **Accessibility** | WCAG 2.1 AA for web shop. Keyboard-navigable POS UI. |
| **Localization** | USD pricing; tax calculation per US state. i18n-ready architecture for future expansion. |
| **Data Privacy** | GDPR / CCPA: consent collection, data export, account deletion. |

---

## 11. Tech Stack (Proposed)

| Layer | Technology |
|---|---|
| POS frontend | React + Electron (desktop app) |
| Web shop frontend | Next.js 14 (App Router, SSR + ISR) |
| Styling | Tailwind CSS |
| Backend API | Node.js + Express (REST) + Apollo (GraphQL for web shop) |
| Database | PostgreSQL (primary), Redis (cache + sessions) |
| File storage | AWS S3 (product images) + CloudFront CDN |
| Payments | Stripe (online) + Stripe Terminal (POS) |
| Email | SendGrid |
| Search | Elasticsearch (product search + autocomplete) |
| Hosting | AWS ECS (Fargate) + RDS + ElastiCache |
| CI/CD | GitHub Actions |
| Monitoring | Datadog (APM + logs) |

---

## 12. Data Models (Core Entities)

### Product
```
id, sku, name, brand_id, category_id, description, model_number,
price, sale_price, cost, weight_lbs, dimensions_in (json),
energy_star_rating, color, warranty_months, is_active,
created_at, updated_at
```

### InventoryItem
```
id, product_id, location_id, quantity_on_hand, quantity_reserved,
reorder_threshold, created_at, updated_at
```

### Order
```
id, order_number, channel (pos|web), customer_id, location_id,
status, subtotal, discount_amount, tax_amount, shipping_amount, total,
fulfillment_type, notes, created_at, updated_at
```

### OrderLine
```
id, order_id, product_id, quantity, unit_price, discount_amount, line_total
```

### Customer
```
id, first_name, last_name, email, phone, loyalty_points,
store_credit_cents, created_at, updated_at
```

### Payment
```
id, order_id, method (cash|card|store_credit|financing),
amount_cents, status, stripe_payment_intent_id, created_at
```

---

## 13. API Endpoints (Key)

### Products
```
GET    /api/products               List / search products
GET    /api/products/:id           Get product detail
POST   /api/products               Create product (Admin)
PUT    /api/products/:id           Update product (Admin)
DELETE /api/products/:id           Archive product (Admin)
```

### Orders
```
GET    /api/orders                 List orders (filtered by role)
GET    /api/orders/:id             Get order detail
POST   /api/orders                 Create order
PUT    /api/orders/:id/status      Update order status
POST   /api/orders/:id/refund      Issue refund
```

### Customers
```
GET    /api/customers              Search customers
GET    /api/customers/:id          Get customer profile
POST   /api/customers              Create customer
PUT    /api/customers/:id          Update customer
```

### Inventory
```
GET    /api/inventory/:productId   Get stock levels by location
POST   /api/inventory/adjust       Adjust stock count
POST   /api/inventory/transfer     Transfer stock between locations
```

### Cart (Web Shop)
```
GET    /api/cart                   Get current cart
POST   /api/cart/items             Add item
PUT    /api/cart/items/:id         Update quantity
DELETE /api/cart/items/:id         Remove item
POST   /api/cart/promo             Apply promo code
```

---

## 14. Milestones

| Phase | Scope | Target |
|---|---|---|
| **Phase 1 — Foundation** | Product catalog, inventory service, admin CRUD, basic POS (cash only) | Week 6 |
| **Phase 2 — POS Complete** | Card payments (Stripe Terminal), customer management, returns, receipts, offline mode | Week 12 |
| **Phase 3 — Web Shop MVP** | Homepage, catalog, PDP, cart, checkout (card), order confirmation, user accounts | Week 18 |
| **Phase 4 — Enhancements** | Loyalty program, promotions engine, white-glove delivery scheduling, search (Elasticsearch), reviews | Week 24 |
| **Phase 5 — Operations** | Admin reporting dashboard, SMS notifications, performance tuning, accessibility audit | Week 28 |

---

## 15. Open Questions

1. Will the POS run on dedicated hardware (e.g., touch-screen kiosks) or standard laptops/tablets?
2. Which financing partner(s) should be integrated at launch?
3. Is multi-store support required in Phase 1 or can it be deferred?
4. Should the web shop support international shipping, or US-only at launch?
5. Is there an existing ERP or accounting system (e.g., QuickBooks) that requires integration?
6. What is the preferred loyalty program structure — points-per-dollar, tiered membership, or both?
