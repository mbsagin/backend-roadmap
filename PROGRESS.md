# Learning Progress Tracker

Track your journey through the Backend Developer Roadmap.

**How to use this file:**

1. Fork the [backend-roadmap](https://github.com/mbsagin/backend-roadmap) repository to your own GitHub account
2. Copy this file to your fork (or keep a local copy)
3. Check off items as you complete them — commit your progress regularly
4. Use this alongside the [interactive roadmap](https://mbsagin.github.io/backend-roadmap/) which shows the content for each section

**Total estimated time:** 700–900 hours | 12–18 months at consistent effort

---

## Networking (1–2 weeks)

*Goal: Understand how computers communicate before you build systems on top of networks.*

### Concepts
- [ ] TCP/IP stack: OSI layers, ports, packet delivery, reliability guarantees
- [ ] Three-way handshake (SYN, SYN-ACK, ACK) and connection termination
- [ ] DNS: name resolution, TTLs, A/AAAA/CNAME records, propagation
- [ ] HTTP/1.1: request/response structure, headers, status codes, methods
- [ ] HTTP/2 and HTTP/3: multiplexing, header compression, QUIC
- [ ] TLS/HTTPS: handshake, certificates, public/private key basics
- [ ] Sockets: what they are, blocking vs non-blocking I/O
- [ ] UDP vs TCP: when to use each, trade-offs

### Hands-on
- [ ] Use `curl -v` to inspect raw HTTP request/response headers
- [ ] Use `dig` or `nslookup` to trace DNS resolution
- [ ] Write a raw TCP socket server that echoes back messages
- [ ] Capture packets with `tcpdump` or Wireshark; read a handshake

---

## Programming Fundamentals (8–10 weeks)

*Goal: Deep fluency in one backend language. Syntax is easy; thinking in the language is not.*

*Supported languages: Python, Go, Rust, Java/Kotlin, C#/.NET, Node.js/TypeScript. Pick one. See [FAQ.md](FAQ.md) and [RESOURCES.md](RESOURCES.md) for language-specific resources.*

### Language Basics (weeks 1–2)
- [ ] Variables, types, control flow, functions, closures
- [ ] Memory model for your language (stack vs heap, GC vs ownership)
- [ ] Error handling idioms (exceptions, Result types, error codes)
- [ ] Standard library: collections, I/O, strings, time

### Data Structures (weeks 3–4)
- [ ] Arrays and dynamic arrays
- [ ] Linked lists (singly, doubly)
- [ ] Hash maps / hash tables — understand collision resolution
- [ ] Sets
- [ ] Stacks and queues
- [ ] Heaps / priority queues
- [ ] Trees (binary trees, BSTs)
- [ ] Graphs (adjacency list, adjacency matrix)

### Algorithms (weeks 5–6)
- [ ] Big O notation — time and space complexity
- [ ] Sorting: bubble, merge, quick, heap — understand trade-offs
- [ ] Binary search
- [ ] Tree traversal: DFS (pre/in/post-order), BFS
- [ ] Graph traversal: DFS, BFS, topological sort
- [ ] Recursion and dynamic programming basics

### Build Project (weeks 7–10)
- [ ] Implement a hash table from scratch (handle collisions)
- [ ] Implement a binary search tree (insert, search, delete)
- [ ] Implement a graph with DFS and BFS
- [ ] Write a test suite for each data structure

---

## Operating Systems (2–3 weeks)

*Goal: Understand the environment your backend runs in. Limited resources are not abstractions.*

### Concepts
- [ ] Process lifecycle: creation, execution, termination, exit codes
- [ ] Threads vs processes: fork, exec, context switching
- [ ] Memory layout: stack, heap, code segment, BSS
- [ ] Virtual memory and paging
- [ ] File descriptors and the everything-is-a-file model
- [ ] Blocking vs non-blocking I/O
- [ ] Signals (SIGTERM, SIGKILL, SIGINT) and graceful shutdown
- [ ] Environment variables, PATH, working directory

### Linux Essentials
- [ ] Navigation: `ls`, `cd`, `pwd`, `find`, `grep`
- [ ] File operations: `cp`, `mv`, `rm`, `chmod`, `chown`
- [ ] Process management: `ps`, `top`, `htop`, `kill`, `pkill`
- [ ] I/O redirection: `>`, `>>`, `|`, `/dev/null`
- [ ] Network: `curl`, `wget`, `netstat`, `ss`, `lsof`
- [ ] Disk: `df`, `du`, `mount`

### Hands-on
- [ ] Write a script that monitors a process and restarts it on crash
- [ ] Use `strace` to inspect system calls of a running program
- [ ] Implement graceful shutdown in your language fundamentals project (handle SIGTERM)

---

## Concurrency & Async Programming (2–3 weeks)

*Goal: Modern backends serve thousands of requests simultaneously. Understand how, and where it goes wrong.*

### Concepts
- [ ] Thread creation and lifecycle
- [ ] Shared state and race conditions — reproduce one intentionally
- [ ] Mutex and locks: what they protect and when to use them
- [ ] Deadlocks: conditions for occurrence, prevention strategies
- [ ] Semaphores and condition variables
- [ ] Thread pools: why raw thread creation is expensive
- [ ] Async/await: event loop, coroutines, non-blocking I/O
- [ ] Futures and promises
- [ ] Actor model (conceptual understanding)

### Hands-on
- [ ] Write a multi-threaded counter, reproduce a race condition
- [ ] Fix it with a mutex; measure the overhead
- [ ] Write an async HTTP client that fetches 10 URLs concurrently
- [ ] Implement a simple worker pool

---

## Relational Databases & SQL (6–8 weeks)

*Goal: Schema design and query optimization are engineering skills, not DBA skills. Every backend engineer needs them.*

### Schema Design (weeks 1–2)
- [ ] Normalization: 1NF, 2NF, 3NF — and when to denormalize
- [ ] Relationships: one-to-one, one-to-many, many-to-many
- [ ] Foreign keys and referential integrity
- [ ] Constraints: NOT NULL, UNIQUE, CHECK
- [ ] Primary key choices: surrogate vs natural keys

### SQL (weeks 3–4)
- [ ] SELECT, FROM, WHERE, ORDER BY, LIMIT
- [ ] JOINs: INNER, LEFT, RIGHT, FULL OUTER
- [ ] GROUP BY, HAVING, aggregate functions (COUNT, SUM, AVG, MIN, MAX)
- [ ] Subqueries and correlated subqueries
- [ ] Window functions: ROW_NUMBER, RANK, LAG, LEAD
- [ ] CTEs (WITH clauses)
- [ ] INSERT, UPDATE, DELETE, UPSERT
- [ ] Indexes: CREATE INDEX, covering indexes, partial indexes

### Performance & Transactions (weeks 5–6)
- [ ] B-tree index internals (conceptual)
- [ ] EXPLAIN / EXPLAIN ANALYZE: reading a query plan
- [ ] N+1 query problem: what it is, how to detect, how to fix
- [ ] ACID properties: Atomicity, Consistency, Isolation, Durability
- [ ] Transaction isolation levels: READ UNCOMMITTED → SERIALIZABLE
- [ ] Deadlocks in transactions: why they happen, how to handle
- [ ] Optimistic vs pessimistic locking

### Build Project (weeks 7–8)
- [ ] Design schema: users, products, orders, payments, order_items
- [ ] Implement order state machine (pending → paid → shipped → delivered) using transactions
- [ ] Write 20+ queries: search by category, filter by price range, monthly revenue aggregation, top products
- [ ] Identify hot query paths and add appropriate indexes
- [ ] Document the schema with an ERD or written relationships map

*See [PROJECT_TEMPLATE.md](PROJECT_TEMPLATE.md) for the full spec of this project.*

---

## Git & Professional Tooling (2–3 weeks)

*Goal: These tools are table stakes. Every professional backend team uses them. Incompetence here signals inexperience immediately.*

### Git
- [ ] init, add, commit, status, log, diff
- [ ] Branches: create, switch, merge, delete
- [ ] Rebase: interactive rebase, squashing commits
- [ ] Remote: push, pull, fetch, clone
- [ ] Conflict resolution: understand what a conflict means, resolve it cleanly
- [ ] Cherry-pick, stash, reset (soft vs hard)
- [ ] Pull request workflow: branch naming, commit messages, review etiquette

### Linters, Formatters, and Static Analysis
- [ ] Set up a linter for your language (ESLint, golangci-lint, flake8/ruff, Clippy)
- [ ] Set up a formatter (Prettier, gofmt, black, rustfmt)
- [ ] Understand what static analysis catches that tests miss
- [ ] Configure pre-commit hooks

### Debuggers
- [ ] Set breakpoints, step through code in your IDE debugger
- [ ] Inspect variables at runtime
- [ ] Use conditional breakpoints
- [ ] Post-mortem debugging: read a stack trace, find the root cause

### Package Management
- [ ] Understand semantic versioning (major.minor.patch)
- [ ] Lock files: what they do and why they exist
- [ ] Scan dependencies for known vulnerabilities (`npm audit`, `cargo audit`, `safety`)

---

## Backend Architecture Fundamentals (3–4 weeks)

*Goal: Organize code so it's maintainable and testable. The wrong architecture is debt that compounds.*

### Layered Architecture
- [ ] Controllers/Handlers — parse requests, validate input, return responses
- [ ] Services/Use Cases — business logic, orchestration
- [ ] Repositories/DAOs — data access, no business logic
- [ ] Separation of concerns: why mixing layers creates bugs
- [ ] Dependency direction: outer layers depend on inner layers, never reversed

### Design Patterns
- [ ] Dependency Injection: what it is, why it makes code testable
- [ ] Repository pattern: abstract data access behind an interface
- [ ] Factory and Builder patterns: when construction is complex
- [ ] Observer/Event patterns: decoupled notifications
- [ ] Strategy pattern: swap behavior at runtime

### Practical Application
- [ ] Refactor your data structures project to use layered architecture
- [ ] Wire up DI manually (no framework yet) — understand what a container does before you use one
- [ ] Write a service that has zero knowledge of HTTP (pure business logic)
- [ ] Write tests for the service layer without a running database

---

## API Design: REST & gRPC (4–5 weeks)

*Goal: APIs are contracts between systems. Poor contracts cause bugs forever. Good contracts prevent entire categories of bugs.*

### REST Principles
- [ ] Resources vs actions: nouns in URLs, not verbs
- [ ] HTTP verbs and idempotency: GET, POST, PUT, PATCH, DELETE
- [ ] Status codes used correctly: 200, 201, 204, 400, 401, 403, 404, 409, 422, 500
- [ ] Pagination: offset/limit and cursor-based
- [ ] Filtering and sorting via query params
- [ ] Versioning strategies: URI versioning vs header versioning

### Request/Response Design
- [ ] Consistent error response format
- [ ] Input validation: fail fast, return all errors at once
- [ ] Response envelopes: when to use, when not to
- [ ] Content negotiation

### API Documentation
- [ ] Write an OpenAPI (Swagger) spec for an API you've built
- [ ] Test the spec with Swagger UI

### gRPC
- [ ] Understand Protocol Buffers: define a .proto schema
- [ ] Understand when gRPC is better than REST (internal services, streaming, performance)
- [ ] Write a simple gRPC server and client

### Build Project
- [ ] Build a versioned REST API for the e-commerce schema from the Databases section
- [ ] Include: auth endpoints, product CRUD, order flow, proper error handling
- [ ] Write an OpenAPI spec for it
- [ ] Test all endpoints with a client (curl, HTTPie, Postman, or a test suite)

---

## Security Fundamentals (3–4 weeks)

*Goal: Security bugs are often irreversible — leaked credentials, exposed data, compromised users. Build the right habits now.*

### Authentication
- [ ] Password hashing: bcrypt or Argon2, salts, why MD5/SHA1 are wrong
- [ ] JWT: structure (header.payload.signature), signing algorithms, expiry
- [ ] Session-based auth: cookies, session stores, CSRF
- [ ] OAuth 2.0: authorization code flow, client credentials, tokens
- [ ] Refresh tokens: rotation, revocation

### Authorization
- [ ] Role-based access control (RBAC): roles, permissions, enforcement
- [ ] Attribute-based access control (ABAC): policy evaluation
- [ ] Row-level security in databases
- [ ] Principle of least privilege

### Common Vulnerabilities
- [ ] SQL injection: reproduce it, then fix it with parameterized queries
- [ ] Cross-site scripting (XSS): stored vs reflected
- [ ] CSRF: how it works, SameSite cookie protection
- [ ] Path traversal: `../../etc/passwd`
- [ ] Insecure deserialization
- [ ] OWASP Top 10: read and understand each entry

### Secrets Management
- [ ] Never hardcode credentials in code (even tests)
- [ ] Environment variables as the minimum standard
- [ ] Secrets managers: AWS Secrets Manager, HashiCorp Vault (conceptual)

---

## Observability (3–4 weeks)

*Goal: You cannot fix what you cannot see. This is not about dashboards — it's about being able to answer "why is this broken?" in production.*

### Logging
- [ ] Structured logging (JSON): why unstructured logs don't scale
- [ ] Log levels: DEBUG, INFO, WARN, ERROR, FATAL — use them correctly
- [ ] Correlation IDs: trace a request across multiple log lines
- [ ] What to log: requests, errors, key business events — not passwords, tokens, or PII
- [ ] Log aggregation tools: ELK stack, Loki, Datadog (conceptual)

### Metrics
- [ ] RED method: Rate, Errors, Duration
- [ ] USE method: Utilization, Saturation, Errors
- [ ] Prometheus metrics types: Counter, Gauge, Histogram, Summary
- [ ] Instrument your REST API with request latency and error rate metrics
- [ ] Grafana dashboard basics (conceptual)

### Distributed Tracing
- [ ] Trace context propagation across services
- [ ] Spans and trace IDs
- [ ] OpenTelemetry: the open standard for instrumentation
- [ ] Jaeger or Zipkin (conceptual)

### Alerting
- [ ] Alert on symptoms (high error rate, high latency), not just causes
- [ ] On-call basics: escalation, runbooks
- [ ] Avoid alert fatigue: don't alert on things that don't require action

---

## Testing Strategy (4–5 weeks)

*Goal: Untested code is broken code. The testing pyramid is a load-bearing structure, not a suggestion.*

### Testing Philosophy
- [ ] Testing pyramid: many unit tests, fewer integration tests, minimal E2E tests
- [ ] What makes a good test: deterministic, isolated, fast, one assertion
- [ ] Test doubles: mocks, stubs, spies, fakes — when to use each

### Unit Tests
- [ ] Test pure functions thoroughly
- [ ] Mock external dependencies (databases, HTTP clients, clocks)
- [ ] Arrange/Act/Assert structure
- [ ] Edge cases: nulls, empty inputs, boundary values, unexpected types
- [ ] Aim for 70–80% coverage on business logic

### Integration Tests
- [ ] Test with a real database (not mocked) — use a test database or Docker
- [ ] Test your repository layer against real queries
- [ ] Test your API endpoints end-to-end within the service

### E2E Tests
- [ ] Test critical user paths only (checkout, login, payment)
- [ ] Understand why E2E tests are slow and flaky — and accept that trade-off selectively

### Build
- [ ] Add a full test suite to your REST API project
- [ ] Achieve 70%+ coverage on service layer
- [ ] Write at least one regression test for a bug you've already fixed

---

## Docker & CI/CD (4–5 weeks)

*Goal: Code that doesn't run in production reliably is not production code.*

### Docker
- [ ] Images vs containers: the difference
- [ ] Dockerfile: FROM, RUN, COPY, CMD, ENTRYPOINT, EXPOSE
- [ ] Layer caching: understand how to write Dockerfiles efficiently
- [ ] Multi-stage builds: keep images small
- [ ] Docker Compose: define multi-container environments (app + db + cache)
- [ ] Networking in Docker: bridge, host, overlay
- [ ] Container registries: Docker Hub, ECR, GCR

### CI/CD
- [ ] What CI does: automated test on every push
- [ ] What CD does: automated deployment on passing tests
- [ ] Write a GitHub Actions workflow: lint → test → build → (deploy)
- [ ] Environment variables in CI: secrets handling
- [ ] Deployment strategies: blue-green, canary, rolling update — understand each

### Build
- [ ] Containerize your REST API project
- [ ] Write a Docker Compose file with app + PostgreSQL + Redis
- [ ] Set up GitHub Actions: run tests on every pull request
- [ ] Add a deployment step (even to a free-tier service: Railway, Fly.io, Render)

---

## Scalability & Distributed Systems (6–8 weeks)

*Goal: Your app works with 10 users. What about 10 million? This is where backend engineering gets hard.*

### Scaling Fundamentals
- [ ] Vertical vs horizontal scaling: limits and trade-offs
- [ ] Stateless services: why they scale, what makes a service stateful
- [ ] Load balancing algorithms: round-robin, least connections, IP hash
- [ ] Health checks and automatic failover
- [ ] Session management in a horizontally scaled service

### Caching
- [ ] Cache-aside pattern
- [ ] Write-through and write-behind patterns
- [ ] TTL design: too short vs too long
- [ ] Cache invalidation: the hard problem
- [ ] Redis basics: data types (strings, hashes, sets, sorted sets, lists), expiry, pub/sub

### Database Scaling
- [ ] Read replicas and replication lag
- [ ] Connection pooling (PgBouncer, HikariCP)
- [ ] Database sharding: range-based vs hash-based
- [ ] Consistent hashing (conceptual)
- [ ] NoSQL trade-offs: when to use Redis, MongoDB, Cassandra vs PostgreSQL

### Message Queues and Event-Driven Architecture
- [ ] Why async processing: decouple producers from consumers
- [ ] Queue semantics: at-most-once, at-least-once, exactly-once
- [ ] RabbitMQ or Kafka: understand one deeply
- [ ] Dead letter queues and retry strategies
- [ ] Event sourcing and CQRS (conceptual)

### Distributed Systems Theory
- [ ] CAP theorem: Consistency, Availability, Partition tolerance
- [ ] PACELC: extension of CAP
- [ ] Eventual consistency: what it means in practice
- [ ] Distributed transactions: two-phase commit, saga pattern

---

## Cloud Fundamentals (3–4 weeks)

*Goal: Most backends run on AWS, GCP, or Azure. Understand the building blocks before you use managed services.*

### Compute
- [ ] Virtual machines vs containers vs serverless — when each makes sense
- [ ] EC2 / Compute Engine / Azure VMs: instance types, pricing, auto-scaling groups
- [ ] Container orchestration: ECS, Cloud Run, App Engine
- [ ] Serverless: Lambda/Cloud Functions — cold starts, statelessness, pricing

### Storage
- [ ] Object storage: S3, GCS, Azure Blob — when to use instead of a database
- [ ] Block storage: EBS, persistent disks
- [ ] CDN: what it is, when to use it, cache headers

### Networking
- [ ] VPCs: subnets, CIDR blocks, public vs private subnets
- [ ] Security groups and network ACLs
- [ ] Load balancers: ALB vs NLB vs CLB
- [ ] Route53 / Cloud DNS: hosted zones, health checks

### Managed Services
- [ ] Managed databases: RDS, Cloud SQL — when to use vs self-hosted
- [ ] Managed caches: ElastiCache, Memorystore
- [ ] Managed queues: SQS, Cloud Pub/Sub

### Build
- [ ] Deploy your containerized API to a real cloud provider (AWS, GCP, or Azure)
- [ ] Set up a managed database and connect your application
- [ ] Configure environment-specific settings without hardcoding

---

## Specialization (4–6 weeks)

*Goal: Go deep in one domain. Breadth got you hired. Depth makes you valuable.*

Pick one track. The others can be explored later.

### Track A: Fintech
- [ ] PCI-DSS compliance basics: what you can and can't store
- [ ] ACID transactions for financial operations: idempotency, double-spend prevention
- [ ] Payment gateway integration (Stripe or similar)
- [ ] Reconciliation: balancing books between systems
- [ ] Audit logs: immutable, append-only records

### Track B: E-commerce
- [ ] Inventory management: reservation, oversell prevention
- [ ] Shopping cart design: session-based vs persistent
- [ ] Payment processing: authorize vs capture, refunds, disputes
- [ ] Order management: state machines, fulfillment integration
- [ ] Search and recommendation: relevance ranking basics

### Track C: Infrastructure / Platform
- [ ] Kubernetes: pods, deployments, services, ingress, namespaces
- [ ] Helm charts: templated Kubernetes configuration
- [ ] Service mesh: Istio or Linkerd basics
- [ ] Disaster recovery: RTO, RPO, backup strategies
- [ ] Multi-region deployments

### Track D: Real-time Systems
- [ ] WebSockets: connection lifecycle, reconnection, scaling
- [ ] Server-Sent Events vs WebSockets: when to use each
- [ ] gRPC streaming: server-streaming, client-streaming, bidirectional
- [ ] Stream processing: Kafka Streams, Flink (conceptual)
- [ ] Real-time analytics: time-series databases (InfluxDB, TimescaleDB)

---

## Time Estimates

| Section | Estimated Time |
|---|---|
| Networking | 1–2 weeks |
| Programming Fundamentals | 8–10 weeks |
| Operating Systems | 2–3 weeks |
| Concurrency & Async | 2–3 weeks |
| Relational Databases | 6–8 weeks |
| Git & Tooling | 2–3 weeks |
| Backend Architecture | 3–4 weeks |
| API Design | 4–5 weeks |
| Security | 3–4 weeks |
| Observability | 3–4 weeks |
| Testing | 4–5 weeks |
| Docker & CI/CD | 4–5 weeks |
| Scalability & Distributed Systems | 6–8 weeks |
| Cloud Fundamentals | 3–4 weeks |
| Specialization | 4–6 weeks |
| **Total** | **55–74 weeks** |

*Overlap is possible (Git & Tooling alongside Databases; Cloud alongside Scalability). Realistic total: **12–18 months** at consistent 2–4 hours/day.*

---

## Staying Motivated

**What works:**

- Commit your progress to GitHub. Public accountability is real.
- Build things that actually interest you. The e-commerce schema is more memorable if you care about the domain.
- Pair a concept with a project. Every section has a concrete deliverable. Don't skip them.
- Track what you've shipped, not what you've read. Reading is cheap. Building is not.
- Connect with others. Find one or two engineers at the same stage. Share code, share struggles.

**What doesn't work:**

- Collecting tutorials without building. Tutorial completion is a false signal of progress.
- Restarting the roadmap. If you're on Architecture and realize your OS knowledge is shaky, go back and fill the gap — don't restart from the beginning.
- Comparing pace. Some engineers move through Programming Fundamentals in 6 weeks. Others take 14. Both can be right if the depth is there.
- Waiting until you feel "ready" to start applying. You won't feel ready. Start applying at 12 months regardless.

---

*See also: [FAQ.md](FAQ.md) for common questions, [RESOURCES.md](RESOURCES.md) for learning materials, [PROJECT_TEMPLATE.md](PROJECT_TEMPLATE.md) for scoping projects.*
