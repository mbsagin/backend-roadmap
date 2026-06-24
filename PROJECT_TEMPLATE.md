# Project Specification Template

Use this template to scope, plan, and execute projects throughout the roadmap. A well-scoped project teaches more than an open-ended one. Constraint is productive.

---

## Why project specs matter

Engineers who build vague projects ("I'll make a todo app") learn less than engineers who build tightly scoped ones. Specificity forces you to confront design decisions, not defer them. This template replicates how real projects are scoped in production teams.

Fill out every field before writing a line of code. If you can't fill a field, the project scope is unclear. Clarify it first.

---

## Template

```
# Project: [Name]

## Roadmap Section
[Which section(s) of the roadmap this project covers]

## Objective
[One paragraph. What does this project exist to do? What problem does it solve?]

## Prerequisites
[What must you already understand before starting this?
List the specific concepts required, not just section names.]

## Functional Requirements
[What must the system do? Be specific.
Use "The system must..." or "Users can..."]

1.
2.
3.
...

## Non-Functional Requirements
[Performance, security, reliability, scalability constraints]

- Latency:
- Availability:
- Security:
- Scale:

## Out of Scope
[What are you explicitly NOT building? This prevents scope creep.]

- Not implementing:
- Not implementing:

## Data Model
[List tables/collections and their key fields.
Draw relationships if it helps.]

## API Contracts (if applicable)
[List endpoints with method, path, and brief description.
Define request/response shapes for complex ones.]

## Success Criteria
[How do you know when this project is done?
Each criterion should be objectively verifiable — not "it works" but "it returns HTTP 200 for valid input and 422 for missing required fields".]

- [ ]
- [ ]
- [ ]

## Difficulty Level
[ ] Beginner — applies concepts from one section directly
[ ] Intermediate — combines multiple sections, requires design decisions
[ ] Advanced — requires trade-off analysis, non-obvious solutions

## Estimated Time
[Be honest. Underestimating is common. Double your first estimate.]

## Portfolio / Interview Value
[How would you explain this project in an interview?
What interesting technical decisions did it force you to make?]
```

---

## Example: E-commerce Data Layer

This is the Databases project from the roadmap. Completed example using the template above.

---

# Project: E-commerce Data Layer

## Roadmap Section
Relational Databases & SQL

## Objective
Design and implement the relational database foundation for a simplified e-commerce platform. The goal is not to build a UI or an API — only the data layer. This forces full focus on schema design, normalization, transaction semantics, and query performance.

## Prerequisites
- Normalization (1NF, 2NF, 3NF) and when to violate it deliberately
- SQL: SELECT, JOIN, GROUP BY, subqueries, CTEs
- Indexes: when they help, when they hurt, how to read a query plan
- ACID transactions and isolation levels
- Constraints: PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK, NOT NULL

## Functional Requirements

1. The system must store users with email, hashed password, and registration timestamp
2. The system must store products with name, description, price, stock quantity, and category
3. The system must store orders with a state machine: `pending` → `paid` → `shipped` → `delivered` (and `cancelled` from `pending` or `paid`)
4. The system must store order items linking orders to products with quantity and unit price at time of purchase
5. The system must support payment records referencing an order (one payment per order)
6. The system must prevent overselling: placing an order must decrement stock atomically
7. The system must support soft deletes for products (mark as inactive, not delete rows)

## Non-Functional Requirements

- **Correctness:** All order state transitions must be enforced at the database level (CHECK constraint or application-level enforcement with tests)
- **Consistency:** Inventory decrement and order creation must be atomic (single transaction)
- **Performance:** Product search by name and category must return results in under 100ms on a 100k-row products table (index accordingly)
- **Auditability:** Order status changes should record a timestamp for each transition

## Out of Scope

- Not implementing: API layer, authentication, frontend
- Not implementing: Payment gateway integration (mock a payment record only)
- Not implementing: Shipping carrier integration
- Not implementing: Product reviews or ratings

## Data Model

```
users
  id            UUID        PRIMARY KEY
  email         TEXT        NOT NULL UNIQUE
  password_hash TEXT        NOT NULL
  created_at    TIMESTAMPTZ NOT NULL DEFAULT now()

categories
  id    SERIAL      PRIMARY KEY
  name  TEXT        NOT NULL UNIQUE

products
  id          UUID        PRIMARY KEY
  name        TEXT        NOT NULL
  description TEXT
  price       NUMERIC(10,2) NOT NULL CHECK (price >= 0)
  stock_qty   INT         NOT NULL DEFAULT 0 CHECK (stock_qty >= 0)
  category_id INT         REFERENCES categories(id)
  is_active   BOOLEAN     NOT NULL DEFAULT true
  created_at  TIMESTAMPTZ NOT NULL DEFAULT now()

orders
  id          UUID        PRIMARY KEY
  user_id     UUID        NOT NULL REFERENCES users(id)
  status      TEXT        NOT NULL DEFAULT 'pending'
                          CHECK (status IN ('pending','paid','shipped','delivered','cancelled'))
  created_at  TIMESTAMPTZ NOT NULL DEFAULT now()
  updated_at  TIMESTAMPTZ NOT NULL DEFAULT now()

order_items
  id           UUID          PRIMARY KEY
  order_id     UUID          NOT NULL REFERENCES orders(id)
  product_id   UUID          NOT NULL REFERENCES products(id)
  quantity     INT           NOT NULL CHECK (quantity > 0)
  unit_price   NUMERIC(10,2) NOT NULL   -- snapshot of price at order time

payments
  id           UUID          PRIMARY KEY
  order_id     UUID          NOT NULL UNIQUE REFERENCES orders(id)
  amount       NUMERIC(10,2) NOT NULL
  paid_at      TIMESTAMPTZ   NOT NULL DEFAULT now()
  method       TEXT          NOT NULL   -- 'card', 'bank_transfer', etc.
```

