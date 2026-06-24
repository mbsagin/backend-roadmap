# Frequently Asked Questions

Common questions from engineers working through the roadmap. Direct answers, no hedging.

---

## How do I choose a backend language?

Pick one and go deep. The language matters less than your mastery of it.

**Practical guidance:**

- **Python** — Easiest onboarding, vast ecosystem, dominant in data-adjacent backends and scripting. Slower raw performance, but that rarely matters at your career stage. Good first choice.
- **Go** — Excellent for systems and services where concurrency and performance matter. Simple syntax, strong standard library, compiles to a single binary. Strong in infrastructure, fintech, and cloud tooling.
- **Rust** — Steep learning curve (ownership, borrowing). Rewarding if you want systems-level programming or infrastructure roles. Not a first language.
- **Java / Kotlin** — Dominant in enterprise, fintech, and Android. Heavy ecosystem, strong typing, mature. Kotlin is strictly better than Java for new code.
- **C# (.NET)** — Strong in enterprise and gaming backends. Excellent tooling (Rider, Visual Studio). Often underrated outside Microsoft-heavy shops.
- **Node.js (TypeScript)** — Fine for I/O-heavy APIs. TypeScript adds the type safety Node sorely needs. Common in startups.

**Decision rule:** Look at the job listings in your target domain. Pick the language that appears most often. Learn it deeply. Transfer to others later — the fundamentals are the same.

---

## Can I skip phases?

Some phases have hard dependencies. Others are softer.

