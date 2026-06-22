# 🆚 LLD vs HLD Cheatsheet

> Side-by-side comparison of High-Level Design and Low-Level Design — what each covers, what interviewers look for, how to prepare, and example questions.

---

## At a Glance

| Aspect | HLD (High-Level Design) | LLD (Low-Level Design) |
|--------|-------------------------|------------------------|
| Also called | System Design | Object-Oriented Design / Machine Coding |
| Altitude | Whole system ("boxes & arrows") | Inside one component (classes & methods) |
| Question type | "Design YouTube / Uber" | "Design a parking lot / elevator" |
| Primary output | Architecture diagram + capacity estimates | Class diagram + working code |
| Core skills | Scaling, trade-offs, data flow | OOP, SOLID, design patterns |
| Granularity | Services, DBs, caches, queues | Classes, interfaces, relationships |
| Time | ~45 min, mostly discussion | ~45–60 min, often live coding |

---

## What Each Covers

| HLD topics | LLD topics |
|------------|------------|
| Load balancing & scaling | Classes & objects |
| Database choice & sharding | Encapsulation, inheritance, polymorphism |
| Caching & CDN | SOLID principles |
| Messaging & queues | Creational/structural/behavioral patterns |
| Consistency & CAP | UML class/sequence/state diagrams |
| API design | Thread safety / concurrency in code |
| Capacity estimation | Clean, extensible code structure |

---

## What Interviewers Look For

| HLD round | LLD round |
|-----------|-----------|
| Did you clarify requirements & scale? | Did you identify the right entities? |
| Are trade-offs justified (not buzzwords)? | Are responsibilities cleanly separated (SRP)? |
| Did you find bottlenecks/SPOFs? | Is it extensible without modification (OCP)? |
| Right DB/cache/queue choices? | Are patterns used appropriately (not forced)? |
| Capacity math sane? | Is the code clean, correct, and runnable? |
| Clear communication & structure? | Edge cases & concurrency handled? |

---

## How to Prepare

| HLD prep | LLD prep |
|----------|----------|
| Master building blocks (folders 01–13) | Master OOP + SOLID (folder 14) |
| Drill back-of-envelope estimation | Memorize 15 design patterns + when to use |
| Practice case studies out loud | Practice modeling problems into classes |
| Use the 6-step framework | Practice timed coding (parking lot, etc.) |
| Learn real architectures (eng blogs) | Draw class + sequence diagrams fast |

---

## Process / Framework

| HLD steps | LLD steps |
|-----------|-----------|
| 1. Clarify requirements (FR + NFR) | 1. Clarify requirements & scope |
| 2. Estimate scale (QPS, storage) | 2. Identify core entities (nouns) |
| 3. High-level architecture | 3. Define attributes & relationships |
| 4. Deep dive on components | 4. Draw class diagram |
| 5. Bottlenecks & trade-offs | 5. Apply patterns where they fit |
| 6. Wrap up / improvements | 6. Implement key methods + edge cases |

---

## Example Questions

| HLD examples | LLD examples |
|--------------|--------------|
| Design a URL shortener | Design a parking lot |
| Design Twitter's feed | Design an elevator system |
| Design YouTube | Design a vending machine |
| Design Uber | Design Splitwise |
| Design WhatsApp | Design a chess game |
| Design a rate limiter (system) | Design a rate limiter (classes) |
| Design Google Drive | Design a movie-ticket booking |

---

## Common Pitfalls

| HLD pitfall | LLD pitfall |
|-------------|-------------|
| Skipping requirements/estimation | Jumping to code before modeling |
| Over-engineering | God classes (no SRP) |
| Buzzwords without trade-offs | Forcing unnecessary patterns |
| Ignoring bottlenecks/SPOFs | Poor encapsulation |
| Poor time management | Ignoring edge cases/concurrency |

---

## 🔗 Related
- [How to Approach SD (HLD) Interviews](../11-interview-playbook/01-how-to-approach-sd-interviews.md)
- [HLD Interview Framework](../13-hld-deep-dive/02-hld-interview-framework.md)
- [How to Approach LLD Rounds](../14-lld/08-lld-interview-playbook/01-how-to-approach-lld-rounds.md)
- [Design Patterns Quick Reference](design-patterns-quick-reference.md)