**Key relationships:**
- `users` → `orders`: one-to-many
- `orders` → `order_items`: one-to-many
- `products` → `order_items`: one-to-many (a product appears in many order items)
- `orders` → `payments`: one-to-one

## API Contracts (if applicable)

Not applicable — this is a data layer project. Interface is SQL and stored procedures/functions.

Expose the following as SQL functions or application-layer transactions:

- `place_order(user_id, items[{product_id, quantity}])` → creates order + items atomically, decrements stock
- `pay_order(order_id, amount, method)` → creates payment record, transitions order to 'paid'
- `cancel_order(order_id)` → transitions to 'cancelled', restores stock

## Success Criteria

- [ ] Schema creates without errors; all constraints and foreign keys are in place
- [ ] `place_order` is wrapped in a transaction; concurrent calls do not oversell stock (test with two simultaneous orders for the same low-stock product)
- [ ] Invalid state transitions are rejected (e.g., shipping a cancelled order)
- [ ] The following 20 queries run and return correct results:
  - [ ] All products in a category, sorted by price
  - [ ] Search products by name (case-insensitive)
  - [ ] All active products with stock_qty > 0
  - [ ] All orders for a user with their total value
  - [ ] All order items for a given order with product names and prices
  - [ ] Total revenue per month (last 12 months)
  - [ ] Top 10 best-selling products by quantity
  - [ ] Top 10 best-selling products by revenue
  - [ ] Orders in 'paid' status older than 7 days (identify stuck orders)
  - [ ] Average order value per user
  - [ ] Products that have never been ordered
  - [ ] Current stock levels for all products, sorted by stock ascending
  - [ ] Users with more than 3 orders
  - [ ] Daily order count and revenue for the last 30 days
  - [ ] Category breakdown of revenue
  - [ ] All orders placed between two dates
  - [ ] Orders with more than 5 items
  - [ ] Average days between order creation and delivery (for completed orders)
  - [ ] Users who have ordered the same product more than once
  - [ ] Products where stock_qty is below a threshold (low-stock alert)
- [ ] EXPLAIN ANALYZE on the product search and top-selling queries shows index scans, not sequential scans
- [ ] Schema is documented: relationships described, constraints explained

## Difficulty Level

[x] Intermediate — combines normalization, transactions, indexing, and performance analysis

## Estimated Time

6–8 weeks (concurrent with the Databases section)

## Portfolio / Interview Value

**How to explain in an interview:**

> "I built the relational database layer for an e-commerce system — schema design, transaction semantics, and query optimization. The interesting part was implementing the order state machine with atomic inventory decrement. I reproduced a race condition where two concurrent orders could both read available stock and proceed to decrement, resulting in negative inventory, then fixed it with a `SELECT ... FOR UPDATE` lock inside the transaction. I also analyzed query plans and added composite indexes on the most expensive queries, reducing product search from a sequential scan to an index scan."

**Technical decisions this project forces:**
- Surrogate vs natural keys for products
- Whether to store unit_price in order_items (yes — price can change)
- How to enforce state machine transitions (CHECK constraint vs application layer vs both)
- When to use `SELECT ... FOR UPDATE` vs optimistic locking
- What to index and why (not every column, just the ones in WHERE and ORDER BY on hot queries)

---

## Tips for Project Execution

**Before you start:**
- Read the entire spec. Know what "done" looks like before writing the first CREATE TABLE.
- Set up a local database (PostgreSQL). Don't use SQLite for this — the query planner and locking behavior differ.

**While building:**
- Write the schema DDL in a file (`schema.sql`), not in a GUI. Version-control everything.
- Write test data insertion scripts early. It's hard to test queries against an empty database.
- Run EXPLAIN (not EXPLAIN ANALYZE) first to see the plan without executing the query. Use EXPLAIN ANALYZE when you've added indexes and want to verify.

**When you think you're done:**
- Re-read the success criteria. Check each one.
- Test the race condition for stock decrement explicitly — don't assume transactions fix it automatically.
- Document the schema. Not for others (yet) — for you, in a week, when you've forgotten why you made a decision.

**After completion:**
- Push to GitHub with a clear README explaining what the project does, how to run it, and what interesting problems it solved.
- This project is worth showing in interviews. Most candidates have todo apps. An e-commerce data layer with documented transaction handling and query analysis is differentiated.

---

*See also: [PROGRESS.md](PROGRESS.md) for the full checklist, [RESOURCES.md](RESOURCES.md) for SQL learning resources.*
