# 📅 12-Week System Design Study Plan

This plan takes you from **zero** to **interview-ready** for both HLD and LLD rounds. Spend ~6–8 hours per week. Each week lists **files to read**, a **hands-on exercise**, and a **self-check question**.

> **How to use:** Don't just read — draw the diagrams yourself and explain each concept out loud as if to an interviewer. Teaching forces understanding.

---

## Week 1 — Fundamentals + Scalability

**Read:**
- `01-fundamentals/01-what-is-system-design.md`
- `01-fundamentals/02-client-server-model.md`
- `01-fundamentals/03-network-basics.md`
- `01-fundamentals/04-latency-vs-throughput.md`
- `02-scalability/01-horizontal-vs-vertical-scaling.md`
- `02-scalability/02-load-balancing.md`
- `02-scalability/03-auto-scaling.md`
- `02-scalability/04-cap-theorem.md`

**Hands-on exercise:** Draw the request path for `https://example.com/home` from browser to server and back, labeling DNS, load balancer, app server, and database.

**Self-check:** When would you scale vertically instead of horizontally, and why?

---

## Week 2 — Databases

**Read:**
- `03-databases/01-relational-vs-nosql.md`
- `03-databases/02-indexing.md`
- `03-databases/03-sharding.md`
- `03-databases/04-replication.md`
- `03-databases/05-acid-vs-base.md`
- `03-databases/06-database-selection-guide.md`

**Hands-on exercise:** For a hypothetical e-commerce app (users, products, orders), decide which tables go to SQL vs NoSQL and design a sharding key for the orders table.

**Self-check:** Explain the difference between ACID and BASE and give one system that prefers each.

---

## Week 3 — Caching + CDN

**Read:**
- `04-caching/01-caching-fundamentals.md`
- `04-caching/02-cache-strategies.md`
- `04-caching/03-eviction-policies.md`
- `04-caching/04-cdn.md`

**Hands-on exercise:** Pick cache-aside vs write-through for a product-detail page and a shopping-cart, and justify each choice.

**Self-check:** What is a cache stampede and how do you prevent it?

---

## Week 4 — Messaging + API Design

**Read:**
- `05-messaging-and-queues/01-message-queues.md`
- `05-messaging-and-queues/02-pub-sub.md`
- `05-messaging-and-queues/03-kafka-deep-dive.md`
- `05-messaging-and-queues/04-event-driven-architecture.md`
- `06-api-design/01-rest-vs-graphql-vs-grpc.md`
- `06-api-design/02-rate-limiting.md`
- `06-api-design/03-api-gateway.md`
- `06-api-design/04-pagination.md`

**Hands-on exercise:** Design the event flow for "user places order → inventory updated → email sent" using a message queue.

**Self-check:** When would you choose gRPC over REST?

---

## Week 5 — Distributed Systems

**Read:**
- `07-distributed-systems/01-consistency-models.md`
- `07-distributed-systems/02-distributed-transactions.md`
- `07-distributed-systems/03-consensus-algorithms.md`
- `07-distributed-systems/04-service-discovery.md`
- `07-distributed-systems/05-circuit-breaker-pattern.md`

**Hands-on exercise:** Sketch the Saga pattern for a travel-booking flow (flight + hotel + car) including compensating transactions.

**Self-check:** Why can't you have strong consistency, availability, and partition tolerance all at once?

---

## Week 6 — Storage + Security

**Read:**
- `08-storage/01-object-storage.md`
- `08-storage/02-block-vs-file-vs-object.md`
- `08-storage/03-data-lakes-and-warehouses.md`
- `09-security/01-authentication-vs-authorization.md`
- `09-security/02-oauth2-and-jwt.md`
- `09-security/03-https-and-tls.md`
- `09-security/04-common-attack-vectors.md`

**Hands-on exercise:** Design the auth flow for a mobile app using OAuth2 + JWT, including token refresh.

**Self-check:** When would you use object storage instead of a block device?

---

## Week 7 — HLD Case Studies (pick 4)

**Read (choose any 4):**
- `10-real-world-case-studies/01-design-url-shortener.md`
- `10-real-world-case-studies/02-design-twitter-feed.md`
- `10-real-world-case-studies/03-design-youtube.md`
- `10-real-world-case-studies/04-design-uber.md`
- `10-real-world-case-studies/05-design-whatsapp.md`
- `10-real-world-case-studies/06-design-google-drive.md`
- `10-real-world-case-studies/07-design-notification-system.md`
- `10-real-world-case-studies/08-design-rate-limiter.md`

**Hands-on exercise:** Take one case study and redo the capacity estimation from scratch on paper without looking.

**Self-check:** For your chosen system, what is the single biggest bottleneck and how do you fix it?

---

## Week 8 — HLD Interview Playbook + Mock HLD Sessions

**Read:**
- `11-interview-playbook/01-how-to-approach-sd-interviews.md`
- `11-interview-playbook/02-estimation-and-back-of-envelope.md`
- `11-interview-playbook/03-common-mistakes.md`
- `13-hld-deep-dive/02-hld-interview-framework.md`
- `13-hld-deep-dive/09-hld-case-study-checklist.md`

**Hands-on exercise:** Do a 45-minute mock interview with a friend: design Instagram. Use the 6-step framework and stay on time.

**Self-check:** Can you complete requirements + estimation + architecture in under 20 minutes?

---

## Week 9 — OOP + SOLID Principles

**Read:**
- `14-lld/01-what-is-lld.md`
- `14-lld/02-lld-vs-hld.md`
- `14-lld/03-oop-fundamentals/` (all 5 files)
- `14-lld/04-solid-principles/` (all 5 files)

**Hands-on exercise:** Refactor a "God class" (one class doing everything) into multiple classes following the Single Responsibility Principle.

**Self-check:** Give a code example that violates the Open/Closed Principle and fix it.

---

## Week 10 — Design Patterns: Creational + Structural

**Read:**
- `14-lld/05-design-patterns/creational/` (all 5 files)
- `14-lld/05-design-patterns/structural/` (all 5 files)

**Hands-on exercise:** Implement a notification system using the Factory pattern (Email, SMS, Push) in Python.

**Self-check:** What is the difference between the Factory and Abstract Factory patterns?

---

## Week 11 — Design Patterns: Behavioral + UML

**Read:**
- `14-lld/05-design-patterns/behavioral/` (all 5 files)
- `14-lld/06-uml-and-diagrams/` (all 3 files)

**Hands-on exercise:** Model a vending machine's states (idle, has-money, dispensing) using the State pattern and draw its state-machine diagram.

**Self-check:** When would you choose Strategy over inheritance?

---

## Week 12 — LLD Case Studies + Mock LLD Interview

**Read:**
- `14-lld/07-lld-case-studies/` (pick 4, e.g. parking lot, elevator, Splitwise, movie booking)
- `14-lld/08-lld-interview-playbook/` (all 3 files)

**Hands-on exercise:** In 45 minutes, design a parking-lot system: class diagram + core Python classes for entry/exit.

**Self-check:** Can you produce a clean class diagram and identify which design patterns apply within 45 minutes?

---

## 🏁 After 12 Weeks

- Revisit the [cheatsheets](../12-cheatsheets/) weekly.
- Do 1 mock HLD + 1 mock LLD interview per week until your real interviews.
- Keep a personal "mistakes log" — review it before every interview.

Good luck! 🚀
