# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (20.5%) is 2.2× the overall rate (9.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 20.5% | 0.586 | 0.3 |       36 | 75.0% |  35.3% | 1.6× | 10.5% |   0.4722 |
|       OK |   23 |   37.1 | 4.3% | 0.510 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.3% |   0.1364 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.485 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |   97 |   58.3 | 9.3% | 0.532 | 0.1 |       93 | 66.7% |  20.7% | 2.1× | 4.7% |   0.3118 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 0.0% | 0.483 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.1389 |
|       OK |   23 |   37.1 | 0.0% | 0.365 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.365 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |   97 |   58.3 | 0.0% | 0.412 | 0.0 |       93 |    - |   0.0% |    - | 0.0% |   0.0860 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 5.1% | 0.609 | 0.1 |       36 | 0.0% |   0.0% |    - | 6.1% |   0.0833 |
|       OK |   23 |   37.1 | 4.3% | 0.553 | 0.0 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.498 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |   97 |   58.3 | 3.1% | 0.556 | 0.0 |       93 | 0.0% |   0.0% |    - | 3.4% |   0.0430 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.0 | 7.7% | 0.555 | 0.1 |       10 | 0.0% |   0.0% |    - | 14.3% |   0.3000 |
|       OK |    8 |   39.7 | 0.0% | 0.464 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   91.9 | 0.0% | 0.570 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   45.8 | 3.2% | 0.536 | 0.1 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.0 | 0.0% | 0.455 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   39.7 | 0.0% | 0.274 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   91.9 | 0.0% | 0.355 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   45.8 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.0 | 7.7% | 0.605 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    8 |   39.7 | 0.0% | 0.582 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   91.9 | 0.0% | 0.575 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.8 | 3.2% | 0.589 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available