# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-18 UTC
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
🟡 **X+**: FRESH alert rate (9.5%) is 2.7× the overall rate (3.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.1 | 33.3% | 0.632 | 0.6 |       81 | 64.3% |  50.0% | 1.4× | 22.2% |   0.4444 |
|       OK |   46 |   36.4 | 10.9% | 0.526 | 0.1 |       45 | 20.0% |  16.7% | 1.5× | 10.3% |   0.1333 |
| DEGRADED |  124 |  117.7 | 15.3% | 0.464 | 0.1 |      124 | 42.1% |  32.0% | 2.1× | 11.1% |   0.2016 |
|      ALL |  254 |   68.1 | 20.5% | 0.531 | 0.3 |      250 | 51.9% |  40.3% | 1.9× | 13.7% |   0.2680 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.1 | 2.4% | 0.567 | 0.0 |       81 | 100.0% |  15.4% | 6.2× | 0.0% |   0.1605 |
|       OK |   46 |   36.4 | 0.0% | 0.404 | 0.0 |       45 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.378 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0403 |
|      ALL |  254 |   68.1 | 0.8% | 0.445 | 0.0 |      250 | 100.0% |  11.1% | 13.9× | 0.0% |   0.0720 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.1 | 9.5% | 0.609 | 0.1 |       81 | 12.5% |  20.0% | 2.0× | 9.2% |   0.0617 |
|       OK |   46 |   36.4 | 2.2% | 0.540 | 0.0 |       45 | 0.0% |      - |    - | 2.2% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.492 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  254 |   68.1 | 3.5% | 0.539 | 0.0 |      250 | 11.1% |  16.7% | 4.6× | 3.3% |   0.0240 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |    9.9 | 57.1% | 0.733 | 0.6 |        4 | 25.0% | 100.0% | 1.0× | 100.0% |   0.2500 |
|       OK |    4 |   33.4 | 50.0% | 0.725 | 0.5 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   20 |  113.0 | 10.0% | 0.380 | 0.1 |       20 | 100.0% |  66.7% | 6.7× | 0.0% |   0.1500 |
|      ALL |   31 |   79.5 | 25.8% | 0.504 | 0.3 |       27 | 50.0% |  80.0% | 2.7× | 18.2% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |    9.9 | 0.0% | 0.676 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.4 | 0.0% | 0.625 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  113.0 | 0.0% | 0.330 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   79.5 | 0.0% | 0.446 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |    9.9 | 0.0% | 0.609 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.4 | 0.0% | 0.621 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  113.0 | 0.0% | 0.443 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   79.5 | 0.0% | 0.503 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available