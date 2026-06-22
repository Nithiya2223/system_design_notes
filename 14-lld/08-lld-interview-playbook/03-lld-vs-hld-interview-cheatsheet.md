# 🆚 LLD vs HLD Interview Cheatsheet

> Fast, table-heavy reference for distinguishing and preparing for the two design rounds. (See also the [course-wide cheatsheet](../../12-cheatsheets/lld-vs-hld-cheatsheet.md).)

---

## Which Round Am I In?

| Signal | It's HLD | It's LLD |
|--------|----------|----------|
| Prompt | "Design Netflix / Uber / a chat app" | "Design a parking lot / elevator / Splitwise" |
| Whiteboard fills with | Services, DBs, queues, arrows | Classes, methods, relationships |
| They ask about | Scale, latency, consistency | Class responsibilities, patterns |
| You produce | Architecture + capacity math | Class diagram + working code |
| Often involves | Talking/diagramming | Actual coding |

---

## Core Differences

| Dimension | HLD | LLD |
|-----------|-----|-----|
| Altitude | Whole system | One component's internals |
| Goal | Scalable, available architecture | Clean, extensible code |
| Key topics | LB, sharding, caching, CAP, queues | OOP, SOLID, patterns, UML |
| Output artifact | Component/architecture diagram | Class + sequence diagrams + code |
| Failure mode | Doesn't scale / SPOFs | God classes / rigid code |

---

## Process Side-by-Side

| Step | HLD | LLD |
|------|-----|-----|
| 1 | Clarify FR + NFR | Clarify scope/features |
| 2 | Estimate scale (QPS/storage) | Identify entities (nouns) |
| 3 | High-level architecture | Attributes + relationships |
| 4 | Deep dive components | Class diagram |
| 5 | Bottlenecks & trade-offs | Apply patterns (where they fit) |
| 6 | Wrap up + improvements | Implement core methods + edges |

---

## What to Master for Each

| HLD toolkit | LLD toolkit |
|-------------|-------------|
| Scaling (H/V), load balancing | OOP pillars (encapsulation, etc.) |
| SQL/NoSQL, sharding, replication | SOLID principles |
| Caching, CDN | 15 design patterns |
| Queues, pub/sub, Kafka | UML class/sequence/state |
| CAP, consistency, consensus | Concurrency basics |
| Estimation / capacity math | Clean code & naming |

---

## Example Prompts

| HLD | LLD |
|-----|-----|
| Design a URL shortener | Design a parking lot |
| Design Twitter's feed | Design an elevator |
| Design YouTube | Design a vending machine |
| Design WhatsApp | Design Splitwise |
| Design a rate limiter (system) | Design a movie booking (classes) |

---

## Top Pitfalls per Round

| HLD pitfalls | LLD pitfalls |
|--------------|--------------|
| Skipping requirements/estimation | Coding before modeling |
| Over-engineering | God classes |
| Buzzwords w/o trade-offs | Forcing patterns |
| Ignoring SPOFs/bottlenecks | Poor encapsulation |
| Bad time management | Ignoring concurrency/edge cases |

---

## Winning Phrases

| HLD | LLD |
|-----|-----|
| "Since it's read-heavy, I'll cache + add replicas." | "This varies, so I'll put it behind a Strategy interface." |
| "The bottleneck is X; I'd mitigate with Y." | "I'll apply SRP and split this responsibility." |
| "I'll choose eventual consistency here because…" | "Two threads could race here, so I'll lock the seat." |

---

## 🔗 Related
- [How to Approach LLD Rounds](01-how-to-approach-lld-rounds.md)
- [HLD Interview Framework](../../13-hld-deep-dive/02-hld-interview-framework.md)
- [LLD vs HLD Cheatsheet (full)](../../12-cheatsheets/lld-vs-hld-cheatsheet.md)
- [LLD vs HLD (concept)](../02-lld-vs-hld.md)
