# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 55.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.6%) is 2.3× the overall rate (1.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.3%) is 2.1× the overall rate (6.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.1 | 28.6% | 0.638 | 0.6 |       56 | 75.0% |  44.4% | 1.6× | 13.8% |   0.4821 |
|       OK |   28 |   37.1 | 7.1% | 0.511 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.7% |   0.1481 |
| DEGRADED |   48 |  118.1 | 10.4% | 0.502 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  132 |   55.9 | 17.4% | 0.561 | 0.3 |      128 | 56.5% |  30.9% | 1.7× | 11.6% |   0.3281 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.1 | 3.6% | 0.538 | 0.0 |       56 | 100.0% |  18.2% | 5.1× | 0.0% |   0.1964 |
|       OK |   28 |   37.1 | 0.0% | 0.365 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  118.1 | 0.0% | 0.385 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  132 |   55.9 | 1.5% | 0.446 | 0.0 |      128 | 100.0% |  14.3% | 9.1× | 0.0% |   0.1094 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.1 | 14.3% | 0.644 | 0.1 |       56 | 12.5% |  20.0% | 1.4× | 13.7% |   0.0893 |
|       OK |   28 |   37.1 | 3.6% | 0.547 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |
| DEGRADED |   48 |  118.1 | 0.0% | 0.508 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  132 |   55.9 | 6.8% | 0.574 | 0.1 |      128 | 11.1% |  16.7% | 2.4× | 6.6% |   0.0469 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.1 | 47.1% | 0.757 | 1.2 |       17 | 75.0% |  60.0% | 1.3× | 28.6% |   0.5882 |
|       OK |    4 |   36.0 | 25.0% | 0.594 | 0.2 |        3 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
| DEGRADED |   10 |  111.0 | 50.0% | 0.587 | 0.5 |        7 | 20.0% |  50.0% | 0.7× | 80.0% |   0.2857 |
|      ALL |   31 |   46.0 | 45.2% | 0.681 | 0.9 |       27 | 50.0% |  53.8% | 1.0× | 50.0% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.1 | 11.8% | 0.662 | 0.1 |       17 | 100.0% |  33.3% | 2.8× | 0.0% |   0.3529 |
|       OK |    4 |   36.0 | 0.0% | 0.426 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 0.0% | 0.459 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.0 | 6.5% | 0.566 | 0.1 |       27 | 100.0% |  33.3% | 4.5× | 0.0% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.1 | 35.3% | 0.725 | 0.3 |       17 | 16.7% |  50.0% | 1.4× | 33.3% |   0.1176 |
|       OK |    4 |   36.0 | 0.0% | 0.562 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.0 | 0.0% | 0.580 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.0 | 19.4% | 0.657 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available