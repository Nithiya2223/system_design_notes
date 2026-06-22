# 🗄️ Database Comparison Cheatsheet

> Scannable comparison of database types and popular engines. Match workload → type → engine.

---

## Database Types at a Glance

| Type | Data model | Consistency | Scaling | Best for | Avoid for |
|------|-----------|-------------|---------|----------|-----------|
| Relational (SQL) | Tables, rows, joins | Strong (ACID) | Vertical / hard sharding | Transactions, complex queries | Massive flexible scale |
| Document | JSON-like docs | Tunable | Horizontal | Flexible/evolving schema | Complex multi-entity joins |
| Key-Value | key → value | Tunable | Horizontal | Caching, sessions, lookups | Range/complex queries |
| Wide-Column | Rows w/ dynamic cols | Tunable (eventual) | Horizontal | High writes, time-series | Ad-hoc joins |
| Graph | Nodes + edges | Varies | Vertical-ish | Relationship queries | Bulk analytics |
| Search | Inverted index | Eventual | Horizontal | Full-text search | Source of truth/transactions |
| Columnar / Warehouse | Columnar | N/A (analytics) | Horizontal | OLAP, BI, aggregations | OLTP / low-latency writes |
| Time-Series | Time-indexed | Eventual | Horizontal | Metrics, IoT, monitoring | General-purpose data |

---

## Popular Engines

| Engine | Type | Consistency | Notable for |
|--------|------|-------------|-------------|
| PostgreSQL | Relational | Strong (ACID) | Feature-rich, JSON support |
| MySQL | Relational | Strong (ACID) | Ubiquitous, read replicas |
| Google Spanner | Relational (distributed) | Strong (global) | TrueTime, global scale |
| CockroachDB | Relational (distributed) | Strong | Horizontal SQL |
| MongoDB | Document | Tunable | Flexible schema, sharding |
| DynamoDB | Key-Value/Document | Tunable (eventual default) | Serverless, predictable scale |
| Redis | Key-Value (in-mem) | Strong (single node) | Cache, sessions, pub/sub |
| Memcached | Key-Value (in-mem) | N/A | Pure caching |
| Cassandra | Wide-Column | Tunable (AP) | Massive writes, multi-region |
| HBase / Bigtable | Wide-Column | Strong-ish (CP) | Huge tables, analytics |
| Neo4j | Graph | ACID | Deep relationship queries |
| Elasticsearch | Search | Eventual | Full-text, log search |
| BigQuery / Snowflake / Redshift | Columnar Warehouse | N/A | OLAP / BI |
| InfluxDB / TimescaleDB | Time-Series | Eventual | Metrics, sensors |

---

## SQL vs NoSQL Quick Decision

| If you need... | Choose |
|----------------|--------|
| Multi-row transactions | SQL |
| Complex joins / ad-hoc queries | SQL |
| Strong consistency / constraints | SQL |
| Flexible / changing schema | Document NoSQL |
| Extreme write throughput | Wide-Column |
| Sub-ms key lookups / caching | Key-Value |
| Relationship traversal | Graph |
| Full-text search | Search engine |
| Analytics over big data | Warehouse |

---

## CAP Positioning

| System | CAP lean |
|--------|----------|
| PostgreSQL/MySQL (single leader) | CP |
| Spanner | CP (strong) |
| HBase, etcd, ZooKeeper, MongoDB (default) | CP |
| Cassandra, DynamoDB (default), Riak | AP |
| DNS | AP |

---

## Consistency vs Latency vs Scale (relative)

| Type | Consistency | Read latency | Write scale |
|------|-------------|--------------|-------------|
| SQL | ★★★★★ | ★★★☆ | ★★ |
| Document | ★★★ | ★★★★ | ★★★★ |
| Key-Value (in-mem) | ★★★ | ★★★★★ | ★★★★★ |
| Wide-Column | ★★★ | ★★★★ | ★★★★★ |
| Graph | ★★★★ | ★★★ | ★★ |

---

## 🔗 Related
- [Relational vs NoSQL](../03-databases/01-relational-vs-nosql.md)
- [Database Selection Guide](../03-databases/06-database-selection-guide.md)
- [Choosing the Right Database](../13-hld-deep-dive/03-choosing-the-right-database.md)
