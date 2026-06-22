# 🎨 Design Patterns Quick Reference

> All 15 core Gang-of-Four patterns covered in this course. Name · category · intent · analogy · when to use. Scannable, no prose.

---

## Creational (object creation)

| Pattern | Intent (1-line) | Analogy | Use when |
|---------|-----------------|---------|----------|
| **Singleton** | One shared instance, global access | One company CEO | Exactly one instance needed (config, logger, pool) |
| **Factory Method** | Subclass decides which object to create | Hiring agency picks the worker | Creation logic varies by type; decouple from `new` |
| **Abstract Factory** | Create families of related objects | Furniture set in one style | Need consistent product families (UI themes, OS widgets) |
| **Builder** | Build complex object step by step | Ordering a custom burger | Many optional params; immutable complex objects |
| **Prototype** | Clone existing objects | Photocopying a document | Object creation is expensive; copy a template |

---

## Structural (object composition)

| Pattern | Intent (1-line) | Analogy | Use when |
|---------|-----------------|---------|----------|
| **Adapter** | Convert one interface to another | Travel plug adapter | Integrate incompatible interfaces |
| **Decorator** | Add behavior dynamically without subclassing | Adding toppings to coffee | Extend behavior flexibly at runtime |
| **Facade** | Simple interface over a complex subsystem | Hotel concierge | Hide subsystem complexity behind one entry point |
| **Proxy** | Stand-in controlling access to an object | Security guard / ID check | Lazy load, access control, caching, remote calls |
| **Composite** | Treat individual & groups uniformly (tree) | Folders containing files/folders | Part-whole hierarchies (file systems, UI trees) |

---

## Behavioral (object interaction)

| Pattern | Intent (1-line) | Analogy | Use when |
|---------|-----------------|---------|----------|
| **Observer** | Notify many objects of state changes | Newsletter subscribers | One-to-many event notification (pub/sub, listeners) |
| **Strategy** | Swap interchangeable algorithms at runtime | Choosing a route in maps app | Multiple algorithms; pick one dynamically |
| **Command** | Encapsulate a request as an object | Restaurant order ticket | Queue/undo/log operations |
| **State** | Behavior changes with internal state | Traffic light | Object behaves differently per state; avoid big if/else |
| **Iterator** | Sequentially access elements without exposing structure | TV remote channel button | Traverse a collection uniformly |

---

## Pattern Selection by Problem

| Problem | Pattern |
|---------|---------|
| Need exactly one instance | Singleton |
| Decouple object creation by type | Factory / Abstract Factory |
| Too many constructor params | Builder |
| Make incompatible APIs work together | Adapter |
| Add features without modifying class | Decorator |
| Simplify a messy subsystem | Facade |
| Control/defer access to an object | Proxy |
| Tree of nested objects | Composite |
| React to events / state changes | Observer |
| Choose algorithm at runtime | Strategy |
| Undo/redo, queued actions | Command |
| Behavior depends on mode/state | State |
| Walk a collection | Iterator |

---

## Category Cheat

| Category | Concern | Patterns |
|----------|---------|----------|
| Creational | How objects are **created** | Singleton, Factory, Abstract Factory, Builder, Prototype |
| Structural | How objects are **composed** | Adapter, Decorator, Facade, Proxy, Composite |
| Behavioral | How objects **interact/communicate** | Observer, Strategy, Command, State, Iterator |

---

## 🔗 Related
- [Design Patterns (full)](../14-lld/05-design-patterns/)
- [SOLID Principles](../14-lld/04-solid-principles/)
- [LLD vs HLD Cheatsheet](lld-vs-hld-cheatsheet.md)
