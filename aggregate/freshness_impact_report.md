# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.0%) is 50.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.3%) is 2.5× the overall rate (1.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.8%) is 2.1× the overall rate (6.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   11.9 | 29.8% | 0.624 | 0.6 |       43 | 70.0% |  35.0% | 1.5× | 13.0% |   0.4651 |
|       OK |   25 |   37.1 | 8.0% | 0.510 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  117 |   58.9 | 17.9% | 0.561 | 0.3 |      113 | 47.1% |  23.5% | 1.6× | 11.4% |   0.3009 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   11.9 | 4.3% | 0.533 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.1628 |
|       OK |   25 |   37.1 | 0.0% | 0.357 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  117 |   58.9 | 1.7% | 0.447 | 0.0 |      113 |    - |   0.0% |    - | 0.0% |   0.0885 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   11.9 | 12.8% | 0.644 | 0.1 |       43 | 0.0% |   0.0% |    - | 5.1% |   0.0930 |
|       OK |   25 |   37.1 | 4.0% | 0.550 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  117 |   58.9 | 6.0% | 0.576 | 0.1 |      113 | 0.0% |   0.0% |    - | 2.8% |   0.0442 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.2 | 46.7% | 0.728 | 1.1 |       11 | 33.3% |  25.0% | 0.9× | 28.6% |   0.3636 |
|       OK |    5 |   40.0 | 20.0% | 0.547 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 45.5% | 0.645 | 0.5 |       11 | 20.0% |  50.0% | 1.1× | 44.4% |   0.1818 |
|      ALL |   31 |   49.2 | 41.9% | 0.669 | 0.7 |       27 | 22.2% |  33.3% | 1.0× | 33.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.2 | 13.3% | 0.663 | 0.1 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.0 | 0.0% | 0.307 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.545 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.2 | 6.5% | 0.564 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.2 | 33.3% | 0.747 | 0.3 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.0 | 0.0% | 0.590 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.595 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.2 | 16.1% | 0.667 | 0.2 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available