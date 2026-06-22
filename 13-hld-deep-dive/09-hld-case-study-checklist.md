# HLD Case Study Checklist

## 🧭 Overview
This is a one-stop **checklist** to run through when designing any large system — in interviews or in real design docs. Use it to make sure you haven't missed anything between requirements and wrap-up. It complements the [6-step framework](02-hld-interview-framework.md) by giving you concrete prompts at each stage.

---

## ✅ The Master Checklist

### 1. Requirements
- [ ] Functional requirements listed and scoped (MVP vs nice-to-have)?
- [ ] Non-functional requirements explicit (latency, availability, consistency, durability)?
- [ ] Read vs write ratio identified?
- [ ] Assumptions stated and confirmed with interviewer?

### 2. Scale & Estimation
- [ ] DAU/MAU and per-user activity assumed?
- [ ] QPS computed (avg **and** peak ~2–3×)?
- [ ] Storage/day and /year estimated?
- [ ] Bandwidth estimated?
- [ ] Numbers actually used to justify design choices?

### 3. API & Data Model
- [ ] Key APIs/endpoints defined?
- [ ] Core entities and high-level schema identified?
- [ ] Which datastore holds which data?
- [ ] ID generation strategy (if relevant)?

### 4. High-Level Architecture
- [ ] Client → LB/gateway → services → data stores drawn clearly?
- [ ] Cache placed where reads are heavy?
- [ ] CDN/object storage for static/media?
- [ ] Queue for async/heavy work?
- [ ] Each component's purpose justified?

### 5. Deep Dive
- [ ] The hardest 2–3 components covered in depth?
- [ ] Storage choice + schema + indexing for the key data?
- [ ] Caching strategy + invalidation?
- [ ] Sharding/partitioning key chosen (and hotspots considered)?
- [ ] Followed interviewer hints?

### 6. Scalability & Reliability
- [ ] Horizontal scaling for stateless tiers?
- [ ] Replication + failover for data tier?
- [ ] No single points of failure (LB, DB, cache all redundant)?
- [ ] Hot-key / celebrity problem addressed?
- [ ] Rate limiting / overload protection?

### 7. Consistency & Correctness
- [ ] Consistency model chosen per use case (strong vs eventual)?
- [ ] Distributed transactions handled (saga/outbox) if needed?
- [ ] Idempotency for retried operations?

### 8. Cross-Cutting Concerns
- [ ] Security: authN/authZ, TLS, input validation?
- [ ] Observability: metrics, logs, traces, alerting?
- [ ] Deployment: rollout strategy, zero-downtime migrations?
- [ ] Cost awareness?

### 9. Bottlenecks & Trade-offs
- [ ] Main bottleneck named + mitigation?
- [ ] Rejected alternatives mentioned with reasons?
- [ ] Trade-offs of each major choice articulated?

### 10. Wrap Up
- [ ] 30-second recap tying back to requirements?
- [ ] Future improvements (multi-region, ranking, analytics)?

---

## 🧭 Component Trigger Table (what to add when you see…)

| If the system is… | Reach for… |
|-------------------|------------|
| Read-heavy | Cache + read replicas + CDN |
| Write-heavy | LSM store, sharding, queue/buffer |
| Media-heavy | Object storage + CDN |
| Real-time | WebSockets + pub/sub + connection servers |
| Geo-distributed | Multi-region, GeoDNS, regional replicas |
| Spiky traffic | Queue + autoscaling + rate limiting |
| Multi-service workflow | Events + saga + idempotency |
| Search-heavy | Search index (Elasticsearch) |
| Analytics needed | Stream to warehouse/lake (not OLTP DB) |

---

## ⚖️ Quick Trade-off Reminders
| Lever | Improves | At the cost of |
|-------|----------|----------------|
| Cache | Latency, read load | Staleness, invalidation |
| Replication | Availability, read scale | Consistency (lag) |
| Sharding | Write scale, storage | Cross-shard query complexity |
| Async/queue | Responsiveness, burst absorption | Eventual processing, complexity |
| Strong consistency | Correctness | Latency, availability |

---

## 🎯 Interview Questions
1. What's the first checklist item people skip? → **Answer:** Explicit non-functional requirements and the read/write ratio.
2. How do you ensure no single points of failure? → **Answer:** Redundancy at every tier — multiple LBs, replicated DB with failover, clustered cache.
3. When should analytics live outside the OLTP database? → **Answer:** Always for heavy analytics — stream to a warehouse/lake to avoid degrading transactional performance.
4. What's a good wrap-up? → **Answer:** A concise recap mapping the design to the NFRs plus realistic future improvements.
5. How do you handle the celebrity/hot-key problem? → **Answer:** Dedicated handling — hybrid fan-out, key replication, local caching, or request coalescing.

---

## 🔗 Related Topics
- [HLD Interview Framework](02-hld-interview-framework.md)
- [Estimation & Back-of-Envelope](../11-interview-playbook/02-estimation-and-back-of-envelope.md)
- [Trade-offs Quick Reference](../12-cheatsheets/trade-offs-quick-reference.md)
- [Real-World Case Studies](../10-real-world-case-studies/)
