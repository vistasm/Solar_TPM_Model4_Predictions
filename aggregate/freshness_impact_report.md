# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (25.9%) is 2.2× the overall rate (11.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   12.5 | 25.9% | 0.592 | 0.4 |       26 | 85.7% |  42.9% | 1.6× | 8.3% |   0.5385 |
|       OK |   16 |   35.6 | 6.2% | 0.529 | 0.1 |       15 | 0.0% |   0.0% |    - | 8.3% |   0.2000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.452 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.2174 |
|      ALL |   68 |   62.9 | 11.8% | 0.526 | 0.2 |       64 | 75.0% |  27.3% | 2.2× | 4.8% |   0.3438 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   12.5 | 0.0% | 0.489 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |   16 |   35.6 | 0.0% | 0.398 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.369 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|      ALL |   68 |   62.9 | 0.0% | 0.423 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0938 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   12.5 | 3.7% | 0.608 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   16 |   35.6 | 6.2% | 0.538 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.468 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   68 |   62.9 | 2.9% | 0.540 | 0.0 |       64 | 0.0% |   0.0% |    - | 3.3% |   0.0469 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.1 | 54.5% | 0.701 | 0.9 |       10 | 83.3% |  83.3% | 1.4× | 25.0% |   0.6000 |
|       OK |    5 |   35.7 | 0.0% | 0.562 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  165.3 | 0.0% | 0.517 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.3077 |
|      ALL |   31 |   89.7 | 19.4% | 0.590 | 0.3 |       27 | 83.3% |  50.0% | 2.2× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.1 | 0.0% | 0.613 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    5 |   35.7 | 0.0% | 0.395 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  165.3 | 0.0% | 0.396 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   89.7 | 0.0% | 0.473 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.1 | 9.1% | 0.702 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    5 |   35.7 | 0.0% | 0.543 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  165.3 | 0.0% | 0.494 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   89.7 | 3.2% | 0.576 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available