# 🏛️ System Design Course (HLD + LLD)

A complete, beginner-friendly System Design course that takes you from zero to interview-ready for top product companies (Google, Meta, Amazon, Netflix, Uber, Stripe, Airbnb, LinkedIn).

This repository covers **both** of the system design rounds you will face:

- **High-Level Design (HLD)** — architecture, scalability, databases, caching, messaging, distributed systems, and full system case studies.
- **Low-Level Design (LLD)** — OOP, SOLID principles, design patterns, UML, and object-oriented case studies with code.

---

## 🎯 Course Goals

By the end of this course you will be able to:

1. Reason about scale, latency, throughput, consistency, and availability trade-offs.
2. Design large-scale systems (URL shortener, Twitter feed, YouTube, Uber, WhatsApp, etc.) end-to-end.
3. Apply OOP and SOLID principles and recognize when to use each of the 15 core design patterns.
4. Walk into separate **HLD** and **LLD** interview rounds with a repeatable framework for each.

---

## 🧩 HLD vs LLD — Which Round Is Which?

| | High-Level Design (HLD) | Low-Level Design (LLD) |
|---|---|---|
| **Question style** | "Design YouTube / Uber / a rate limiter" | "Design a parking lot / elevator / Splitwise (classes)" |
| **Focus** | Components, data flow, scaling, storage, trade-offs | Classes, objects, relationships, patterns, clean code |
| **Output** | Architecture diagram + capacity estimates | Class diagram + working code |
| **Interview round** | "System Design" round | "Machine Coding" / "OOD" / "LLD" round |
| **Folders** | `01`–`13` | `14-lld/` |

Top companies usually run these as **separate rounds**. This course prepares you for both. See [`12-cheatsheets/lld-vs-hld-cheatsheet.md`](12-cheatsheets/lld-vs-hld-cheatsheet.md).

---

## 📋 Prerequisites

**None.** This course is beginner-friendly. You only need:

- Basic familiarity with programming (any language; code examples use **Python**).
- Curiosity about how large applications work.

---

## 🗺️ How to Use This Repo

1. Start with [`00-how-to-use/study-plan.md`](00-how-to-use/study-plan.md) — a 12-week plan.
2. Read folders **in order** (`01` → `14`). Each builds on the previous.
3. Every concept file follows the same structure: Overview → Technical Explanation → ELI5 Analogy → Diagram → Trade-offs → Real-World Examples → Interview Questions → Further Reading.
4. After each module, do the hands-on exercise in the study plan.
5. Use the [cheatsheets](12-cheatsheets/) for last-minute revision before interviews.

> **Tip:** Diagrams use [Mermaid](https://mermaid.js.org/), which renders automatically on GitHub. Just read the files on GitHub to see the visuals.

---

## 📚 Table of Contents

### Part 1 — High-Level Design (HLD)

| # | Module | Description |
|---|--------|-------------|
| 00 | [How to Use](00-how-to-use/study-plan.md) | 12-week study plan |
| 01 | [Fundamentals](01-fundamentals/) | What is system design, client-server, networks, latency vs throughput |
| 02 | [Scalability](02-scalability/) | Scaling, load balancing, auto-scaling, CAP theorem |
| 03 | [Databases](03-databases/) | SQL vs NoSQL, indexing, sharding, replication, ACID vs BASE |
| 04 | [Caching](04-caching/) | Fundamentals, strategies, eviction, CDN |
| 05 | [Messaging & Queues](05-messaging-and-queues/) | Queues, pub/sub, Kafka, event-driven architecture |
| 06 | [API Design](06-api-design/) | REST/GraphQL/gRPC, rate limiting, API gateway, pagination |
| 07 | [Distributed Systems](07-distributed-systems/) | Consistency, transactions, consensus, discovery, circuit breaker |
| 08 | [Storage](08-storage/) | Object storage, block/file/object, data lakes & warehouses |
| 09 | [Security](09-security/) | AuthN vs AuthZ, OAuth2/JWT, HTTPS/TLS, attack vectors |
| 10 | [Real-World Case Studies](10-real-world-case-studies/) | URL shortener, Twitter, YouTube, Uber, WhatsApp, Drive, notifications, rate limiter |
| 11 | [Interview Playbook](11-interview-playbook/) | Approach, estimation, mistakes, behavioral |
| 12 | [Cheatsheets](12-cheatsheets/) | Numbers, DB comparison, trade-offs, acronyms, patterns, HLD vs LLD |
| 13 | [HLD Deep Dive](13-hld-deep-dive/) | Framework, DB/cache choice, microservices, service mesh, observability, deployment |

### Part 2 — Low-Level Design (LLD)

| # | Module | Description |
|---|--------|-------------|
| 14 | [LLD](14-lld/) | OOP, SOLID, 15 design patterns, UML, 10 case studies, LLD interview playbook |

---

## ✅ Course Quality Standards

- Every concept file includes a real-world analogy, a Mermaid diagram where helpful, trade-offs, and at least 5 interview questions.
- HLD case studies include explicit capacity-estimation math.
- LLD files include runnable **Python** code and class diagrams.
- Cheatsheets are table-heavy and scannable.

---

## 🚀 Quick Start

```bash
git clone <this-repo-url>
cd system_design_notes
# Open any .md file on GitHub to see rendered Mermaid diagrams
```

Happy designing! 🎉
