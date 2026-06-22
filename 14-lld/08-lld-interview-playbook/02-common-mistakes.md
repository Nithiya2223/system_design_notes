# Common LLD Interview Mistakes

## 🧭 Overview
The LLD round trips up candidates with predictable mistakes — usually around process, OOP fundamentals, and pattern misuse. This checklist pairs each common mistake with **what to do instead**. Review it before any machine-coding/OOD interview.

---

## 🧱 Modeling & Process Mistakes

### 1. Coding before modeling
❌ Writing methods before identifying entities and relationships.
✅ Clarify scope → identify entities → draw the class diagram → then code.

### 2. Skipping requirements clarification
❌ Building the wrong scope from assumptions.
✅ Confirm must-have features and explicitly defer the rest.

### 3. The God class
❌ One class (`Manager`, `System`) doing everything.
✅ Apply SRP — split distinct responsibilities into focused classes.

### 4. Poor naming
❌ `data`, `obj`, `manager2`, `doStuff()`.
✅ Intention-revealing names (`ParkingSpot`, `calculateFee()`).

### 5. Anemic or over-fragmented models
❌ Classes with only getters/setters and no behavior, or splitting trivially into dozens of tiny classes.
✅ Put behavior with data (tell, don't ask); keep cohesion sensible.

---

## 🧩 OOP & SOLID Mistakes

### 6. Public mutable state (poor encapsulation)
❌ Exposing fields so any code can corrupt invariants.
✅ Keep state private; expose validated behavior.

### 7. Inheritance for code reuse (not "is-a")
❌ Subclassing just to reuse methods.
✅ Use composition for "has-a/uses-a"; inherit only for genuine "is-a."

### 8. Violating Open/Closed with if/elif chains
❌ A growing conditional on a type you must edit for each new case.
✅ Program to an interface; add new behavior as new classes (Strategy/Factory).

### 9. LSP violations
❌ A subclass that throws "not supported" or breaks the parent's contract.
✅ Ensure subtypes are truly substitutable; otherwise restructure (composition/interfaces).

### 10. Fat interfaces (ISP violation)
❌ One huge interface forcing irrelevant method stubs.
✅ Split into small, role-specific interfaces.

---

## 🎨 Pattern & Implementation Mistakes

### 11. Forcing design patterns
❌ Cramming Singleton/Factory everywhere to look clever.
✅ Use a pattern only when it genuinely solves the problem; simplest correct design wins.

### 12. Wrong pattern for the job
❌ Using inheritance where Decorator/Strategy fits, or Singleton as a global dumping ground.
✅ Match the pattern to the intent (varying behavior → Strategy; lifecycle → State).

### 13. Ignoring concurrency
❌ Designing only the happy single-threaded path.
✅ Discuss shared-state races (two cars → last spot; double-booking) and use locks/atomic ops.

### 14. Ignoring edge cases
❌ No handling for invalid input, empty/full states, or failures.
✅ Validate inputs and handle boundary conditions explicitly.

### 15. Not making code runnable/testable
❌ Pseudocode that wouldn't compile; no clear units.
✅ Write clean, working code with small, testable methods.

### 16. Poor time management
❌ Perfecting one class while the core flow is unfinished.
✅ Get the core flow working end-to-end first, then refine.

---

## ⚖️ Quick Do / Don't

| Don't | Do |
|-------|-----|
| Code before modeling | Entities → diagram → code |
| God classes | SRP / focused classes |
| Inherit for reuse | Compose for has-a |
| if/elif on type | Interface + new classes (OCP) |
| Force patterns | Use patterns only when they fit |
| Ignore concurrency/edges | Handle locks, races, invalid input |

---

## 🎯 Interview Questions (Reflection)
1. What's the most common LLD mistake? → **Answer:** Coding before modeling (and building God classes); fix by modeling entities and responsibilities first.
2. How do you avoid forcing patterns? → **Answer:** Apply a pattern only when it solves a real, recurring problem; otherwise keep it simple.
3. How do you demonstrate concurrency awareness? → **Answer:** Identify shared-state races (last parking spot, seat booking) and use locks/atomic operations.
4. Why is composition often safer than inheritance? → **Answer:** It avoids fragile, rigid hierarchies and is more flexible; inherit only for true "is-a."
5. [Amazon] How would you refactor a God class live? → **Answer:** Identify distinct responsibilities/actors and extract focused, single-responsibility classes.

---

## 🔗 Related Topics
- [How to Approach LLD Rounds](01-how-to-approach-lld-rounds.md)
- [SOLID Principles](../04-solid-principles/01-single-responsibility.md)
- [HLD Common Mistakes](../../11-interview-playbook/03-common-mistakes.md)
