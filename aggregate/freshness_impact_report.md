# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.5%) is 2.3× the overall rate (10.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   12.9 | 23.5% | 0.587 | 0.4 |       31 | 85.7% |  40.0% | 1.8× | 6.2% |   0.4839 |
|       OK |   21 |   36.6 | 4.8% | 0.508 | 0.1 |       20 | 0.0% |   0.0% |    - | 5.9% |   0.1500 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   89 |   61.1 | 10.1% | 0.529 | 0.2 |       85 | 75.0% |  22.2% | 2.4× | 3.5% |   0.3176 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   12.9 | 0.0% | 0.478 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.1290 |
|       OK |   21 |   36.6 | 0.0% | 0.373 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.360 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   89 |   61.1 | 0.0% | 0.408 | 0.0 |       85 |    - |   0.0% |    - | 0.0% |   0.0824 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   12.9 | 5.9% | 0.610 | 0.1 |       31 | 0.0% |   0.0% |    - | 3.5% |   0.0645 |
|       OK |   21 |   36.6 | 4.8% | 0.552 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.496 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   89 |   61.1 | 3.4% | 0.553 | 0.0 |       85 | 0.0% |   0.0% |    - | 2.4% |   0.0353 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.5 | 20.0% | 0.532 | 0.3 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
|       OK |    8 |   38.9 | 0.0% | 0.482 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.1 | 0.0% | 0.576 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.4615 |
|      ALL |   31 |   51.6 | 6.5% | 0.538 | 0.1 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.5 | 0.0% | 0.401 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   38.9 | 0.0% | 0.319 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.1 | 0.0% | 0.364 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   51.6 | 0.0% | 0.364 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.5 | 10.0% | 0.598 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   38.9 | 0.0% | 0.580 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.1 | 0.0% | 0.573 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.6 | 3.2% | 0.583 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available