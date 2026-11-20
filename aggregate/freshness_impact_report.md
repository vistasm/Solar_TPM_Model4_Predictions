# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (64.3%) is 22.2% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 3.0× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.4%) is 2.7× the overall rate (3.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 32.9% | 0.629 | 0.5 |       82 | 64.3% |  50.0% | 1.5× | 21.7% |   0.4390 |
|       OK |   47 |   36.2 | 10.6% | 0.527 | 0.1 |       46 | 20.0% |  16.7% | 1.5× | 10.0% |   0.1304 |
| DEGRADED |  124 |  117.7 | 15.3% | 0.464 | 0.1 |      124 | 42.1% |  32.0% | 2.1× | 11.1% |   0.2016 |
|      ALL |  256 |   67.7 | 20.3% | 0.530 | 0.3 |      252 | 51.9% |  40.3% | 1.9× | 13.5% |   0.2659 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 2.4% | 0.567 | 0.0 |       82 | 100.0% |  15.4% | 6.3× | 0.0% |   0.1585 |
|       OK |   47 |   36.2 | 0.0% | 0.405 | 0.0 |       46 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.378 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0403 |
|      ALL |  256 |   67.7 | 0.8% | 0.446 | 0.0 |      252 | 100.0% |  11.1% | 14.0× | 0.0% |   0.0714 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 9.4% | 0.606 | 0.1 |       82 | 12.5% |  20.0% | 2.0× | 9.1% |   0.0610 |
|       OK |   47 |   36.2 | 2.1% | 0.538 | 0.0 |       46 | 0.0% |      - |    - | 2.2% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.492 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  256 |   67.7 | 3.5% | 0.538 | 0.0 |      252 | 11.1% |  16.7% | 4.7× | 3.2% |   0.0238 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 50.0% | 0.689 | 0.5 |        5 | 25.0% | 100.0% | 1.2× | 75.0% |   0.2000 |
|       OK |    5 |   31.8 | 40.0% | 0.693 | 0.4 |        4 | 50.0% | 100.0% | 2.0× | 33.3% |   0.2500 |
| DEGRADED |   18 |  115.0 | 5.6% | 0.334 | 0.1 |       18 | 100.0% |  50.0% | 9.0× | 0.0% |   0.1111 |
|      ALL |   31 |   74.6 | 22.6% | 0.483 | 0.2 |       27 | 42.9% |  75.0% | 2.9× | 17.4% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.667 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   31.8 | 0.0% | 0.588 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  115.0 | 0.0% | 0.295 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   74.6 | 0.0% | 0.438 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.581 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   31.8 | 0.0% | 0.587 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  115.0 | 0.0% | 0.413 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   74.6 | 0.0% | 0.484 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available