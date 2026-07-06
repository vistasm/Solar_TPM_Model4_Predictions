# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 55.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.1%) is 2.4× the overall rate (1.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (16.3%) is 2.2× the overall rate (7.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.7 | 32.6% | 0.639 | 0.7 |       45 | 75.0% |  40.9% | 1.5× | 13.0% |   0.4889 |
|       OK |   25 |   37.1 | 8.0% | 0.510 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  119 |   58.0 | 19.3% | 0.568 | 0.3 |      115 | 52.6% |  27.8% | 1.7× | 11.4% |   0.3130 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.7 | 4.1% | 0.551 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.1778 |
|       OK |   25 |   37.1 | 0.0% | 0.357 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  119 |   58.0 | 1.7% | 0.455 | 0.0 |      115 |    - |   0.0% |    - | 0.0% |   0.0957 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   11.7 | 16.3% | 0.657 | 0.2 |       45 | 0.0% |   0.0% |    - | 9.8% |   0.0889 |
|       OK |   25 |   37.1 | 4.0% | 0.550 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  119 |   58.0 | 7.6% | 0.583 | 0.1 |      115 | 0.0% |   0.0% |    - | 4.5% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.2 | 50.0% | 0.747 | 1.3 |       12 | 75.0% |  50.0% | 1.5× | 16.7% |   0.5000 |
|       OK |    4 |   39.6 | 25.0% | 0.519 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 45.5% | 0.645 | 0.5 |       11 | 20.0% |  50.0% | 1.1× | 44.4% |   0.1818 |
|      ALL |   31 |   47.7 | 45.2% | 0.681 | 0.9 |       27 | 40.0% |  50.0% | 1.4× | 31.6% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.2 | 12.5% | 0.706 | 0.1 |       12 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    4 |   39.6 | 0.0% | 0.273 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.545 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.7 | 6.5% | 0.593 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.2 | 37.5% | 0.762 | 0.4 |       12 | 0.0% |   0.0% |    - | 18.2% |   0.0833 |
|       OK |    4 |   39.6 | 0.0% | 0.541 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.595 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.7 | 19.4% | 0.674 | 0.2 |       27 | 0.0% |   0.0% |    - | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available