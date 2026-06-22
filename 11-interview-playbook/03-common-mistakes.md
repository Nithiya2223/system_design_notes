# Common System Design Interview Mistakes

## 🧭 Overview
Most candidates fail design interviews not from lack of knowledge but from avoidable process and communication mistakes. This is a checklist of the **most common mistakes** across both **HLD** and **LLD** rounds, each paired with **what to do instead**. Review it before every interview.

---

## 🏗️ HLD Mistakes

### 1. Jumping straight to a solution
❌ Drawing databases before understanding the problem.
✅ Spend the first ~5 minutes clarifying functional + non-functional requirements.

### 2. Skipping requirements clarification
❌ Assuming scope and building the wrong thing.
✅ Ask: who are the users? what scale? what's in/out of scope? what matters — latency, consistency, availability?

### 3. Ignoring scale / skipping estimation
❌ Designing without knowing if it's 1k or 1B users.
✅ Do back-of-the-envelope math (QPS, storage, bandwidth) to right-size the design.

### 4. Over-engineering from the start
❌ Adding Kafka, sharding, and microservices for a 1,000-user app.
✅ Start with the simplest design that meets requirements, then scale where needed.

### 5. Name-dropping technologies without justification
❌ "I'll use Cassandra" with no reason.
✅ Justify every choice with a trade-off tied to the requirements.

### 6. Not identifying bottlenecks
❌ Presenting a design as if it has no weak points.
✅ Proactively name the bottleneck (e.g., the database write path) and address it.

### 7. Forgetting non-functional requirements
❌ Only handling features, ignoring availability/latency/consistency.
✅ Explicitly design for the NFRs you gathered.

### 8. Single points of failure
❌ One load balancer, one database, no redundancy.
✅ Add redundancy, replication, and failover; assume components fail.

### 9. Ignoring the read/write ratio
❌ Treating a read-heavy system like a balanced one.
✅ Identify the ratio and optimize accordingly (caching/replicas for reads).

### 10. Poor time management
❌ 20 minutes on requirements, no time for deep dive.
✅ Time-box each phase; keep the whole picture moving.

### 11. Going silent
❌ Thinking quietly while the interviewer guesses if you're stuck.
✅ Narrate your reasoning continuously.

### 12. Not handling data consistency explicitly
❌ Hand-waving "the database handles it."
✅ State your consistency model and why (strong vs eventual) per use case.

---

## 🧩 LLD Mistakes

### 13. Creating "God classes"
❌ One class that does everything.
✅ Apply the Single Responsibility Principle — split responsibilities.

### 14. Ignoring SOLID / extensibility
❌ Hardcoding behavior so new requirements force rewrites.
✅ Use abstractions (interfaces) and patterns (Strategy/Factory) for extension without modification.

### 15. Forcing design patterns where they don't fit
❌ Cramming Singleton/Factory everywhere to look clever.
✅ Use a pattern only when it genuinely solves the problem; simplest correct design wins.

### 16. Jumping to code before modeling
❌ Writing methods before identifying entities/relationships.
✅ Identify core entities (nouns), responsibilities, and relationships → then a class diagram → then code.

### 17. Poor encapsulation
❌ Public mutable fields, leaking internal state.
✅ Keep state private; expose behavior via methods.

### 18. Ignoring edge cases & concurrency
❌ Designing only the happy path.
✅ Discuss invalid inputs, concurrent access (e.g., two cars taking the last parking spot), and thread safety.

---

## ⚖️ Quick Do / Don't Table

| Don't | Do |
|-------|-----|
| Start designing immediately | Clarify requirements first |
| Skip the math | Estimate scale |
| Over-engineer | Start simple, scale deliberately |
| List buzzwords | Justify with trade-offs |
| Claim no weaknesses | Name bottlenecks proactively |
| Build God classes (LLD) | Apply SRP/SOLID |
| Code before modeling (LLD) | Entities → diagram → code |
| Go silent | Think out loud |

---

## 🎯 Interview Questions (Reflection)
1. What are the first two things you should do in any HLD interview? → **Answer:** Clarify requirements (functional + non-functional) and estimate scale.
2. How do you avoid over-engineering? → **Answer:** Build the simplest design meeting requirements, then add complexity only where scale/NFRs demand.
3. What's the most common LLD mistake and its fix? → **Answer:** God classes; fix by applying the Single Responsibility Principle and proper abstractions.
4. Why is going silent costly? → **Answer:** Interviewers score reasoning and communication; silence hides your thinking and reads as being stuck.
5. How should you respond to interviewer pushback? → **Answer:** Re-evaluate openly, weigh the trade-off, and adjust or defend with reasoning — collaboratively.

---

## 📚 Further Reading
- *System Design Interview* — Alex Xu (process chapters)
- "Tech Interview Handbook" — system design tips

---

## 🔗 Related Topics
- [How to Approach SD Interviews](01-how-to-approach-sd-interviews.md)
- [HLD Interview Framework](../13-hld-deep-dive/02-hld-interview-framework.md)
- [LLD Common Mistakes](../14-lld/08-lld-interview-playbook/02-common-mistakes.md)
