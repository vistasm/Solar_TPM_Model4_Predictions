# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (22.9%) is 2.3× the overall rate (9.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 22.9% | 0.589 | 0.4 |       33 | 75.0% |  37.5% | 1.6× | 11.8% |   0.4848 |
|       OK |   22 |   36.7 | 4.5% | 0.509 | 0.1 |       20 | 0.0% |   0.0% |    - | 5.9% |   0.1500 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   91 |   60.3 | 9.9% | 0.531 | 0.1 |       87 | 66.7% |  21.4% | 2.1× | 5.1% |   0.3218 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 0.0% | 0.479 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.1515 |
|       OK |   22 |   36.7 | 0.0% | 0.371 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.360 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   91 |   60.3 | 0.0% | 0.408 | 0.0 |       87 |    - |   0.0% |    - | 0.0% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 5.7% | 0.611 | 0.1 |       33 | 0.0% |   0.0% |    - | 6.7% |   0.0909 |
|       OK |   22 |   36.7 | 4.5% | 0.555 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.496 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   91 |   60.3 | 3.3% | 0.554 | 0.0 |       87 | 0.0% |   0.0% |    - | 3.6% |   0.0460 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 20.0% | 0.580 | 0.3 |        8 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
|       OK |    9 |   38.9 | 0.0% | 0.488 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.1 | 0.0% | 0.607 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.4167 |
|      ALL |   31 |   50.5 | 6.5% | 0.564 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 0.0% | 0.435 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    9 |   38.9 | 0.0% | 0.322 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.1 | 0.0% | 0.383 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   50.5 | 0.0% | 0.382 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 10.0% | 0.611 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|       OK |    9 |   38.9 | 0.0% | 0.585 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.1 | 0.0% | 0.576 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   50.5 | 3.2% | 0.590 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available