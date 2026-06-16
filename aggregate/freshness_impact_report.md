# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (20.5%) is 2.3× the overall rate (9.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 20.5% | 0.586 | 0.3 |       38 | 75.0% |  35.3% | 1.7× | 9.5% |   0.4474 |
|       OK |   24 |   37.2 | 4.2% | 0.497 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.3% |   0.1364 |
| DEGRADED |   36 |  121.0 | 0.0% | 0.488 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |   99 |   58.1 | 9.1% | 0.529 | 0.1 |       95 | 66.7% |  20.7% | 2.2× | 4.5% |   0.3053 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 0.0% | 0.483 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.1316 |
|       OK |   24 |   37.2 | 0.0% | 0.355 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   36 |  121.0 | 0.0% | 0.373 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |   99 |   58.1 | 0.0% | 0.412 | 0.0 |       95 |    - |   0.0% |    - | 0.0% |   0.0842 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 5.1% | 0.609 | 0.1 |       38 | 0.0% |   0.0% |    - | 5.7% |   0.0789 |
|       OK |   24 |   37.2 | 4.2% | 0.545 | 0.0 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |   36 |  121.0 | 0.0% | 0.495 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |   99 |   58.1 | 3.0% | 0.552 | 0.0 |       95 | 0.0% |   0.0% |    - | 3.3% |   0.0421 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.1 | 8.3% | 0.572 | 0.2 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|       OK |    8 |   40.5 | 0.0% | 0.433 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   89.4 | 0.0% | 0.571 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   47.6 | 3.2% | 0.536 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.1 | 0.0% | 0.471 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   40.5 | 0.0% | 0.268 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   89.4 | 0.0% | 0.381 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   47.6 | 0.0% | 0.387 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.1 | 8.3% | 0.610 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    8 |   40.5 | 0.0% | 0.558 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   89.4 | 0.0% | 0.556 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.6 | 3.2% | 0.577 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available