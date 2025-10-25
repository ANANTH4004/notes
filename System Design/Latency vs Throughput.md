
**Source:** [cs.fyi Guide – Latency vs Throughput](https://cs.fyi/guide/latency-vs-throughput)
**Tags:** #system-design  [[SystemDesign]]

---
## 📏 Latency

- **Definition:** Time taken for a system to respond to a request.
  *Measured in milliseconds or microseconds.*
- **Represents:** *Responsiveness* of a system.  
- **High latency →** slower performance.  
- **Low latency →** faster and smoother user experience.
- **Causes:**  
  - Network distance and congestion  
  - Inefficient algorithms  
  - Resource contention (CPU, memory, I/O)
---
# ⚙️ Throughput

- **Definition:** Number of requests or operations handled per unit time.  
  *Measured in req/s, txn/s, or bits/s.*
- **Represents:** *Capacity* of a system.  
- **High throughput →** efficient, scalable system.  
- **Low throughput →** bottlenecks, underutilized resources.
- **Limiting factors:**  
  - Hardware capacity (CPU, memory, bandwidth)  
  - Concurrency model and thread limits  
  - Algorithm efficiency
---
## 🔄 Relationship Between Latency & Throughput
- There’s a **trade-off**:
  - Increasing throughput often increases latency (more load per resource).
  - Reducing latency may lower throughput (fewer parallel tasks).
- **Goal:** Find a balance — *maximize throughput while keeping latency acceptable.

---
## 🌐 Real-World Examples

### 1. Web Server

- **Low latency:** fast page load.  
- **High throughput:** handle many concurrent requests.  
- **Trade-offs:**
  - Adding more servers → higher throughput but possible routing latency.
  - Optimizing concurrency → may increase CPU load and delay response times.
  - Use caching + load balancing for best balance.

### 2. Databases
- **Low latency focus:** caching frequently accessed data → faster reads.  
- **Impact:** may reduce throughput (less memory for other tasks).  
- **Strategy:** tune caching + indexing to meet query performance SLAs.

---
## 🧠 Key Insight

> Always aim for **maximum throughput with acceptable latency**, not the lowest latency possible.

---
## 🧩 Quick Comparison Table
| Metric | Measures | Goal | Typical Unit | Affected By |
|--------|-----------|------|---------------|--------------|
**Latency** | Time per operation | Minimize | ms, µs | Network delay, computation time |
| **Throughput** | Ops per unit time | Maximize | req/s, txn/s | Hardware limits, concurrency |