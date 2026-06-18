# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (20.5%) is 2.3× the overall rate (8.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 20.5% | 0.586 | 0.3 |       39 | 75.0% |  35.3% | 1.7× | 9.1% |   0.4359 |
|       OK |   24 |   37.2 | 4.2% | 0.497 | 0.0 |       23 | 0.0% |   0.0% |    - | 5.0% |   0.1304 |
| DEGRADED |   38 |  119.9 | 0.0% | 0.480 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |  101 |   59.0 | 8.9% | 0.525 | 0.1 |       97 | 66.7% |  20.7% | 2.2× | 4.4% |   0.2990 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 0.0% | 0.483 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   24 |   37.2 | 0.0% | 0.355 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   38 |  119.9 | 0.0% | 0.366 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |  101 |   59.0 | 0.0% | 0.409 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0825 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 5.1% | 0.609 | 0.1 |       39 | 0.0% |   0.0% |    - | 5.6% |   0.0769 |
|       OK |   24 |   37.2 | 4.2% | 0.545 | 0.0 |       23 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |   38 |  119.9 | 0.0% | 0.489 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |  101 |   59.0 | 3.0% | 0.548 | 0.0 |       97 | 0.0% |   0.0% |    - | 3.2% |   0.0412 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.9 | 9.1% | 0.577 | 0.2 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|       OK |    7 |   42.6 | 0.0% | 0.459 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.0 | 0.0% | 0.533 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   53.1 | 3.2% | 0.532 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.9 | 0.0% | 0.464 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    7 |   42.6 | 0.0% | 0.268 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.0 | 0.0% | 0.360 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   53.1 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.9 | 9.1% | 0.617 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    7 |   42.6 | 0.0% | 0.563 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.0 | 0.0% | 0.529 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.1 | 3.2% | 0.568 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available