**Hard dependencies (don't skip):**

- Networking → required before API Design, Observability, and Scalability
- Programming Fundamentals → required for everything
- Databases → required before Architecture and Scalability
- Security → complete before building production APIs (even if you cover it after API Design conceptually, implement it before shipping anything real)

**Safe to reorder or compress if you have prior experience:**

- OS Basics — if you've used Linux professionally, skim
- Git & Tooling — if you already use Git daily in a real workflow, move fast
- Cloud — can be done in parallel with Docker & CI/CD or Scalability

**Rule of thumb:** If you don't understand *why* a phase exists, don't skip it. The phases aren't arbitrary. Each one explains something the next one assumes you know.

---

## What if I'm struggling with a phase?

Slow down. The roadmap timeline is a guide, not a deadline.

Specific strategies:

1. **Time-box confusion.** Spend 25 minutes stuck on a concept before searching. Most blockers dissolve with slightly different search terms or a different explanation.
2. **Build something small.** Reading without building produces fragile knowledge. If Phase 4 (Concurrency) isn't clicking, write a small multi-threaded HTTP server. Concrete failures teach faster than abstract reading.
3. **Change the resource.** If the documentation isn't working, try a YouTube walkthrough. If a video isn't working, try a book. Same concept, different format.
4. **Don't rush into Phase N+1 with a weak Phase N.** Weak foundations compound. A shaky understanding of transactions in Phase 5 will cause real pain in Phase 13.
5. **Post in communities.** r/learnprogramming, r/golang, r/rust, or the relevant Discord for your language. Frame your question with what you tried and what you expected.

Struggling is normal. It means you're at the edge of your current model. That's the only place growth happens.

---

## How do I know I'm ready for a job?

Stop asking the question and start measuring against this checklist:

**Technical readiness:**
- [ ] You can explain TCP/IP, HTTP, and DNS to a non-engineer
- [ ] You can design a normalized database schema for a real-world problem from scratch
- [ ] You have built and deployed at least one working API with authentication
- [ ] You can read a slow query, add an index, and explain why it helped
- [ ] You can write unit tests and explain what you're testing and why
- [ ] You can write a Dockerfile and run your application in a container
- [ ] You can debug an issue using logs, not by adding print statements randomly

**Interview readiness:**
- [ ] You can solve medium-difficulty data structures problems (LeetCode, HackerRank)
- [ ] You can walk through a system design for a simple service (URL shortener, rate limiter) at a whiteboard level
- [ ] You can talk clearly about a project you've built: what you chose, why you chose it, and what you'd change

**Reality check:** The 9–12 month mark gets you *possibly* ready. 12–18 months is more honest. If you're checking most boxes above, start applying. Interviews give you calibration that self-assessment cannot.

---

## Should I specialize early?

No. Complete the full roadmap first.

**Why:**

Specialization (Phase 15) builds on Phases 1–14. A fintech engineer who doesn't understand ACID transactions, or an infrastructure engineer who doesn't understand networking, is not actually specialized — they're just narrowly experienced with gaps.

The right time to specialize is when you have a job offer in a specific domain, or when you're applying to roles in a domain you've already chosen.

**Exception:** If you already have work experience in a specific domain (e-commerce, ML infrastructure, gaming), use that context to make earlier phases concrete. Build your database project in the domain you know. Specialization as *context* is fine. Specialization as *shortcut* is not.

---

## What if I already know some of this?

Calibrate, don't assume. Work experience in a domain doesn't guarantee depth in fundamentals.

**Phase-by-phase skip criteria:**

| Phase | Skip if you can... |
|---|---|
| 1 — Networking | Explain TCP handshake, DNS resolution, HTTP status codes, and TLS off the top of your head |
| 2 — Programming | Implement a hash map with collision handling, write a BFS/DFS, explain time complexity |
| 3 — Operating Systems | Explain the process lifecycle, virtual memory, file descriptors, and blocking I/O |
| 4 — Concurrency | Explain race conditions, write a thread-safe counter, describe async/await execution |
| 5 — Databases | Design a normalized schema, write a JOIN with GROUP BY, explain B-tree indexes |
| 6 — Git & Tooling | Resolve a merge conflict, explain rebase vs merge, set up a linter |
| 7 — Architecture | Implement a layered service with DI, explain separation of concerns with examples |
| 8 — API Design | Build a versioned REST API with proper error formats and pagination |
| 9 — Security | Implement JWT auth, explain SQL injection with a real example, hash passwords correctly |
| 10 — Observability | Set up structured logging with correlation IDs, describe distributed tracing |
| 11 — Testing | Write unit, integration, and E2E tests; explain when to use each |
| 12 — Docker & CI/CD | Write a Dockerfile, set up a GitHub Actions pipeline that tests and deploys |
| 13 — Scalability | Explain consistent hashing, cache invalidation strategies, event-driven architecture |
| 14 — Cloud | Deploy a containerized service to a managed cloud platform from scratch |

Specialization is intentionally not in this table — you can't skip it because the whole point is choosing a track once you've completed everything else. There's nothing to skip; it's where you go deep.

If you can't do the thing without looking it up, don't skip the section. Familiarity and competence are different.

---

## How much time daily do I need?

Minimum 2 hours of focused, distraction-free work. 3–4 is better.

**What "focused" means here:** Writing code, debugging real problems, reading primary documentation. It does not mean watching videos passively or skimming tutorials.

**Realistic math:**
- Total roadmap: approximately 700–900 hours of material
- At 2 hours/day, 5 days/week: ~70–90 weeks (~17–21 months)
- At 3 hours/day, 6 days/week: ~40–50 weeks (~12–14 months)
- At 4+ hours/day, 7 days/week: possible in 9–12 months, but burnout risk is real

**Weekends matter.** Engineers who treat this as a hobby fit it around everything else and take 3 years. Engineers who treat it like a second job — consistent daily hours, no excuses — finish in 12–18 months.

**Quality over quantity.** Two hours of deliberate practice (write code, hit a wall, understand the wall, fix it) beats six hours of passive video watching. Track what you build, not hours logged.

---

## Do I need a CS degree?

No. But a STEM background (math, physics, engineering, any hard science) significantly reduces ramp-up time.

**What a CS degree provides:**
- Structured exposure to fundamentals (data structures, algorithms, OS, theory of computation)
- Practice thinking in systems
- A credential that removes friction in some hiring pipelines

**What this roadmap replaces:**
- The applied, practical curriculum. The degree's theoretical content doesn't directly map to backend production work.

**What neither provides:**
- Production judgment. That requires shipping real systems under pressure.

**Practical reality:** Top companies (FAANG-tier) still filter heavily on CS degrees in initial screening, though this is declining. Startups and most mid-size companies care about what you can build and how you think.

If you don't have a degree, your portfolio of real, deployed projects is your credential. Phase projects (database layer, REST API, containerized service) done well, documented clearly, and pushed to GitHub matter more than a diploma at most companies you'd actually want to work for.

---

## Can I do this while working full-time?

Yes, but it takes longer and requires discipline.

**Practical constraints:**
- Realistic pace: 1–2 hours on weekdays, 3–4 hours on weekends
- At this pace, expect 24–30 months to complete the roadmap
- Mental fatigue from a full-time job reduces effective learning hours significantly

**What works:**
- Morning sessions before work (fewer interruptions, higher focus)
- Fixed weekly schedule rather than "whenever I have time"
- Longer focused sessions on weekends rather than fragmented daily bits
- One phase at a time; don't split attention across three phases simultaneously

**What doesn't work:**
- Watching tutorials during lunch — insufficient depth and retention
- Weekend-only learning with no weekday sessions — too much context loss between sessions
- Burning out by doing 6+ hours daily on top of a demanding job

The roadmap is completable working full-time. It just takes longer. Plan accordingly rather than setting an unrealistic deadline that leads to abandoned attempts.

---

*See also: [PROGRESS.md](PROGRESS.md) for the phase-by-phase tracker, [RESOURCES.md](RESOURCES.md) for learning materials.*
