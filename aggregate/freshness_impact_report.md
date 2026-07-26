# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (77.8%) is 57.8% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.3× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.3%) is 2.1× the overall rate (6.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.2 | 31.7% | 0.649 | 0.6 |       58 | 77.8% |  48.3% | 1.6× | 13.8% |   0.5000 |
|       OK |   29 |   37.1 | 6.9% | 0.516 | 0.1 |       28 | 0.0% |   0.0% |    - | 8.3% |   0.1429 |
| DEGRADED |   50 |  117.3 | 10.0% | 0.500 | 0.1 |       49 | 20.0% |   8.3% | 0.8× | 10.8% |   0.2449 |
|      ALL |  139 |   55.2 | 18.7% | 0.568 | 0.3 |      135 | 60.0% |  33.3% | 1.8× | 11.1% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.2 | 3.3% | 0.558 | 0.0 |       58 | 100.0% |  18.2% | 5.3× | 0.0% |   0.1897 |
|       OK |   29 |   37.1 | 0.0% | 0.362 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  117.3 | 0.0% | 0.381 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  139 |   55.2 | 1.4% | 0.454 | 0.0 |      135 | 100.0% |  14.3% | 9.6× | 0.0% |   0.1037 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.2 | 13.3% | 0.635 | 0.1 |       58 | 12.5% |  20.0% | 1.4× | 13.2% |   0.0862 |
|       OK |   29 |   37.1 | 3.5% | 0.547 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   50 |  117.3 | 0.0% | 0.507 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  139 |   55.2 | 6.5% | 0.571 | 0.1 |      135 | 11.1% |  16.7% | 2.5× | 6.2% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.1 | 55.6% | 0.810 | 1.3 |       16 | 88.9% |  80.0% | 1.4× | 16.7% |   0.6250 |
|       OK |    4 |   37.1 | 0.0% | 0.553 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    9 |  114.8 | 44.4% | 0.566 | 0.4 |        8 | 25.0% |  50.0% | 1.0× | 50.0% |   0.2500 |
|      ALL |   31 |   44.5 | 45.2% | 0.706 | 0.9 |       27 | 69.2% |  69.2% | 1.4× | 28.6% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.1 | 11.1% | 0.728 | 0.1 |       16 | 100.0% |  40.0% | 3.2× | 0.0% |   0.3125 |
|       OK |    4 |   37.1 | 0.0% | 0.396 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  114.8 | 0.0% | 0.415 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   44.5 | 6.5% | 0.594 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.1 | 33.3% | 0.705 | 0.3 |       16 | 16.7% |  50.0% | 1.3× | 35.7% |   0.1250 |
|       OK |    4 |   37.1 | 0.0% | 0.531 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  114.8 | 0.0% | 0.573 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   44.5 | 19.4% | 0.644 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available