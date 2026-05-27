# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.3%) is 2.3× the overall rate (10.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 23.3% | 0.570 | 0.4 |       30 | 85.7% |  40.0% | 1.7× | 6.7% |   0.5000 |
|       OK |   19 |   35.8 | 5.3% | 0.494 | 0.1 |       18 | 0.0% |   0.0% |    - | 6.7% |   0.1667 |
| DEGRADED |   30 |  125.5 | 0.0% | 0.465 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   79 |   61.1 | 10.1% | 0.512 | 0.1 |       75 | 75.0% |  25.0% | 2.3× | 3.9% |   0.3200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 0.0% | 0.476 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   19 |   35.8 | 0.0% | 0.375 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   30 |  125.5 | 0.0% | 0.355 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   79 |   61.1 | 0.0% | 0.406 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 3.3% | 0.599 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   19 |   35.8 | 5.3% | 0.538 | 0.1 |       18 | 0.0% |      - |    - | 5.6% |   0.0000 |
| DEGRADED |   30 |  125.5 | 0.0% | 0.484 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   79 |   61.1 | 2.5% | 0.541 | 0.0 |       75 | 0.0% |   0.0% |    - | 2.8% |   0.0400 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.2 | 27.3% | 0.548 | 0.5 |       11 | 66.7% |  50.0% | 1.8× | 14.3% |   0.3636 |
|       OK |    8 |   36.2 | 0.0% | 0.468 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   73.4 | 0.0% | 0.542 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   42.4 | 9.7% | 0.525 | 0.2 |       27 | 66.7% |  28.6% | 2.6× | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.2 | 0.0% | 0.471 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.341 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   73.4 | 0.0% | 0.347 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   42.4 | 0.0% | 0.389 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.2 | 0.0% | 0.609 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.541 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   73.4 | 0.0% | 0.564 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   42.4 | 0.0% | 0.574 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available