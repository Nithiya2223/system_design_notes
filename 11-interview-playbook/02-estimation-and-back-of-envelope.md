# Estimation & Back-of-the-Envelope Calculations

## 🧭 Overview
Back-of-the-envelope estimation is the skill of quickly approximating scale — QPS, storage, bandwidth, memory — to justify architecture decisions. Interviewers use it to see if your design matches reality (do you need 3 servers or 3,000?). This guide gives you the standard numbers to memorize and **5 fully worked examples**.

---

## 📊 Numbers Every Engineer Should Know

### Latency Numbers (orders of magnitude)
| Operation | Approx Latency | Relative |
|-----------|---------------|----------|
| L1 cache reference | ~1 ns | 1x |
| L2 cache reference | ~4 ns | |
| Branch mispredict | ~3 ns | |
| Main memory (RAM) reference | ~100 ns | 100x L1 |
| Mutex lock/unlock | ~17 ns | |
| Compress 1 KB (Snappy) | ~2 µs | |
| Send 1 KB over 1 Gbps network | ~10 µs | |
| Read 1 MB sequentially from RAM | ~ 0.25 ms | |
| SSD random read | ~16 µs–150 µs | ~1,000x RAM |
| Read 1 MB sequentially from SSD | ~1 ms | |
| Round trip within same datacenter | ~0.5 ms | |
| Read 1 MB sequentially from HDD | ~20 ms | |
| Disk seek (HDD) | ~10 ms | ~100,000x RAM |
| Round trip CA ↔ Netherlands | ~150 ms | |

**Mental model:** RAM is ~100x faster than the L1-to-RAM... and disk seeks/network round trips (ms) are ~1,000,000x slower than memory (ns). **Avoid disk seeks and cross-region round trips on hot paths.**

### Storage / Data Size Units
| Unit | Bytes | Rough scale |
|------|-------|-------------|
| KB | 10^3 | a short text |
| MB | 10^6 | a small image / 1 min MP3 |
| GB | 10^9 | a movie |
| TB | 10^12 | ~thousands of movies |
| PB | 10^15 | large company's data |

### Typical Sizes (assumptions you can state)
| Item | Size |
|------|------|
| char (ASCII) | 1 byte |
| Integer / timestamp | 4–8 bytes |
| UUID | 16 bytes |
| Short text / tweet | ~200–300 bytes |
| Typical web page request metadata | ~1 KB |
| Photo (compressed) | ~200 KB–2 MB |
| 1 min of video (compressed) | ~10–50 MB |

### Throughput / Availability
| Reference | Value |
|-----------|-------|
| Single commodity server QPS (simple) | ~1,000–10,000+ |
| Redis ops/sec (single node) | ~100k–200k |
| Seconds in a day | **86,400** (~10^5) |
| Seconds in a month | ~2.6M |
| "99.9%" availability downtime | ~8.7 hrs/year |
| "99.99%" availability downtime | ~52 min/year |
| "99.999%" availability downtime | ~5 min/year |

### Handy Shortcuts
- **1 day ≈ 86,400 sec ≈ 10^5 sec** (round for speed).
- **QPS = daily count / 10^5.** Peak ≈ 2–3x average (sometimes more).
- 1 million seconds ≈ 11.5 days.

---

## 🧮 5 Fully Worked Examples

### Example 1 — Twitter storage per day
- **Assumptions:** 150M DAU, 2 tweets/user/day, 300 bytes/tweet (text+metadata).
- Tweets/day = 150M × 2 = **300M tweets/day**.
- Storage/day = 300M × 300 B = 9 × 10^10 B = **~90 GB/day** (text only).
- Per year ≈ 90 GB × 365 ≈ **~33 TB/year**. With media (separate, much larger), multiply heavily.
- **Takeaway:** text is cheap; media dominates storage.

### Example 2 — YouTube upload storage & bandwidth
- **Assumptions:** 500 hours uploaded/min, 1 GB per hour (post-transcode, one rendition).
- Per minute: 500 GB; per day: 500 GB × 1,440 = **720 TB/day** for one rendition.
- With ~5 renditions: **~3.6 PB/day**.
- **Takeaway:** video needs object storage + tiering; transcoding multiplies storage.

### Example 3 — Chat app QPS & connections
- **Assumptions:** 500M DAU, 40 messages/day each, 50% online at peak.
- Messages/day = 500M × 40 = 20B → QPS = 20B / 10^5 = **200,000 msg/sec** avg; peak ~3x ≈ **600,000/sec**.
- Concurrent connections at peak ≈ 250M. At ~250k conns/server → **~1,000 connection servers**.
- **Takeaway:** connection count, not just QPS, drives the fleet size.

### Example 4 — URL shortener key space & reads
- **Assumptions:** 100M new URLs/month, 100:1 read:write.
- Writes/sec = 100M / 2.6M ≈ **~40/sec**; reads ≈ **~4,000/sec** avg.
- Key space: base62, 7 chars → 62^7 ≈ **3.5 × 10^12** keys → decades of headroom.
- **Takeaway:** read-heavy → cache aggressively; 7-char keys suffice.

### Example 5 — Cache memory sizing (80/20 rule)
- **Assumptions:** 10M reads/day on items averaging 1 KB; 20% of items = 80% of traffic.
- If there are 1M unique hot items × 1 KB = **~1 GB** to cache the hot set.
- Daily cache hit could serve ~80% of 10M reads = 8M from cache.
- **Takeaway:** a modest few-GB cache often serves most traffic — huge backend offload.

---

## 🎯 Interview Questions
1. [Amazon] Estimate the storage Instagram needs per day for photos. → **Answer:** DAU × photos/day × avg photo size; e.g., 100M × 2 × 500 KB = 100 TB/day → state assumptions.
2. [Google] How many servers to handle 1M QPS if each does 10k QPS? → **Answer:** ~100 servers + headroom/redundancy (e.g., 130–150 for peak + failures).
3. [Meta] What's the QPS if a feature gets 1B requests/day? → **Answer:** 1B / 10^5 ≈ 10,000 QPS avg; peak ~2–3x.
4. [Netflix] Estimate bandwidth to stream to 1M concurrent viewers at 5 Mbps. → **Answer:** 1M × 5 Mbps = 5 Tbps → must be served by CDN, not origin.
5. [Amazon] How much downtime does 99.99% availability allow per year? → **Answer:** ~52 minutes/year.

---

## 📚 Further Reading
- Jeff Dean's "Numbers Everyone Should Know"
- *System Design Interview* (Alex Xu): estimation chapter

---

## 🔗 Related Topics
- [Numbers Every Engineer Should Know](../12-cheatsheets/numbers-every-engineer-should-know.md)
- [Latency vs Throughput](../01-fundamentals/04-latency-vs-throughput.md)
- [HLD Interview Framework](../13-hld-deep-dive/02-hld-interview-framework.md)
