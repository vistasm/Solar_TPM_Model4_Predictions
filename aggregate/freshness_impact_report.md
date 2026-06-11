# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (21.6%) is 2.3× the overall rate (9.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   12.7 | 21.6% | 0.592 | 0.3 |       35 | 75.0% |  35.3% | 1.5× | 11.1% |   0.4857 |
|       OK |   22 |   36.7 | 4.5% | 0.509 | 0.1 |       21 | 0.0% |   0.0% |    - | 5.6% |   0.1429 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   94 |   59.3 | 9.6% | 0.533 | 0.1 |       90 | 66.7% |  20.7% | 2.1× | 4.9% |   0.3222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   12.7 | 0.0% | 0.490 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   22 |   36.7 | 0.0% | 0.371 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.365 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   94 |   59.3 | 0.0% | 0.416 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   12.7 | 5.4% | 0.614 | 0.1 |       35 | 0.0% |   0.0% |    - | 6.2% |   0.0857 |
|       OK |   22 |   36.7 | 4.5% | 0.555 | 0.1 |       21 | 0.0% |      - |    - | 4.8% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.498 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   94 |   59.3 | 3.2% | 0.557 | 0.0 |       90 | 0.0% |   0.0% |    - | 3.5% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.2 | 9.1% | 0.570 | 0.2 |        9 | 0.0% |   0.0% |    - | 16.7% |   0.3333 |
|       OK |    8 |   39.0 | 0.0% | 0.497 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.2 | 0.0% | 0.591 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   49.3 | 3.2% | 0.559 | 0.1 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.2 | 0.0% | 0.472 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   39.0 | 0.0% | 0.304 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.2 | 0.0% | 0.364 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   49.3 | 0.0% | 0.387 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.2 | 9.1% | 0.623 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    8 |   39.0 | 0.0% | 0.593 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.2 | 0.0% | 0.576 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.3 | 3.2% | 0.597 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available