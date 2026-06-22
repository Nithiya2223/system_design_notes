# How to Approach System Design Interviews

## 🧭 Overview
The system design interview evaluates how you think about building large-scale systems: requirements gathering, trade-off reasoning, and communication — not whether you memorized a "right answer." This guide covers the overall mindset, what interviewers actually score, and — crucially — how **top companies run separate HLD and LLD rounds** that require different preparation.

---

## 🧠 What the Interviewer Is Really Evaluating
- **Structured thinking:** do you drive the conversation with a clear method?
- **Requirements & scoping:** do you clarify before designing?
- **Trade-off reasoning:** can you justify *why* X over Y (not just name technologies)?
- **Communication & collaboration:** do you think out loud and respond to hints?
- **Depth + breadth:** can you go deep on a component yet keep the whole picture?
- **Handling ambiguity:** the problem is intentionally open-ended.

> It's a conversation, not a monologue. Treat the interviewer as a collaborator.

---

## 🧩 HLD vs LLD — Two Separate Rounds at Top Companies

Most top product companies (Google, Meta, Amazon, etc.) run **two distinct design rounds**. Confusing them is a common, costly mistake.

| | **HLD Round** ("System Design") | **LLD Round** ("Machine Coding" / "OOD") |
|---|---|---|
| **Prompt** | "Design YouTube / Uber / a rate limiter" | "Design a parking lot / elevator / Splitwise" |
| **Scope** | Whole-system architecture | Classes within one component |
| **Output** | Architecture diagram, data flow, capacity estimates, trade-offs | Class diagram, clean OOP code, design patterns |
| **Topics** | Scaling, DB choice, caching, queues, sharding, CAP | OOP, SOLID, design patterns, UML |
| **What they score** | Scalability, trade-offs, bottlenecks | Clean abstractions, extensibility, correct code |
| **Time** | ~45 min, mostly whiteboard/talk | ~45–60 min, often actual coding |

### How to Prepare Differently
- **For HLD:** master the building blocks (this course's folders 01–13), practice the [6-step framework](../13-hld-deep-dive/02-hld-interview-framework.md), and drill capacity estimation. Practice case studies out loud.
- **For LLD:** master OOP + SOLID + the 15 design patterns (folder 14), and practice translating a problem into classes, relationships, and working code under time pressure.

Some companies blur the line (e.g., a startup may do one combined round), but assume **separate rounds** unless told otherwise, and ask the recruiter which round it is.

---

## 🪜 The General Flow (HLD)
1. **Clarify requirements** (functional + non-functional). ~5 min.
2. **Estimate scale** (users, QPS, storage). ~5 min.
3. **High-level architecture** (boxes & arrows). ~10 min.
4. **Deep dive** on 2–3 hard components. ~10 min.
5. **Bottlenecks & trade-offs.** ~5 min.
6. **Wrap up + future improvements.** ~5 min.

(Full detail in the [HLD Interview Framework](../13-hld-deep-dive/02-hld-interview-framework.md).)

---

## 🗣️ Communication Tips
- **Narrate your reasoning** — silence reads as being stuck.
- **State assumptions explicitly** ("I'll assume 100M DAU").
- **Lead the conversation**, but pause to check direction.
- **Take hints gracefully** — they're steering you toward what they want to probe.
- **Manage time** — don't spend 20 minutes on requirements.

---

## ⚖️ Mindset Trade-offs
| Do | Instead of |
|----|-----------|
| Clarify scope first | Jumping straight to a database |
| Justify choices with trade-offs | Name-dropping tech buzzwords |
| Start simple, then scale | Over-engineering from minute one |
| Admit unknowns and reason | Bluffing confidently |

---

## 🎯 Interview Questions (Meta-Level)
1. [General] How do you decide what to deep-dive on? → **Answer:** Pick the components that are hardest, most scale-critical, or where the interviewer hints; cover the riskiest part thoroughly.
2. [Google] How do you handle an intentionally vague prompt? → **Answer:** Drive clarification — define scope, users, and non-functional targets before designing.
3. [Amazon] What's the difference between the HLD and LLD rounds and how do you prepare for each? → **Answer:** HLD = architecture/scaling/trade-offs; LLD = OOP/patterns/code. Prepare with building blocks + estimation for HLD, and OOP/SOLID/patterns + timed coding for LLD.
4. [Meta] How do you respond when the interviewer pushes back on your choice? → **Answer:** Re-examine the trade-off openly, acknowledge their point, and adjust or defend with reasoning — collaboration over ego.
5. [Netflix] How do you keep both breadth and depth in 45 minutes? → **Answer:** Get a complete high-level picture first, then deep-dive selectively while time-boxing each phase.

---

## 📚 Further Reading
- *System Design Interview* Vol 1 & 2 — Alex Xu
- "Grokking the System Design Interview"

---

## 🔗 Related Topics
- [HLD Interview Framework](../13-hld-deep-dive/02-hld-interview-framework.md)
- [Estimation and Back-of-Envelope](02-estimation-and-back-of-envelope.md)
- [Common Mistakes](03-common-mistakes.md)
- [LLD Interview Playbook](../14-lld/08-lld-interview-playbook/01-how-to-approach-lld-rounds.md)
- [LLD vs HLD Cheatsheet](../12-cheatsheets/lld-vs-hld-cheatsheet.md)
