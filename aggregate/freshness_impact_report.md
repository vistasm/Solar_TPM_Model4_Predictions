# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.5%) is 56.5% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.3× the overall rate (1.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.3%) is 2.0× the overall rate (6.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.2 | 31.7% | 0.649 | 0.6 |       57 | 76.5% |  46.4% | 1.6× | 13.8% |   0.4912 |
|       OK |   29 |   37.1 | 6.9% | 0.516 | 0.1 |       28 | 0.0% |   0.0% |    - | 8.3% |   0.1429 |
| DEGRADED |   49 |  118.5 | 10.2% | 0.496 | 0.1 |       49 | 20.0% |   8.3% | 0.8× | 10.8% |   0.2449 |
|      ALL |  138 |   55.2 | 18.8% | 0.567 | 0.3 |      134 | 58.3% |  31.8% | 1.8× | 11.1% |   0.3284 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.2 | 3.3% | 0.558 | 0.0 |       57 | 100.0% |  18.2% | 5.2× | 0.0% |   0.1930 |
|       OK |   29 |   37.1 | 0.0% | 0.362 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   49 |  118.5 | 0.0% | 0.382 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  138 |   55.2 | 1.5% | 0.454 | 0.0 |      134 | 100.0% |  14.3% | 9.6× | 0.0% |   0.1045 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.2 | 13.3% | 0.635 | 0.1 |       57 | 12.5% |  20.0% | 1.4× | 13.5% |   0.0877 |
|       OK |   29 |   37.1 | 3.5% | 0.547 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   49 |  118.5 | 0.0% | 0.506 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  138 |   55.2 | 6.5% | 0.571 | 0.1 |      134 | 11.1% |  16.7% | 2.5× | 6.2% |   0.0448 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.1 | 55.6% | 0.810 | 1.3 |       15 | 87.5% |  77.8% | 1.5× | 16.7% |   0.6000 |
|       OK |    4 |   37.1 | 0.0% | 0.553 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    9 |  117.0 | 55.6% | 0.581 | 0.6 |        9 | 20.0% |  50.0% | 0.9× | 57.1% |   0.2222 |
|      ALL |   31 |   45.2 | 48.4% | 0.711 | 0.9 |       27 | 61.5% |  66.7% | 1.4× | 33.3% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.1 | 11.1% | 0.728 | 0.1 |       15 | 100.0% |  40.0% | 3.0× | 0.0% |   0.3333 |
|       OK |    4 |   37.1 | 0.0% | 0.396 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  117.0 | 0.0% | 0.473 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.2 | 6.5% | 0.611 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.1 | 33.3% | 0.705 | 0.3 |       15 | 16.7% |  50.0% | 1.2× | 38.5% |   0.1333 |
|       OK |    4 |   37.1 | 0.0% | 0.531 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  117.0 | 0.0% | 0.588 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.2 | 19.4% | 0.649 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available