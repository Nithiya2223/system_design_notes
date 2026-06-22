# How to Approach LLD / Machine Coding Rounds

## 🧭 Overview
The LLD round (a.k.a. "Machine Coding," "Object-Oriented Design," or "OOD") asks you to design and often **code** a system's classes within ~45–60 minutes — e.g., "design a parking lot." Unlike the HLD round (architecture/scale), it evaluates clean OOP modeling, SOLID adherence, appropriate design patterns, and working code. This is your repeatable framework for it.

---

## 🪜 The 6-Step LLD Framework

### 1. Clarify Requirements & Scope (~5 min)
Ask what's in/out of scope. Pin down the **must-have** features and explicitly defer the rest. "Should the parking lot support multiple levels? Payment? Reservations?" Agree on a focused MVP.

### 2. Identify Core Entities (nouns) (~5 min)
Extract the key objects from the problem: parking lot → `ParkingLot`, `Level`, `ParkingSpot`, `Vehicle`, `Ticket`. Assign each a **single responsibility** (SRP).

### 3. Define Relationships & Attributes (~5 min)
For each entity, list attributes and how entities relate (has-a/is-a, multiplicity). `ParkingLot` *has* `Level`s; `Vehicle` *is-a* base type with subtypes.

### 4. Draw the Class Diagram (~10 min)
Sketch classes, key methods, and relationships. This is your blueprint and communicates your design clearly. Identify where **abstractions/interfaces** belong.

### 5. Apply Design Patterns Where They Fit (~5 min)
Name patterns that genuinely solve a problem: Strategy for pricing, Factory for object creation, State for lifecycles, Observer for notifications. **Don't force patterns.**

### 6. Implement Key Methods + Edge Cases (~15–20 min)
Write clean, working code for the **core flows** (e.g., park/unpark). Handle edge cases (full lot, invalid input) and mention **concurrency** (two cars, last spot). You won't code everything — prioritize the important methods.

---

## 🧰 What Interviewers Score
- Correct entity modeling & single responsibilities.
- Extensibility (Open/Closed) — can you add a feature without rewriting?
- Appropriate (not forced) pattern usage.
- Clean, compiling/working code with good names.
- Edge cases and concurrency awareness.
- Communication — narrate your reasoning.

---

## 🗣️ Communication Tips
- Think out loud; state assumptions.
- Start with the diagram before coding — agree on structure first.
- Code incrementally; get the core flow working, then extend.
- When you spot a pattern, say *why* it fits.

---

## ⚖️ Do / Don't

| Do | Don't |
|----|-------|
| Clarify scope first | Start coding immediately |
| Model entities → diagram → code | Jump to methods before structure |
| Use interfaces for varying behavior | Hardcode behavior in big if/elif |
| Apply patterns when they fit | Force patterns to look clever |
| Handle edge cases & concurrency | Only code the happy path |
| Keep classes single-responsibility | Build a God class |

---

## 📋 Quick Pre-Submit Checklist
- [ ] Core entities have single responsibilities?
- [ ] Behavior that varies is behind an interface/strategy?
- [ ] No God class?
- [ ] Patterns justified, not forced?
- [ ] Core methods implemented and working?
- [ ] Edge cases + concurrency mentioned?
- [ ] Code is readable with clear names?

---

## 🎯 Interview Questions (Meta)
1. What's the first step in an LLD round? → **Answer:** Clarify requirements and scope, then identify core entities — never start coding immediately.
2. How do you decide which patterns to use? → **Answer:** Only where they genuinely solve a recurring problem (Strategy for swappable algorithms, State for lifecycles); avoid forcing them.
3. How do you handle running low on time? → **Answer:** Prioritize a working core flow and a clean diagram; stub/describe the rest and note edge cases.
4. [Amazon] How do you show extensibility? → **Answer:** Program to interfaces so new variants (fee types, payment methods) are added as classes without modifying existing code.
5. [Google] Why start with a class diagram? → **Answer:** It aligns you and the interviewer on structure before coding, reducing rework.

---

## 🔗 Related Topics
- [Common LLD Mistakes](02-common-mistakes.md)
- [LLD vs HLD Interview Cheatsheet](03-lld-vs-hld-interview-cheatsheet.md)
- [SOLID Principles](../04-solid-principles/01-single-responsibility.md)
- [Parking Lot Case Study](../07-lld-case-studies/01-parking-lot.md)
