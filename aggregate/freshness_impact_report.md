# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (25.0%) is 2.2× the overall rate (11.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.2 | 25.0% | 0.589 | 0.4 |       26 | 85.7% |  42.9% | 1.6× | 8.3% |   0.5385 |
|       OK |   17 |   35.0 | 5.9% | 0.512 | 0.1 |       16 | 0.0% |   0.0% |    - | 7.7% |   0.1875 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.444 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   71 |   61.4 | 11.3% | 0.518 | 0.2 |       67 | 75.0% |  27.3% | 2.3× | 4.4% |   0.3284 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.2 | 0.0% | 0.491 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |   17 |   35.0 | 0.0% | 0.390 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.359 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   71 |   61.4 | 0.0% | 0.418 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0896 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.2 | 3.6% | 0.605 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   17 |   35.0 | 5.9% | 0.537 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.470 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   71 |   61.4 | 2.8% | 0.539 | 0.0 |       67 | 0.0% |   0.0% |    - | 3.1% |   0.0448 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.6 | 50.0% | 0.686 | 0.8 |       10 | 83.3% |  83.3% | 1.4× | 25.0% |   0.6000 |
|       OK |    6 |   34.0 | 0.0% | 0.511 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  151.1 | 0.0% | 0.498 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   74.1 | 19.4% | 0.573 | 0.3 |       27 | 83.3% |  50.0% | 2.2× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.6 | 0.0% | 0.607 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    6 |   34.0 | 0.0% | 0.373 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  151.1 | 0.0% | 0.374 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   74.1 | 0.0% | 0.464 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.6 | 8.3% | 0.688 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    6 |   34.0 | 0.0% | 0.539 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  151.1 | 0.0% | 0.504 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   74.1 | 3.2% | 0.582 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available