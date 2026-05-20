# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (24.1%) is 2.2× the overall rate (11.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.4 | 24.1% | 0.577 | 0.4 |       27 | 85.7% |  40.0% | 1.5× | 8.3% |   0.5556 |
|       OK |   17 |   35.0 | 5.9% | 0.512 | 0.1 |       16 | 0.0% |   0.0% |    - | 7.7% |   0.1875 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.444 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   72 |   60.8 | 11.1% | 0.514 | 0.2 |       68 | 75.0% |  26.1% | 2.2× | 4.4% |   0.3382 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.4 | 0.0% | 0.477 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |
|       OK |   17 |   35.0 | 0.0% | 0.390 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.359 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   72 |   60.8 | 0.0% | 0.414 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0882 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.4 | 3.5% | 0.602 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |
|       OK |   17 |   35.0 | 5.9% | 0.537 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.470 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   72 |   60.8 | 2.8% | 0.539 | 0.0 |       68 | 0.0% |   0.0% |    - | 3.1% |   0.0441 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.3 | 46.2% | 0.651 | 0.8 |       11 | 83.3% |  71.4% | 1.3× | 25.0% |   0.6364 |
|       OK |    6 |   34.0 | 0.0% | 0.511 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  144.0 | 0.0% | 0.503 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   67.0 | 19.4% | 0.566 | 0.3 |       27 | 83.3% |  45.5% | 2.0× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.3 | 0.0% | 0.569 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   34.0 | 0.0% | 0.373 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  144.0 | 0.0% | 0.368 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|      ALL |   31 |   67.0 | 0.0% | 0.453 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.3 | 7.7% | 0.674 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    6 |   34.0 | 0.0% | 0.539 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  144.0 | 0.0% | 0.504 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   67.0 | 3.2% | 0.582 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available