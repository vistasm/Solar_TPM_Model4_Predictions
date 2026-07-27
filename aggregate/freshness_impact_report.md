# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.3× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.1%) is 2.0× the overall rate (6.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 31.1% | 0.650 | 0.6 |       59 | 73.7% |  48.3% | 1.5× | 16.7% |   0.4915 |
|       OK |   29 |   37.1 | 6.9% | 0.516 | 0.1 |       28 | 0.0% |   0.0% |    - | 8.3% |   0.1429 |
| DEGRADED |   50 |  117.3 | 10.0% | 0.500 | 0.1 |       49 | 20.0% |   8.3% | 0.8× | 10.8% |   0.2449 |
|      ALL |  140 |   54.9 | 18.6% | 0.569 | 0.3 |      136 | 57.7% |  33.3% | 1.7× | 12.1% |   0.3309 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 3.3% | 0.557 | 0.0 |       59 | 100.0% |  18.2% | 5.4× | 0.0% |   0.1864 |
|       OK |   29 |   37.1 | 0.0% | 0.362 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  117.3 | 0.0% | 0.381 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  140 |   54.9 | 1.4% | 0.454 | 0.0 |      136 | 100.0% |  14.3% | 9.7× | 0.0% |   0.1029 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 13.1% | 0.634 | 0.1 |       59 | 12.5% |  20.0% | 1.5× | 13.0% |   0.0847 |
|       OK |   29 |   37.1 | 3.5% | 0.547 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   50 |  117.3 | 0.0% | 0.507 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  140 |   54.9 | 6.4% | 0.571 | 0.1 |      136 | 11.1% |  16.7% | 2.5× | 6.2% |   0.0441 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 52.6% | 0.805 | 1.2 |       17 | 80.0% |  80.0% | 1.4× | 28.6% |   0.5882 |
|       OK |    4 |   37.1 | 0.0% | 0.553 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    8 |  115.9 | 37.5% | 0.525 | 0.4 |        7 | 33.3% |  50.0% | 1.2× | 40.0% |   0.2857 |
|      ALL |   31 |   41.6 | 41.9% | 0.700 | 0.8 |       27 | 69.2% |  69.2% | 1.4× | 28.6% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 10.5% | 0.715 | 0.1 |       17 | 100.0% |  40.0% | 3.4× | 0.0% |   0.2941 |
|       OK |    4 |   37.1 | 0.0% | 0.396 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  115.9 | 0.0% | 0.382 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   41.6 | 6.5% | 0.588 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 31.6% | 0.696 | 0.3 |       17 | 16.7% |  50.0% | 1.4× | 33.3% |   0.1176 |
|       OK |    4 |   37.1 | 0.0% | 0.531 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  115.9 | 0.0% | 0.542 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   41.6 | 19.4% | 0.635 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available