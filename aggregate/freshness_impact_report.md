# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.4× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.1× the overall rate (6.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       61 | 73.7% |  48.3% | 1.6× | 15.6% |   0.4754 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       31 | 0.0% |   0.0% |    - | 7.4% |   0.1290 |
| DEGRADED |   53 |  114.4 | 9.4% | 0.513 | 0.1 |       51 | 20.0% |   7.1% | 0.7× | 10.8% |   0.2745 |
|      ALL |  147 |   54.4 | 17.7% | 0.574 | 0.3 |      143 | 57.7% |  31.9% | 1.8× | 11.5% |   0.3287 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       61 | 100.0% |  18.2% | 5.5× | 0.0% |   0.1803 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   53 |  114.4 | 0.0% | 0.395 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  147 |   54.4 | 1.4% | 0.459 | 0.0 |      143 | 100.0% |  14.3% | 10.2× | 0.0% |   0.0979 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       61 | 12.5% |  20.0% | 1.5× | 12.5% |   0.0820 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       31 | 0.0% |      - |    - | 3.2% |   0.0000 |
| DEGRADED |   53 |  114.4 | 0.0% | 0.511 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0196 |
|      ALL |  147 |   54.4 | 6.1% | 0.569 | 0.1 |      143 | 11.1% |  16.7% | 2.6× | 5.8% |   0.0420 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   12.7 | 37.5% | 0.751 | 0.8 |       15 | 66.7% |  66.7% | 1.7× | 22.2% |   0.4000 |
|       OK |    7 |   34.6 | 0.0% | 0.588 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    8 |   83.1 | 0.0% | 0.448 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   35.8 | 19.4% | 0.636 | 0.4 |       27 | 66.7% |  40.0% | 1.8× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   12.7 | 6.2% | 0.667 | 0.1 |       15 | 100.0% |  50.0% | 7.5× | 0.0% |   0.1333 |
|       OK |    7 |   34.6 | 0.0% | 0.405 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   83.1 | 0.0% | 0.338 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   35.8 | 3.2% | 0.523 | 0.0 |       27 | 100.0% |  50.0% | 13.5× | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   12.7 | 18.8% | 0.621 | 0.2 |       15 | 33.3% | 100.0% | 5.0× | 14.3% |   0.0667 |
|       OK |    7 |   34.6 | 0.0% | 0.522 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   83.1 | 0.0% | 0.458 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   35.8 | 9.7% | 0.556 | 0.1 |       27 | 33.3% | 100.0% | 9.0× | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available