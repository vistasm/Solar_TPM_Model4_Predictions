# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (24.1%) is 2.2× the overall rate (11.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.4 | 24.1% | 0.577 | 0.4 |       28 | 85.7% |  40.0% | 1.6× | 7.7% |   0.5357 |
|       OK |   18 |   35.5 | 5.6% | 0.495 | 0.1 |       16 | 0.0% |   0.0% |    - | 7.7% |   0.1875 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.444 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   73 |   60.6 | 11.0% | 0.509 | 0.2 |       69 | 75.0% |  26.1% | 2.2× | 4.3% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.4 | 0.0% | 0.477 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   18 |   35.5 | 0.0% | 0.375 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.359 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   73 |   60.6 | 0.0% | 0.410 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.4 | 3.5% | 0.602 | 0.0 |       28 | 0.0% |   0.0% |    - | 3.9% |   0.0714 |
|       OK |   18 |   35.5 | 5.6% | 0.536 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   26 |  131.7 | 0.0% | 0.470 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   73 |   60.6 | 2.7% | 0.539 | 0.0 |       69 | 0.0% |   0.0% |    - | 3.0% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.3 | 46.2% | 0.651 | 0.8 |       12 | 83.3% |  71.4% | 1.4× | 20.0% |   0.5833 |
|       OK |    7 |   35.3 | 0.0% | 0.467 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  133.4 | 0.0% | 0.519 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   60.0 | 19.4% | 0.563 | 0.3 |       27 | 83.3% |  45.5% | 2.0× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.3 | 0.0% | 0.569 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   35.3 | 0.0% | 0.336 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  133.4 | 0.0% | 0.381 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   60.0 | 0.0% | 0.449 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.3 | 7.7% | 0.674 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    7 |   35.3 | 0.0% | 0.536 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  133.4 | 0.0% | 0.522 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   60.0 | 3.2% | 0.589 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available