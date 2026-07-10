# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 55.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 2.4× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (15.4%) is 2.1× the overall rate (7.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   11.9 | 30.8% | 0.637 | 0.7 |       49 | 75.0% |  48.0% | 1.5× | 16.7% |   0.5102 |
|       OK |   26 |   36.6 | 7.7% | 0.520 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  123 |   56.7 | 18.7% | 0.571 | 0.3 |      119 | 56.5% |  33.3% | 1.7× | 12.5% |   0.3277 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   11.9 | 3.9% | 0.544 | 0.0 |       49 | 100.0% |  18.2% | 4.5× | 0.0% |   0.2245 |
|       OK |   26 |   36.6 | 0.0% | 0.365 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  123 |   56.7 | 1.6% | 0.455 | 0.0 |      119 | 100.0% |  14.3% | 8.5× | 0.0% |   0.1176 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   11.9 | 15.4% | 0.653 | 0.1 |       49 | 12.5% |  20.0% | 1.2× | 15.9% |   0.1020 |
|       OK |   26 |   36.6 | 3.9% | 0.555 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  123 |   56.7 | 7.3% | 0.584 | 0.1 |      119 | 11.1% |  16.7% | 2.2× | 7.1% |   0.0504 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |    9.8 | 47.1% | 0.738 | 1.2 |       14 | 75.0% |  75.0% | 1.3× | 33.3% |   0.5714 |
|       OK |    4 |   35.8 | 25.0% | 0.580 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   10 |  110.8 | 50.0% | 0.660 | 0.5 |       10 | 20.0% |  50.0% | 1.0× | 50.0% |   0.2000 |
|      ALL |   31 |   45.7 | 45.2% | 0.692 | 0.9 |       27 | 50.0% |  70.0% | 1.4× | 41.2% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |    9.8 | 11.8% | 0.677 | 0.1 |       14 | 100.0% |  33.3% | 2.3× | 0.0% |   0.4286 |
|       OK |    4 |   35.8 | 0.0% | 0.327 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.548 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.7 | 6.5% | 0.590 | 0.1 |       27 | 100.0% |  33.3% | 4.5× | 0.0% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |    9.8 | 35.3% | 0.740 | 0.3 |       14 | 16.7% |  50.0% | 1.2× | 41.7% |   0.1429 |
|       OK |    4 |   35.8 | 0.0% | 0.558 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.595 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.7 | 19.4% | 0.670 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available