# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (20.5%) is 2.2× the overall rate (9.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 20.5% | 0.586 | 0.3 |       37 | 75.0% |  35.3% | 1.6× | 10.0% |   0.4595 |
|       OK |   24 |   37.2 | 4.2% | 0.497 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.3% |   0.1364 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.485 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |   98 |   58.1 | 9.2% | 0.528 | 0.1 |       94 | 66.7% |  20.7% | 2.2× | 4.6% |   0.3085 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 0.0% | 0.483 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.1351 |
|       OK |   24 |   37.2 | 0.0% | 0.355 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.365 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |   98 |   58.1 | 0.0% | 0.410 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0851 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 5.1% | 0.609 | 0.1 |       37 | 0.0% |   0.0% |    - | 5.9% |   0.0811 |
|       OK |   24 |   37.2 | 4.2% | 0.545 | 0.0 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.498 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |   98 |   58.1 | 3.1% | 0.554 | 0.0 |       94 | 0.0% |   0.0% |    - | 3.3% |   0.0426 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.0 | 7.7% | 0.555 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
|       OK |    8 |   40.5 | 0.0% | 0.433 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   91.9 | 0.0% | 0.570 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   46.0 | 3.2% | 0.528 | 0.1 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.0 | 0.0% | 0.455 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   40.5 | 0.0% | 0.268 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   91.9 | 0.0% | 0.355 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   46.0 | 0.0% | 0.374 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.0 | 7.7% | 0.605 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    8 |   40.5 | 0.0% | 0.558 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   91.9 | 0.0% | 0.575 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.0 | 3.2% | 0.583 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available