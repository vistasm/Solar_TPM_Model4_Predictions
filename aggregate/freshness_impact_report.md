# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 21.4% | 0.581 | 0.3 |       42 | 66.7% |  31.6% | 1.5× | 13.0% |   0.4524 |
|       OK |   25 |   37.1 | 8.0% | 0.510 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   43 |  117.9 | 7.0% | 0.505 | 0.1 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  110 |   59.4 | 12.7% | 0.535 | 0.2 |      106 | 54.5% |  18.8% | 1.8× | 6.8% |   0.3019 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 0.0% | 0.485 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   25 |   37.1 | 0.0% | 0.357 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   43 |  117.9 | 0.0% | 0.391 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  110 |   59.4 | 0.0% | 0.419 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0849 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 4.8% | 0.605 | 0.1 |       42 | 0.0% |   0.0% |    - | 5.1% |   0.0714 |
|       OK |   25 |   37.1 | 4.0% | 0.550 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   43 |  117.9 | 0.0% | 0.508 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  110 |   59.4 | 2.7% | 0.555 | 0.0 |      106 | 0.0% |   0.0% |    - | 2.9% |   0.0377 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 16.7% | 0.607 | 0.2 |       12 | 0.0% |   0.0% |    - | 25.0% |   0.3333 |
|       OK |    6 |   41.1 | 16.7% | 0.559 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   13 |  100.4 | 23.1% | 0.599 | 0.2 |        9 |    - |   0.0% |    - | 0.0% |   0.4444 |
|      ALL |   31 |   55.0 | 19.4% | 0.594 | 0.2 |       27 | 0.0% |   0.0% |    - | 15.8% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 0.0% | 0.509 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   41.1 | 0.0% | 0.301 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  100.4 | 0.0% | 0.474 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   55.0 | 0.0% | 0.454 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 8.3% | 0.621 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    6 |   41.1 | 0.0% | 0.587 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  100.4 | 0.0% | 0.562 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   55.0 | 3.2% | 0.590 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available