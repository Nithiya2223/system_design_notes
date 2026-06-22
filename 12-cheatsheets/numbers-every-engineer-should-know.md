# 🔢 Numbers Every Engineer Should Know

> Scannable reference of latency, storage, throughput, and powers-of-2 numbers for back-of-the-envelope estimation.

---

## Latency Numbers (Jeff Dean style)

| Operation | Latency | In ns |
|-----------|---------|-------|
| L1 cache reference | 1 ns | 1 |
| Branch mispredict | 3 ns | 3 |
| L2 cache reference | 4 ns | 4 |
| Mutex lock/unlock | 17 ns | 17 |
| Main memory (RAM) reference | 100 ns | 100 |
| Compress 1 KB (Snappy) | 2,000 ns | 2 µs |
| Send 1 KB over 1 Gbps network | 10,000 ns | 10 µs |
| SSD random read | 16,000 ns | 16 µs |
| Read 1 MB sequentially from RAM | 250,000 ns | 250 µs |
| Round trip within same datacenter | 500,000 ns | 0.5 ms |
| Read 1 MB sequentially from SSD | 1,000,000 ns | 1 ms |
| Disk seek (HDD) | 10,000,000 ns | 10 ms |
| Read 1 MB sequentially from HDD | 20,000,000 ns | 20 ms |
| Round trip CA ↔ Netherlands | 150,000,000 ns | 150 ms |

**Rules of thumb:** RAM ≈ 100× L1 · SSD ≈ 1,000× RAM · Disk seek / network RTT ≈ 1,000,000× RAM.

---

## Latency Tier Ladder (fastest → slowest)

| Tier | Order of magnitude |
|------|--------------------|
| CPU registers / L1 | ~1 ns |
| L2 / L3 cache | ~4–40 ns |
| RAM | ~100 ns |
| SSD | ~10–150 µs |
| Same-DC network RTT | ~0.5 ms |
| HDD seek | ~10 ms |
| Cross-continent RTT | ~150 ms |

---

## Storage Units

| Unit | Bytes | Powers of 10 |
|------|-------|--------------|
| KB | 1,000 | 10^3 |
| MB | 1,000,000 | 10^6 |
| GB | 1,000,000,000 | 10^9 |
| TB | 10^12 | trillion |
| PB | 10^15 | quadrillion |
| EB | 10^18 | quintillion |

---

## Typical Object Sizes

| Item | Size |
|------|------|
| ASCII char | 1 B |
| int / float | 4 B |
| long / double / timestamp | 8 B |
| UUID | 16 B |
| Tweet / short text | ~200–300 B |
| Metadata row | ~1 KB |
| Web page (HTML) | ~100 KB |
| Compressed photo | ~200 KB–2 MB |
| 1 min compressed video | ~10–50 MB |

---

## Powers of 2 (for capacity/addressing)

| Power | Exact value | Approx | Name |
|-------|-------------|--------|------|
| 2^10 | 1,024 | ~1 thousand | 1 KB |
| 2^16 | 65,536 | ~65 thousand | (max port #) |
| 2^20 | 1,048,576 | ~1 million | 1 MB |
| 2^30 | 1,073,741,824 | ~1 billion | 1 GB |
| 2^32 | ~4.29 × 10^9 | ~4.3 billion | (IPv4 space) |
| 2^40 | ~1.1 × 10^12 | ~1 trillion | 1 TB |
| 2^50 | ~1.13 × 10^15 | ~1 quadrillion | 1 PB |
| 2^63 | ~9.2 × 10^18 | (max signed 64-bit) | |

---

## Throughput Benchmarks (rough)

| Component | Throughput |
|-----------|-----------|
| Single commodity server (simple req) | ~1k–10k+ QPS |
| Redis / Memcached (single node) | ~100k–200k ops/sec |
| PostgreSQL/MySQL (single node) | ~1k–10k+ TPS (workload-dependent) |
| Kafka broker | ~100k–1M+ msgs/sec |
| 1 Gbps link | ~125 MB/sec |
| 10 Gbps link | ~1.25 GB/sec |
| NVMe SSD | ~500k+ IOPS |

---

## Time & QPS Shortcuts

| Reference | Value |
|-----------|-------|
| Seconds/day | 86,400 ≈ 10^5 |
| Seconds/month | ~2.6 × 10^6 |
| Seconds/year | ~3.15 × 10^7 |
| **QPS formula** | daily count ÷ 10^5 |
| Peak factor | ~2–3× average |
| 1 million seconds | ~11.6 days |

---

## Availability ("nines") → Downtime

| Availability | Downtime/year | Downtime/day |
|--------------|---------------|--------------|
| 99% | ~3.65 days | ~14.4 min |
| 99.9% | ~8.77 hrs | ~1.44 min |
| 99.99% | ~52.6 min | ~8.6 sec |
| 99.999% | ~5.26 min | ~0.86 sec |

---

## 🔗 Related
- [Estimation & Back-of-Envelope](../11-interview-playbook/02-estimation-and-back-of-envelope.md)
- [Latency vs Throughput](../01-fundamentals/04-latency-vs-throughput.md)
