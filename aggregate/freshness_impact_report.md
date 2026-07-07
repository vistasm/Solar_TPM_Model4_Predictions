# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.9%) is 56.9% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.1%) is 2.4× the overall rate (1.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (16.3%) is 2.2× the overall rate (7.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.7 | 32.6% | 0.639 | 0.7 |       46 | 76.9% |  43.5% | 1.5× | 13.0% |   0.5000 |
|       OK |   26 |   36.6 | 7.7% | 0.520 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  120 |   57.7 | 19.2% | 0.570 | 0.3 |      116 | 55.0% |  29.7% | 1.7× | 11.4% |   0.3190 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.7 | 4.1% | 0.551 | 0.0 |       46 | 100.0% |  11.1% | 5.1× | 0.0% |   0.1957 |
|       OK |   26 |   36.6 | 0.0% | 0.365 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  120 |   57.7 | 1.7% | 0.456 | 0.0 |      116 | 100.0% |   8.3% | 9.7× | 0.0% |   0.1034 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.7 | 16.3% | 0.657 | 0.2 |       46 | 0.0% |   0.0% |    - | 11.9% |   0.0870 |
|       OK |   26 |   36.6 | 3.9% | 0.555 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  120 |   57.7 | 7.5% | 0.584 | 0.1 |      116 | 0.0% |   0.0% |    - | 5.4% |   0.0431 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    8.9 | 53.3% | 0.756 | 1.4 |       12 | 80.0% |  66.7% | 1.6× | 16.7% |   0.5000 |
|       OK |    5 |   36.5 | 20.0% | 0.570 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 45.5% | 0.645 | 0.5 |       11 | 20.0% |  50.0% | 1.1× | 44.4% |   0.1818 |
|      ALL |   31 |   48.0 | 45.2% | 0.686 | 0.9 |       27 | 45.5% |  62.5% | 1.5× | 31.6% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    8.9 | 13.3% | 0.716 | 0.1 |       12 | 100.0% |  25.0% | 3.0× | 0.0% |   0.3333 |
|       OK |    5 |   36.5 | 0.0% | 0.330 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.545 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.0 | 6.5% | 0.593 | 0.1 |       27 | 100.0% |  25.0% | 6.8× | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    8.9 | 40.0% | 0.765 | 0.4 |       12 | 0.0% |   0.0% |    - | 27.3% |   0.0833 |
|       OK |    5 |   36.5 | 0.0% | 0.571 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.595 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.0 | 19.4% | 0.673 | 0.2 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available