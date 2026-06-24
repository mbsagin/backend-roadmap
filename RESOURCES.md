# Learning Resources

Curated resources organized by topic. Documentation, Books, Video, Courses, and Communities.

**Curation criteria:** Primary sources and high-signal content only. No paid bootcamp promotions. Free resources are marked `[Free]`. Paid resources are marked `[Paid]`.

The standard recommendation: read primary documentation first. Official docs are maintained, accurate, and written by the people who built the thing. Secondary resources (YouTube, books) fill gaps in understanding, not replace docs.

---

## Networking

**Documentation**
- [MDN Web Docs — HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) `[Free]` — Definitive reference for HTTP protocol, headers, status codes, methods
- [RFC 7231 — HTTP/1.1](https://datatracker.ietf.org/doc/html/rfc7231) `[Free]` — Primary spec. Dense. Read the request/response sections, not the full document.
- [Cloudflare Learning Center](https://www.cloudflare.com/learning/) `[Free]` — Excellent plain-language explanations of DNS, TLS, CDN, DDoS. Highly recommended for conceptual clarity.

**Books**
- *Computer Networking: A Top-Down Approach* — Kurose & Ross `[Paid]` — Standard university textbook. Dense but thorough. Read chapters 1–4, 7.
- *High-Performance Browser Networking* — Ilya Grigorik `[Free at hpbn.co]` — HTTP/2, TLS, WebSockets, WebRTC. Practical and well-written.

**Video**
- Hussein Nasser — [YouTube Channel](https://www.youtube.com/@hnasr) `[Free]` — Deep dives on networking, databases, and protocols. Some of the best free technical content available.

---

## Programming Fundamentals

Choose resources for the language you've selected.

**Python**
- [Python Official Docs](https://docs.python.org/3/) `[Free]` — Tutorial and library reference
- [Real Python](https://realpython.com/) `[Free/Paid]` — Practical tutorials with depth
- [Fluent Python, 2nd ed.](https://www.oreilly.com/library/view/fluent-python-2nd/9781492056348/) — Luciano Ramalho `[Paid]` — The best book for going deep in Python
- [Python Data Structures and Algorithms](https://github.com/TheAlgorithms/Python) `[Free]` — Reference implementations

**Go**
- [A Tour of Go](https://go.dev/tour/) `[Free]` — Official interactive tour. Start here.
- [Go by Example](https://gobyexample.com/) `[Free]` — Annotated example programs
- [Effective Go](https://go.dev/doc/effective_go) `[Free]` — Official idioms and conventions
- *The Go Programming Language* — Donovan & Kernighan `[Paid]` — The definitive Go book

**Rust**
- [The Rust Book](https://doc.rust-lang.org/book/) `[Free]` — Official book. Read it cover to cover.
- [Rustlings](https://github.com/rust-lang/rustlings) `[Free]` — Small exercises to learn Rust concepts
- [Rust by Example](https://doc.rust-lang.org/rust-by-example/) `[Free]` — Annotated examples

**Java / Kotlin**
- [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/) `[Free]`
- [Kotlin Docs](https://kotlinlang.org/docs/home.html) `[Free]` — Official Kotlin documentation
- *Effective Java, 3rd ed.* — Joshua Bloch `[Paid]` — Essential for Java engineers
- *Kotlin in Action, 2nd ed.* `[Paid]`

**Algorithms (language-agnostic)**
- [The Algorithm Design Manual](https://www.algorist.com/) — Skiena `[Paid]` — Best book for building intuition
- [LeetCode](https://leetcode.com/) `[Free/Paid]` — Practice problems. Focus on Easy/Medium. Don't grind before you have fundamentals.
- [Visualgo](https://visualgo.net/) `[Free]` — Visualizes algorithms and data structures. Useful for developing intuition.

---

## Operating Systems

**Documentation**
- [Linux man pages](https://man7.org/linux/man-pages/) `[Free]` — Primary reference for Linux system calls and commands
- [The Linux Command Line](https://linuxcommand.org/tlcl.php) `[Free]` — William Shotts. Available free online. Comprehensive and practical.

**Books**
- *Operating Systems: Three Easy Pieces* (OSTEP) `[Free at ostep.org]` — Remzi & Andrea Arpaci-Dusseau. Best free OS textbook. Read: virtualization (processes, memory), concurrency (basic), persistence (file systems).
- *The Linux Programming Interface* — Michael Kerrisk `[Paid]` — Definitive Linux system programming reference. Reference book, not a cover-to-cover read.

**Video**
- [MIT 6.004 Computation Structures](https://ocw.mit.edu/courses/6-004-computation-structures-spring-2017/) `[Free]` — MIT OpenCourseWare. Deeper than this section requires, but useful for STEM graduates who want the full picture.

---

## Concurrency & Async Programming

**Documentation**
- Official documentation for your language's concurrency primitives (goroutines/channels for Go, asyncio for Python, threads for Java/Python, tokio for Rust)
- [Java Concurrency in Practice — Summary](https://jcip.net/) `[Paid]` — Definitive Java concurrency resource

**Books**
- *Java Concurrency in Practice* — Goetz et al. `[Paid]` — Java-specific but the concurrency patterns are universal
- *Programming Rust* (Fearless Concurrency chapter) `[Paid]` — Excellent for understanding ownership and concurrency

**Video**
- Rob Pike — [Concurrency Is Not Parallelism](https://www.youtube.com/watch?v=oV9rvDllKEg) `[Free]` — 30-minute talk. Clear and essential.
- Philip Roberts — [What the heck is the event loop anyway?](https://www.youtube.com/watch?v=8aGhZQkoFbQ) `[Free]` — The classic JSConf talk on async I/O and the event loop. Language-agnostic insight regardless of your stack.

---

## Relational Databases & SQL

**Documentation**
- [PostgreSQL Documentation](https://www.postgresql.org/docs/current/) `[Free]` — Best SQL database documentation. Thorough, well-organized.
- [Use The Index, Luke!](https://use-the-index-luke.com/) `[Free]` — Explains SQL indexes in a way that actually builds understanding. Not just syntax — reasoning.
- [EXPLAIN documentation (PostgreSQL)](https://www.postgresql.org/docs/current/sql-explain.html) `[Free]` — Essential for reading query plans

**Books**
- *Designing Data-Intensive Applications* — Martin Kleppmann `[Paid]` — The most important book in this entire roadmap. Covers databases, distributed systems, and stream processing with unmatched depth. Buy it.
- *SQL Performance Explained* — Markus Winand `[Free chapters at use-the-index-luke.com]` — Focused entirely on index performance

**Video**
- CMU Database Group — [15-445/645 Database Systems (YouTube)](https://www.youtube.com/playlist?list=PLSE8ODhjZXjbohkNBWQs_otTrBTrjyohi) `[Free]` — Full university course. Lectures 1–10 are essential. This is graduate-level material.
- Hussein Nasser — [Database Engineering playlist](https://www.youtube.com/@hnasr/playlists) `[Free]`

---

## Git & Professional Tooling

**Documentation**
- [Pro Git Book](https://git-scm.com/book/en/v2) `[Free]` — Official, comprehensive, well-written. Chapters 1–5 cover everything in this section.
- [Conventional Commits](https://www.conventionalcommits.org/) `[Free]` — Standard for writing structured commit messages
- [GitHub Actions Documentation](https://docs.github.com/en/actions) `[Free]` — Relevant during Docker & CI/CD, but useful to skim now

**Interactive**
- [Learn Git Branching](https://learngitbranching.js.org/) `[Free]` — Visual, interactive. Best way to learn branching and rebasing.

---

## Backend Architecture

**Books**
- *Clean Architecture* — Robert C. Martin `[Paid]` — Core concepts of separation of concerns and dependency direction. Skip the dogma, absorb the principles.
- *Domain-Driven Design* — Eric Evans `[Paid]` — Dense. Read the strategic design sections (Parts I and II). Leave the tactical patterns for later.
- *A Philosophy of Software Design* — John Ousterhout `[Paid]` — Short (190 pages), practical, opinionated. Excellent.

**Video**
- [ArjanCodes YouTube Channel](https://www.youtube.com/@ArjanCodes) `[Free]` — Python-focused architecture, SOLID, design patterns. Concrete and practical.

---

## API Design

**Documentation**
- [OpenAPI Specification](https://swagger.io/specification/) `[Free]` — The spec itself
- [Swagger UI](https://swagger.io/tools/swagger-ui/) `[Free]` — Test and document APIs
- [Google API Design Guide](https://cloud.google.com/apis/design) `[Free]` — Google's internal REST conventions. Opinionated and battle-tested.
- [gRPC Documentation](https://grpc.io/docs/) `[Free]` — Official gRPC docs and tutorials
- [Protocol Buffers Language Guide](https://protobuf.dev/programming-guides/proto3/) `[Free]`

**Books**
- *RESTful Web APIs* — Richardson & Amundsen `[Paid]` — Thorough treatment of REST as an architectural style, not just HTTP conventions

---

## Security

**Documentation**
- [OWASP Top 10](https://owasp.org/www-project-top-ten/) `[Free]` — Read every entry. Understand the attack vector, not just the name.
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) `[Free]` — Comprehensive security testing reference
- [Have I Been Pwned](https://haveibeenpwned.com/Passwords) `[Free]` — Understand what breached password datasets look like

**Books**
- *The Web Application Hacker's Handbook* `[Paid]` — Dense but authoritative. Understand how attacks work before you write defenses.

**Courses**
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) `[Free]` — The best free security training available. Hands-on labs for every OWASP category.

---

## Observability

**Documentation**
- [OpenTelemetry Documentation](https://opentelemetry.io/docs/) `[Free]` — The emerging standard for observability instrumentation
- [Prometheus Documentation](https://prometheus.io/docs/introduction/overview/) `[Free]`
- [Grafana Documentation](https://grafana.com/docs/grafana/latest/) `[Free]`

**Books**
- *Observability Engineering* — Majors, Fong-Jones, Miranda `[Paid]` — Modern approach to observability beyond metrics and logs

**Reading**
- [Google SRE Book](https://sre.google/sre-book/table-of-contents/) `[Free]` — Chapters 6 (monitoring), 10 (practical alerting), and 11 (being on-call) are directly relevant here. Free online.

---

## Testing

**Documentation**
- Testing framework docs for your language: pytest, Jest, JUnit, Go testing package, Rust test module — read the official docs
- [Martin Fowler — Testing](https://martinfowler.com/testing/) `[Free]` — Definitive articles on test doubles, the test pyramid, and testing strategy

**Books**
- *Unit Testing: Principles, Practices, and Patterns* — Vladimir Khorikov `[Paid]` — Best modern book on unit testing. Language-agnostic principles.
- *Growing Object-Oriented Software, Guided by Tests* — Freeman & Pryce `[Paid]` — TDD from first principles. Influential.

---

## Docker & CI/CD

**Documentation**
- [Docker Official Documentation](https://docs.docker.com/) `[Free]` — Guides section covers everything in this section
- [Docker Compose Reference](https://docs.docker.com/compose/) `[Free]`
- [GitHub Actions Documentation](https://docs.github.com/en/actions) `[Free]`
- [GitLab CI/CD Documentation](https://docs.gitlab.com/ee/ci/) `[Free]`

**Books**
- *Docker Deep Dive* — Nigel Poulton `[Paid]` — Short, clear, and practical

**Video**
- [TechWorld with Nana](https://www.youtube.com/@TechWorldwithNana) `[Free]` — Docker and Kubernetes tutorials. Concrete and visual.

---

## Scalability & Distributed Systems

**Books**
- *Designing Data-Intensive Applications* — Martin Kleppmann `[Paid]` — If you haven't bought this yet, buy it now. Covers replication, partitioning, transactions, batch/stream processing.
- *System Design Interview* — Alex Xu (Vol 1 & 2) `[Paid]` — Less academic than Kleppmann, but good for building intuition on real systems (URL shorteners, rate limiters, chat systems)

**Documentation**
- [Redis Documentation](https://redis.io/docs/) `[Free]`
- [Apache Kafka Documentation](https://kafka.apache.org/documentation/) `[Free]`
- [RabbitMQ Documentation](https://www.rabbitmq.com/documentation.html) `[Free]`

**Video**
- [System Design Primer](https://github.com/donnemartin/system-design-primer) `[Free]` — GitHub repo. One of the most starred repos on GitHub. Comprehensive and well-organized.
- [Hussein Nasser — Distributed Systems playlist](https://www.youtube.com/@hnasr) `[Free]`
- MIT 6.824 Distributed Systems — [Lectures on YouTube](https://www.youtube.com/playlist?list=PLrw6a1wE39_tb2fErI4-WkMbsvGQk9_UB) `[Free]` — Graduate-level. Raft, MapReduce, Spanner. Worth watching after you have the Scalability basics solid.

---

## Cloud Fundamentals

**Documentation**
- [AWS Documentation](https://docs.aws.amazon.com/) `[Free]` — EC2, RDS, S3, IAM, VPC. Start with the Getting Started guides for each service.
- [Google Cloud Documentation](https://cloud.google.com/docs) `[Free]`
- [Azure Documentation](https://docs.microsoft.com/en-us/azure/) `[Free]`

**Courses**
- [AWS Cloud Practitioner Essentials](https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/) `[Free]` — Free foundational course from AWS. Good overview before going deep.
- [A Cloud Guru](https://acloudguru.com/) `[Paid]` — Structured cloud certification paths
- [Cloud Academy](https://cloudacademy.com/) `[Paid]`

*Note: Cloud certifications (AWS SAA, GCP ACE) have value but are not a substitute for hands-on deployment. Don't study for the cert without also deploying real services.*

---

## Specialization

### Fintech
- [Stripe Documentation](https://stripe.com/docs) `[Free]` — Best payment API documentation in the industry. Informative even if you don't use Stripe.
- [PCI Security Standards Council](https://www.pcisecuritystandards.org/) `[Free]` — PCI-DSS standards documentation
- [Open Banking resources](https://standards.openbanking.org.uk/) `[Free]`

### E-commerce
- [Shopify Developer Documentation](https://shopify.dev/) `[Free]` — Well-documented real-world e-commerce system
- [Stripe Payments Documentation](https://stripe.com/docs/payments) `[Free]`

### Infrastructure / Platform Engineering
- [Kubernetes Documentation](https://kubernetes.io/docs/home/) `[Free]` — Official docs. Start with Concepts, then Tutorials.
- [Helm Documentation](https://helm.sh/docs/) `[Free]`
- [The Kubernetes Book](https://www.amazon.com/Kubernetes-Book-Nigel-Poulton/dp/1916585000) — Nigel Poulton `[Paid]` — Clear starting point
- [Raft Consensus Algorithm](https://raft.github.io/) `[Free]` — The readable version of distributed consensus

### Real-time Systems
- [WebSocket RFC 6455](https://tools.ietf.org/html/rfc6455) `[Free]` — The spec
- [Kafka: The Definitive Guide](https://www.oreilly.com/library/view/kafka-the-definitive/9781492043072/) `[Free PDF from Confluent]`
- [Flink Documentation](https://nightlies.apache.org/flink/flink-docs-release-1.19/) `[Free]`

---

## Communities

These are the communities worth spending time in. Low noise, high signal.

**Reddit**
- [r/programming](https://www.reddit.com/r/programming/) — General engineering, link-heavy
- [r/learnprogramming](https://www.reddit.com/r/learnprogramming/) — Questions, resources, support
- [r/golang](https://www.reddit.com/r/golang/) — Go-specific
- [r/rust](https://www.reddit.com/r/rust/) — Rust-specific, very active
- [r/java](https://www.reddit.com/r/java/)
- [r/Python](https://www.reddit.com/r/Python/)
- [r/ExperiencedDevs](https://www.reddit.com/r/ExperiencedDevs/) — Discussions from working engineers
- [r/cscareerquestions](https://www.reddit.com/r/cscareerquestions/) — Job market, interviews, career navigation

**Discord**
- [The Programmer's Hangout](https://discord.gg/programming) — Large general programming community
- [Reactiflux](https://www.reactiflux.com/) — JavaScript/TypeScript ecosystem
- Language-specific Discords: Rustaceans Official, Gophers, Python Discord — search for the official server for your language

**Other**
- [Hacker News](https://news.ycombinator.com/) `[Free]` — High-quality technical discussions. Read the comments on relevant posts; they often contain more insight than the linked article.
- [Stack Overflow](https://stackoverflow.com/) `[Free]` — Questions and answers. Better for lookup than learning. Don't copy-paste; understand.
- [GitHub](https://github.com/) `[Free]` — Read the source code of tools you use. It's public. It teaches more than any tutorial.

---

*See also: [FAQ.md](FAQ.md) — choosing your first language and managing pace. [PROGRESS.md](PROGRESS.md) — tracking your progress section by section.*
