# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (22.9%) is 2.3× the overall rate (9.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 22.9% | 0.589 | 0.4 |       33 | 75.0% |  37.5% | 1.6× | 11.8% |   0.4848 |
|       OK |   22 |   36.7 | 4.5% | 0.509 | 0.1 |       21 | 0.0% |   0.0% |    - | 5.6% |   0.1429 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   92 |   60.4 | 9.8% | 0.530 | 0.1 |       88 | 66.7% |  21.4% | 2.1× | 5.0% |   0.3182 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 0.0% | 0.479 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.1515 |
|       OK |   22 |   36.7 | 0.0% | 0.371 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.365 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   92 |   60.4 | 0.0% | 0.410 | 0.0 |       88 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 5.7% | 0.611 | 0.1 |       33 | 0.0% |   0.0% |    - | 6.7% |   0.0909 |
|       OK |   22 |   36.7 | 4.5% | 0.555 | 0.1 |       21 | 0.0% |      - |    - | 4.8% |   0.0000 |
| DEGRADED |   35 |  122.7 | 0.0% | 0.498 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   92 |   60.4 | 3.3% | 0.555 | 0.0 |       88 | 0.0% |   0.0% |    - | 3.6% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 20.0% | 0.580 | 0.3 |        8 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
|       OK |    8 |   39.0 | 0.0% | 0.497 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   87.1 | 0.0% | 0.598 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.4167 |
|      ALL |   31 |   51.3 | 6.5% | 0.566 | 0.1 |       27 | 0.0% |   0.0% |    - | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 0.0% | 0.435 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    8 |   39.0 | 0.0% | 0.304 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   87.1 | 0.0% | 0.393 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   51.3 | 0.0% | 0.384 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.6 | 10.0% | 0.611 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|       OK |    8 |   39.0 | 0.0% | 0.593 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   87.1 | 0.0% | 0.577 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.3 | 3.2% | 0.592 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available