# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 60.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 2.4× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (15.7%) is 2.1× the overall rate (7.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   11.7 | 31.4% | 0.639 | 0.7 |       48 | 80.0% |  48.0% | 1.5× | 13.0% |   0.5208 |
|       OK |   26 |   36.6 | 7.7% | 0.520 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  122 |   57.0 | 18.9% | 0.571 | 0.3 |      118 | 59.1% |  33.3% | 1.8× | 11.4% |   0.3305 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   11.7 | 3.9% | 0.547 | 0.0 |       48 | 100.0% |  18.2% | 4.4× | 0.0% |   0.2292 |
|       OK |   26 |   36.6 | 0.0% | 0.365 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  122 |   57.0 | 1.6% | 0.456 | 0.0 |      118 | 100.0% |  14.3% | 8.4× | 0.0% |   0.1186 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   11.7 | 15.7% | 0.656 | 0.2 |       48 | 14.3% |  20.0% | 1.4× | 14.0% |   0.1042 |
|       OK |   26 |   36.6 | 3.9% | 0.555 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  122 |   57.0 | 7.4% | 0.584 | 0.1 |      118 | 12.5% |  16.7% | 2.5× | 6.2% |   0.0508 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.0 | 50.0% | 0.749 | 1.3 |       13 | 85.7% |  75.0% | 1.4× | 20.0% |   0.6154 |
|       OK |    4 |   35.8 | 25.0% | 0.580 | 0.2 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   11 |  106.5 | 45.5% | 0.645 | 0.5 |       11 | 20.0% |  50.0% | 1.1× | 44.4% |   0.1818 |
|      ALL |   31 |   47.1 | 45.2% | 0.690 | 0.9 |       27 | 53.8% |  70.0% | 1.4× | 35.3% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.0 | 12.5% | 0.697 | 0.1 |       13 | 100.0% |  33.3% | 2.2× | 0.0% |   0.4615 |
|       OK |    4 |   35.8 | 0.0% | 0.327 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.545 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.1 | 6.5% | 0.596 | 0.1 |       27 | 100.0% |  33.3% | 4.5× | 0.0% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.0 | 37.5% | 0.754 | 0.4 |       13 | 20.0% |  50.0% | 1.3× | 36.4% |   0.1538 |
|       OK |    4 |   35.8 | 0.0% | 0.558 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.595 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.1 | 19.4% | 0.672 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available