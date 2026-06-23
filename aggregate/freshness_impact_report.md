# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (21.4%) is 2.1× the overall rate (10.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 21.4% | 0.581 | 0.3 |       39 | 75.0% |  35.3% | 1.7× | 9.1% |   0.4359 |
|       OK |   25 |   37.1 | 8.0% | 0.510 | 0.1 |       24 | 0.0% |   0.0% |    - | 4.8% |   0.1250 |
| DEGRADED |   39 |  120.4 | 0.0% | 0.472 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  106 |   58.1 | 10.4% | 0.524 | 0.1 |      102 | 66.7% |  20.0% | 2.3× | 4.2% |   0.2941 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 0.0% | 0.485 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   25 |   37.1 | 0.0% | 0.357 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  120.4 | 0.0% | 0.363 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  106 |   58.1 | 0.0% | 0.410 | 0.0 |      102 |    - |   0.0% |    - | 0.0% |   0.0784 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 4.8% | 0.605 | 0.1 |       39 | 0.0% |   0.0% |    - | 5.6% |   0.0769 |
|       OK |   25 |   37.1 | 4.0% | 0.550 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   39 |  120.4 | 0.0% | 0.485 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  106 |   58.1 | 2.8% | 0.548 | 0.0 |      102 | 0.0% |   0.0% |    - | 3.1% |   0.0392 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 16.7% | 0.607 | 0.2 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|       OK |    7 |   41.3 | 14.3% | 0.548 | 0.1 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  100.2 | 0.0% | 0.542 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   53.1 | 9.7% | 0.569 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 0.0% | 0.509 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   41.3 | 0.0% | 0.311 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  100.2 | 0.0% | 0.374 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   53.1 | 0.0% | 0.412 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 8.3% | 0.621 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    7 |   41.3 | 0.0% | 0.586 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  100.2 | 0.0% | 0.513 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.1 | 3.2% | 0.571 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available