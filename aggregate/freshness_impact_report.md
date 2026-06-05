# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (24.2%) is 2.4× the overall rate (10.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   12.8 | 24.2% | 0.586 | 0.4 |       31 | 85.7% |  40.0% | 1.8× | 6.2% |   0.4839 |
|       OK |   21 |   36.6 | 4.8% | 0.508 | 0.1 |       20 | 0.0% |   0.0% |    - | 5.9% |   0.1500 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.485 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.2424 |
|      ALL |   88 |   61.6 | 10.2% | 0.528 | 0.2 |       84 | 75.0% |  23.1% | 2.4× | 3.5% |   0.3095 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   12.8 | 0.0% | 0.475 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.1290 |
|       OK |   21 |   36.6 | 0.0% | 0.373 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.360 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0606 |
|      ALL |   88 |   61.6 | 0.0% | 0.406 | 0.0 |       84 |    - |   0.0% |    - | 0.0% |   0.0714 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   12.8 | 6.1% | 0.607 | 0.1 |       31 | 0.0% |   0.0% |    - | 3.5% |   0.0645 |
|       OK |   21 |   36.6 | 4.8% | 0.552 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.496 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0303 |
|      ALL |   88 |   61.6 | 3.4% | 0.551 | 0.0 |       84 | 0.0% |   0.0% |    - | 2.5% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.5 | 22.2% | 0.523 | 0.3 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
|       OK |    8 |   38.9 | 0.0% | 0.482 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.5 | 0.0% | 0.555 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.3846 |
|      ALL |   31 |   52.8 | 6.5% | 0.527 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.5 | 0.0% | 0.383 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   38.9 | 0.0% | 0.319 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.5 | 0.0% | 0.355 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   52.8 | 0.0% | 0.354 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.5 | 11.1% | 0.585 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   38.9 | 0.0% | 0.580 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.5 | 0.0% | 0.570 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.8 | 3.2% | 0.577 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available