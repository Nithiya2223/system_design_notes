# 🔤 System Design Acronyms

> Quick lookup of acronyms used across this course and in interviews.

---

## Core Concepts

| Acronym | Expansion | Meaning (1-liner) |
|---------|-----------|-------------------|
| HLD | High-Level Design | System architecture & components |
| LLD | Low-Level Design | Class/object design & code |
| CAP | Consistency, Availability, Partition tolerance | Pick 2 during a partition |
| PACELC | Partition→A/C, Else→Latency/Consistency | Extension of CAP |
| ACID | Atomicity, Consistency, Isolation, Durability | Strong DB transaction guarantees |
| BASE | Basically Available, Soft state, Eventually consistent | Relaxed, scalable guarantees |
| SPOF | Single Point of Failure | Component whose failure kills the system |
| NFR | Non-Functional Requirement | Latency/availability/scalability etc. |

---

## Performance & Scale

| Acronym | Expansion | Meaning |
|---------|-----------|---------|
| QPS | Queries Per Second | Request throughput |
| RPS | Requests Per Second | Same idea |
| TPS | Transactions Per Second | DB/transaction throughput |
| p50/p95/p99 | Percentile latencies | Median / tail latency |
| RTT | Round Trip Time | Network there-and-back time |
| SLA | Service Level Agreement | Promised reliability (contract) |
| SLO | Service Level Objective | Internal target |
| SLI | Service Level Indicator | Measured metric |
| TTL | Time To Live | How long data/cache stays valid |
| MAU/DAU | Monthly/Daily Active Users | Scale metrics |

---

## Storage & Data

| Acronym | Expansion | Meaning |
|---------|-----------|---------|
| OLTP | Online Transaction Processing | Operational small reads/writes |
| OLAP | Online Analytical Processing | Big analytical scans |
| ETL/ELT | Extract Transform Load (/ Load Transform) | Data pipeline patterns |
| CDC | Change Data Capture | Stream DB changes as events |
| WAL | Write-Ahead Log | Durability/replication log |
| CRDT | Conflict-free Replicated Data Type | Auto-merging data structure |
| LSM | Log-Structured Merge tree | Write-optimized storage |
| LRU/LFU | Least Recently/Frequently Used | Cache eviction policies |

---

## Networking & API

| Acronym | Expansion | Meaning |
|---------|-----------|---------|
| DNS | Domain Name System | Name → IP resolution |
| CDN | Content Delivery Network | Edge caching network |
| TCP/UDP | Transmission Control / User Datagram Protocol | Reliable / fast transport |
| TLS/SSL | Transport Layer Security | Encryption in transit |
| HTTP(S) | HyperText Transfer Protocol (Secure) | Web protocol |
| REST | Representational State Transfer | Resource-based API style |
| gRPC | gRPC Remote Procedure Call | Binary RPC over HTTP/2 |
| API | Application Programming Interface | Service contract |
| LB | Load Balancer | Distributes traffic |
| WS | WebSocket | Persistent bidirectional connection |

---

## Distributed Systems & Reliability

| Acronym | Expansion | Meaning |
|---------|-----------|---------|
| 2PC/3PC | Two/Three-Phase Commit | Distributed atomic commit |
| BFT | Byzantine Fault Tolerance | Tolerates malicious nodes |
| FLP | Fischer-Lynch-Paterson | Consensus impossibility result |
| DLQ | Dead-Letter Queue | Store for failed messages |
| HA | High Availability | Minimal downtime design |
| DR | Disaster Recovery | Recovery from major failures |
| RPO/RTO | Recovery Point/Time Objective | Data loss / downtime tolerance |

---

## Security

| Acronym | Expansion | Meaning |
|---------|-----------|---------|
| AuthN | Authentication | Who you are |
| AuthZ | Authorization | What you can do |
| MFA | Multi-Factor Authentication | Multiple identity proofs |
| JWT | JSON Web Token | Signed claims token |
| OIDC | OpenID Connect | Auth layer on OAuth2 |
| RBAC/ABAC | Role/Attribute-Based Access Control | Permission models |
| XSS/CSRF | Cross-Site Scripting / Request Forgery | Web attacks |
| SSRF | Server-Side Request Forgery | Server tricked into requests |
| DDoS | Distributed Denial of Service | Traffic-flood attack |
| WAF | Web Application Firewall | Filters malicious requests |
| mTLS | Mutual TLS | Both sides present certs |

---

## Architecture & Ops

| Acronym | Expansion | Meaning |
|---------|-----------|---------|
| BFF | Backend For Frontend | Client-specific gateway |
| CQRS | Command Query Responsibility Segregation | Split read/write models |
| EDA | Event-Driven Architecture | Communicate via events |
| CI/CD | Continuous Integration / Delivery | Automated build & deploy |
| IaC | Infrastructure as Code | Provision via code |
| SRE | Site Reliability Engineering | Ops via engineering |
| K8s | Kubernetes | Container orchestration |

---

## 🔗 Related
- [Trade-offs Quick Reference](trade-offs-quick-reference.md)
- [LLD vs HLD Cheatsheet](lld-vs-hld-cheatsheet.md)
