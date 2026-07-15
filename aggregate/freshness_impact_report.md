# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-15 UTC
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
🟡 **X+**: FRESH alert rate (14.3%) is 2.0× the overall rate (7.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.1 | 28.6% | 0.638 | 0.6 |       53 | 75.0% |  46.2% | 1.5× | 14.8% |   0.4906 |
|       OK |   27 |   36.9 | 7.4% | 0.520 | 0.1 |       26 | 0.0% |   0.0% |    - | 9.1% |   0.1538 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  128 |   55.3 | 18.0% | 0.573 | 0.3 |      124 | 56.5% |  31.7% | 1.7× | 12.0% |   0.3306 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.1 | 3.6% | 0.538 | 0.0 |       53 | 100.0% |  18.2% | 4.8× | 0.0% |   0.2075 |
|       OK |   27 |   36.9 | 0.0% | 0.376 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  128 |   55.3 | 1.6% | 0.457 | 0.0 |      124 | 100.0% |  14.3% | 8.9× | 0.0% |   0.1129 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.1 | 14.3% | 0.644 | 0.1 |       53 | 12.5% |  20.0% | 1.3× | 14.6% |   0.0943 |
|       OK |   27 |   36.9 | 3.7% | 0.553 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  128 |   55.3 | 7.0% | 0.581 | 0.1 |      124 | 11.1% |  16.7% | 2.3× | 6.8% |   0.0484 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.1 | 47.1% | 0.757 | 1.2 |       14 | 75.0% |  66.7% | 1.2× | 40.0% |   0.6429 |
|       OK |    4 |   35.8 | 25.0% | 0.575 | 0.2 |        3 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
| DEGRADED |   10 |  110.8 | 50.0% | 0.660 | 0.5 |       10 | 20.0% |  50.0% | 1.0× | 50.0% |   0.2000 |
|      ALL |   31 |   45.9 | 45.2% | 0.702 | 0.9 |       27 | 50.0% |  58.3% | 1.1× | 46.7% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.1 | 11.8% | 0.662 | 0.1 |       14 | 100.0% |  33.3% | 2.3× | 0.0% |   0.4286 |
|       OK |    4 |   35.8 | 0.0% | 0.442 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.548 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.9 | 6.5% | 0.597 | 0.1 |       27 | 100.0% |  33.3% | 4.5× | 0.0% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.1 | 35.3% | 0.725 | 0.3 |       14 | 16.7% |  50.0% | 1.2× | 41.7% |   0.1429 |
|       OK |    4 |   35.8 | 0.0% | 0.556 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.595 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.9 | 19.4% | 0.661 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available