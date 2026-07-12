# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 55.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 2.3× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.8%) is 2.1× the overall rate (7.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   11.8 | 29.6% | 0.641 | 0.6 |       50 | 75.0% |  46.2% | 1.4× | 16.7% |   0.5200 |
|       OK |   26 |   36.6 | 7.7% | 0.520 | 0.1 |       26 | 0.0% |   0.0% |    - | 9.1% |   0.1538 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  125 |   55.9 | 18.4% | 0.574 | 0.3 |      121 | 56.5% |  31.7% | 1.7× | 12.5% |   0.3388 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   11.8 | 3.7% | 0.547 | 0.0 |       50 | 100.0% |  18.2% | 4.5× | 0.0% |   0.2200 |
|       OK |   26 |   36.6 | 0.0% | 0.365 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  125 |   55.9 | 1.6% | 0.458 | 0.0 |      121 | 100.0% |  14.3% | 8.6× | 0.0% |   0.1157 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   11.8 | 14.8% | 0.649 | 0.1 |       50 | 12.5% |  20.0% | 1.2× | 15.6% |   0.1000 |
|       OK |   26 |   36.6 | 3.9% | 0.555 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  125 |   55.9 | 7.2% | 0.583 | 0.1 |      121 | 11.1% |  16.7% | 2.2× | 7.0% |   0.0496 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 47.1% | 0.749 | 1.2 |       13 | 75.0% |  66.7% | 1.1× | 50.0% |   0.6923 |
|       OK |    4 |   35.8 | 25.0% | 0.580 | 0.2 |        4 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
| DEGRADED |   10 |  110.8 | 50.0% | 0.660 | 0.5 |       10 | 20.0% |  50.0% | 1.0× | 50.0% |   0.2000 |
|      ALL |   31 |   45.8 | 45.2% | 0.699 | 0.9 |       27 | 50.0% |  58.3% | 1.1× | 46.7% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 11.8% | 0.670 | 0.1 |       13 | 100.0% |  33.3% | 2.2× | 0.0% |   0.4615 |
|       OK |    4 |   35.8 | 0.0% | 0.327 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.548 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.8 | 6.5% | 0.586 | 0.1 |       27 | 100.0% |  33.3% | 4.5× | 0.0% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.0 | 35.3% | 0.724 | 0.3 |       13 | 16.7% |  50.0% | 1.1× | 45.5% |   0.1538 |
|       OK |    4 |   35.8 | 0.0% | 0.558 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  110.8 | 0.0% | 0.595 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.8 | 19.4% | 0.661 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available