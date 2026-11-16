# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (64.3%) is 22.2% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.8%) is 2.7× the overall rate (3.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.1 | 34.2% | 0.633 | 0.6 |       81 | 64.3% |  50.0% | 1.4× | 22.2% |   0.4444 |
|       OK |   46 |   36.4 | 10.9% | 0.526 | 0.1 |       44 | 20.0% |  16.7% | 1.5× | 10.5% |   0.1364 |
| DEGRADED |  124 |  117.7 | 15.3% | 0.464 | 0.1 |      123 | 42.1% |  32.0% | 2.1× | 11.2% |   0.2033 |
|      ALL |  252 |   68.5 | 20.6% | 0.530 | 0.3 |      248 | 51.9% |  40.3% | 1.9× | 13.8% |   0.2702 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.1 | 2.4% | 0.570 | 0.0 |       81 | 100.0% |  15.4% | 6.2× | 0.0% |   0.1605 |
|       OK |   46 |   36.4 | 0.0% | 0.404 | 0.0 |       44 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.378 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0406 |
|      ALL |  252 |   68.5 | 0.8% | 0.445 | 0.0 |      248 | 100.0% |  11.1% | 13.8× | 0.0% |   0.0726 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.1 | 9.8% | 0.612 | 0.1 |       81 | 12.5% |  20.0% | 2.0× | 9.2% |   0.0617 |
|       OK |   46 |   36.4 | 2.2% | 0.540 | 0.0 |       44 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.492 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  252 |   68.5 | 3.6% | 0.540 | 0.0 |      248 | 11.1% |  16.7% | 4.6× | 3.3% |   0.0242 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.6 | 80.0% | 0.784 | 0.8 |        4 | 25.0% | 100.0% | 1.0× | 100.0% |   0.2500 |
|       OK |    4 |   33.4 | 50.0% | 0.725 | 0.5 |        2 | 50.0% | 100.0% | 1.0× | 100.0% |   0.5000 |
| DEGRADED |   22 |  111.4 | 18.2% | 0.420 | 0.2 |       21 | 50.0% |  66.7% | 3.5× | 11.1% |   0.1429 |
|      ALL |   31 |   85.0 | 32.3% | 0.518 | 0.3 |       27 | 40.0% |  80.0% | 2.2× | 27.3% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.6 | 0.0% | 0.777 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.4 | 0.0% | 0.625 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  111.4 | 0.0% | 0.358 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   85.0 | 0.0% | 0.460 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.6 | 0.0% | 0.664 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.4 | 0.0% | 0.621 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  111.4 | 0.0% | 0.458 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   85.0 | 0.0% | 0.512 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available