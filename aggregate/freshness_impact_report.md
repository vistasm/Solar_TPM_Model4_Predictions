# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (64.3%) is 22.2% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.4%) is 2.7× the overall rate (3.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 32.9% | 0.629 | 0.5 |       85 | 64.3% |  48.6% | 1.5× | 20.8% |   0.4353 |
|       OK |   48 |   36.3 | 10.4% | 0.519 | 0.1 |       48 | 20.0% |  14.3% | 1.4× | 9.8% |   0.1458 |
| DEGRADED |  129 |  117.5 | 14.7% | 0.451 | 0.1 |      125 | 42.1% |  32.0% | 2.1× | 11.0% |   0.2000 |
|      ALL |  262 |   68.4 | 19.9% | 0.521 | 0.3 |      258 | 51.9% |  39.1% | 1.9× | 13.2% |   0.2674 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 2.4% | 0.567 | 0.0 |       85 | 100.0% |  15.4% | 6.5× | 0.0% |   0.1529 |
|       OK |   48 |   36.3 | 0.0% | 0.399 | 0.0 |       48 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  129 |  117.5 | 0.0% | 0.366 | 0.0 |      125 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |  262 |   68.4 | 0.8% | 0.438 | 0.0 |      258 | 100.0% |  11.1% | 14.3× | 0.0% |   0.0698 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 9.4% | 0.606 | 0.1 |       85 | 12.5% |  20.0% | 2.1× | 8.8% |   0.0588 |
|       OK |   48 |   36.3 | 2.1% | 0.534 | 0.0 |       48 | 0.0% |      - |    - | 2.1% |   0.0000 |
| DEGRADED |  129 |  117.5 | 0.0% | 0.486 | 0.0 |      125 |    - |   0.0% |    - | 0.0% |   0.0080 |
|      ALL |  262 |   68.4 | 3.4% | 0.534 | 0.0 |      258 | 11.1% |  16.7% | 4.8× | 3.2% |   0.0233 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 50.0% | 0.689 | 0.5 |        8 | 25.0% |  50.0% | 1.0× | 50.0% |   0.2500 |
|       OK |    6 |   33.1 | 33.3% | 0.602 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   17 |  120.8 | 5.9% | 0.255 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   75.4 | 22.6% | 0.434 | 0.2 |       27 | 42.9% |  50.0% | 1.9× | 19.1% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.667 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.508 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  120.8 | 0.0% | 0.205 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   75.4 | 0.0% | 0.383 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.581 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.545 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  120.8 | 0.0% | 0.384 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   75.4 | 0.0% | 0.466 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available