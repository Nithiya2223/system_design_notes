# ⚖️ Trade-offs Quick Reference

> Scannable "X vs Y" table for the most common system-design decisions. Each row: when to lean each way.

---

## Core Architectural Trade-offs

| Decision | Option A | Option B | Choose A when | Choose B when |
|----------|----------|----------|---------------|---------------|
| Scaling | Vertical (scale up) | Horizontal (scale out) | Simple, moderate load | Large/elastic load, HA |
| Consistency | Strong | Eventual | Money, inventory, locks | Feeds, likes, caches |
| SQL vs NoSQL | SQL | NoSQL | Transactions, joins | Scale, flexible schema |
| Sync vs Async | Synchronous | Asynchronous | Need immediate result | Background/heavy work |
| Monolith vs Microservices | Monolith | Microservices | Small team, early stage | Large org, independent scaling |
| Stateful vs Stateless | Stateful | Stateless | (rarely) local perf | Almost always (scaling) |
| Latency vs Throughput | Optimize latency | Optimize throughput | Interactive UX | Batch/bulk processing |
| Normalization | Normalized | Denormalized | Write integrity, less duplication | Read speed, fewer joins |

---

## Caching

| Decision | Lean A | Lean B |
|----------|--------|--------|
| Strategy | Cache-aside (default) | Write-through (freshness) |
| Write-heavy | Write-back (fast, risky) | Write-through (safe) |
| Eviction | LRU (recency) | LFU (popularity) |
| Freshness | Short TTL | Long TTL + invalidation |

---

## Data Distribution

| Decision | Sharding | Replication |
|----------|----------|-------------|
| Goal | Split data (scale writes/storage) | Copy data (HA + scale reads) |
| Cost | Cross-shard queries hard | Replication lag / conflicts |
| Usually | Combine both | Combine both |

| Replication mode | Sync | Async |
|------------------|------|-------|
| Consistency | Strong | Eventual |
| Write latency | Higher | Lower |
| Data loss on leader crash | None | Possible |

---

## Messaging

| Decision | Queue (point-to-point) | Pub/Sub (fan-out) |
|----------|------------------------|-------------------|
| Delivery | One consumer per message | All subscribers get it |
| Use for | Work distribution | Event broadcasting |

| Broker | RabbitMQ/SQS | Kafka |
|--------|--------------|-------|
| Best for | Task queues, routing | High-throughput streaming, replay |
| Retention | Delete after consume | Retained log |

---

## API

| Decision | REST | GraphQL | gRPC |
|----------|------|---------|------|
| Public API | ✅ | ⚠️ | ❌ |
| Flexible client queries | ⚠️ | ✅ | ❌ |
| Internal microservices | ⚠️ | ⚠️ | ✅ |
| Caching | Easy | Hard | Custom |

| Pagination | Offset | Cursor |
|------------|--------|--------|
| Jump to page | ✅ | ❌ |
| Deep pages / stable feeds | ❌ | ✅ |

---

## Reliability Patterns

| Pattern | Purpose |
|---------|---------|
| Circuit breaker | Stop cascading failures |
| Retry + backoff + jitter | Handle transient failures |
| Bulkhead | Isolate resource pools |
| Rate limiting | Prevent abuse/overload |
| Idempotency keys | Safe retries, no duplicates |
| Timeout | Never wait forever |

---

## Transactions

| Approach | Atomicity | Scale | Use |
|----------|-----------|-------|-----|
| 2PC | Strong | Poor | Rare, tight coupling |
| Saga (orchestration) | Eventual | Good | Microservice workflows |
| Outbox + CDC | Reliable events | Good | Atomic DB write + publish |

---

## "When in doubt" Defaults

| Situation | Sensible default |
|-----------|------------------|
| Web/app tier | Stateless + horizontal scaling + LB |
| Read-heavy data | Cache-aside (Redis) + read replicas |
| Large files/media | Object storage + CDN |
| Async/heavy work | Message queue + workers |
| Unique IDs at scale | Snowflake-style / counter+base62 |
| Consistency unknown | Strong for money, eventual for everything social |

---

## 🔗 Related
- [CAP Theorem](../02-scalability/04-cap-theorem.md)
- [Database Comparison](database-comparison.md)
- [Common Mistakes](../11-interview-playbook/03-common-mistakes.md)
