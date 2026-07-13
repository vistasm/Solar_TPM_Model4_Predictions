# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 55.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.6%) is 2.3× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.5%) is 2.0× the overall rate (7.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.0 | 29.1% | 0.642 | 0.6 |       51 | 75.0% |  46.2% | 1.5× | 16.0% |   0.5098 |
|       OK |   26 |   36.6 | 7.7% | 0.520 | 0.1 |       26 | 0.0% |   0.0% |    - | 9.1% |   0.1538 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  126 |   55.7 | 18.2% | 0.575 | 0.3 |      122 | 56.5% |  31.7% | 1.7× | 12.3% |   0.3361 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.0 | 3.6% | 0.545 | 0.0 |       51 | 100.0% |  18.2% | 4.6× | 0.0% |   0.2157 |
|       OK |   26 |   36.6 | 0.0% | 0.365 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  126 |   55.7 | 1.6% | 0.458 | 0.0 |      122 | 100.0% |  14.3% | 8.7× | 0.0% |   0.1148 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.0 | 14.5% | 0.647 | 0.1 |       51 | 12.5% |  20.0% | 1.3× | 15.2% |   0.0980 |
|       OK |   26 |   36.6 | 3.9% | 0.555 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  126 |   55.7 | 7.1% | 0.583 | 0.1 |      122 | 11.1% |  16.7% | 2.3× | 6.9% |   0.0492 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 47.1% | 0.747 | 1.2 |       13 | 75.0% |  66.7% | 1.1× | 50.0% |   0.6923 |
|       OK |    4 |   35.8 | 25.0% | 0.580 | 0.2 |        4 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
| DEGRADED |   10 |  110.8 | 50.0% | 0.660 | 0.5 |       10 | 20.0% |  50.0% | 1.0× | 50.0% |   0.2000 |
|      ALL |   31 |   45.9 | 45.2% | 0.697 | 0.9 |       27 | 50.0% |  58.3% | 1.1× | 46.7% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 11.8% | 0.665 | 0.1 |       13 | 100.0% |  33.3% | 2.2× | 0.0% |   0.4615 |
|       OK |    4 |   35.8 | 0.0% | 0.327 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.548 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.9 | 6.5% | 0.584 | 0.1 |       27 | 100.0% |  33.3% | 4.5× | 0.0% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 35.3% | 0.718 | 0.3 |       13 | 16.7% |  50.0% | 1.1× | 45.5% |   0.1538 |
|       OK |    4 |   35.8 | 0.0% | 0.558 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.595 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.9 | 19.4% | 0.658 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available