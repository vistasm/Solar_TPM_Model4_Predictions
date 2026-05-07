# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (25.0%) is 2.1× the overall rate (11.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 25.0% | 0.610 | 0.4 |       23 | 100.0% |  42.9% | 1.6× | 0.0% |   0.6087 |
|       OK |   13 |   35.2 | 7.7% | 0.524 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
| DEGRADED |   22 |  143.7 | 0.0% | 0.419 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   59 |   66.3 | 11.9% | 0.520 | 0.2 |       55 | 85.7% |  30.0% | 2.4× | 2.9% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 0.0% | 0.510 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.1739 |
|       OK |   13 |   35.2 | 0.0% | 0.406 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  143.7 | 0.0% | 0.348 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   59 |   66.3 | 0.0% | 0.427 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 4.2% | 0.615 | 0.0 |       23 | 0.0% |   0.0% |    - | 4.8% |   0.0870 |
|       OK |   13 |   35.2 | 7.7% | 0.534 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   22 |  143.7 | 0.0% | 0.452 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   59 |   66.3 | 3.4% | 0.536 | 0.0 |       55 | 0.0% |   0.0% |    - | 3.9% |   0.0545 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.1 | 55.6% | 0.759 | 1.0 |        8 | 100.0% |  83.3% | 1.3× | 0.0% |   0.7500 |
|       OK |    4 |   35.4 | 0.0% | 0.496 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   18 |  156.5 | 0.0% | 0.443 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   98.7 | 16.1% | 0.541 | 0.3 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.1 | 0.0% | 0.662 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    4 |   35.4 | 0.0% | 0.341 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  156.5 | 0.0% | 0.336 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   98.7 | 0.0% | 0.431 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.1 | 11.1% | 0.725 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|       OK |    4 |   35.4 | 0.0% | 0.489 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  156.5 | 0.0% | 0.448 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   98.7 | 3.2% | 0.533 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available