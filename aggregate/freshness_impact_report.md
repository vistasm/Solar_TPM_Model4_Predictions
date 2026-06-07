# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (22.9%) is 2.3× the overall rate (10.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 22.9% | 0.589 | 0.4 |       32 | 85.7% |  37.5% | 1.7× | 6.2% |   0.5000 |
|       OK |   21 |   36.6 | 4.8% | 0.508 | 0.1 |       20 | 0.0% |   0.0% |    - | 5.9% |   0.1500 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   90 |   60.6 | 10.0% | 0.531 | 0.2 |       86 | 75.0% |  21.4% | 2.3× | 3.5% |   0.3256 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 0.0% | 0.479 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1562 |
|       OK |   21 |   36.6 | 0.0% | 0.373 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.360 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   90 |   60.6 | 0.0% | 0.409 | 0.0 |       86 |    - |   0.0% |    - | 0.0% |   0.0930 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   12.9 | 5.7% | 0.611 | 0.1 |       32 | 0.0% |   0.0% |    - | 3.5% |   0.0938 |
|       OK |   21 |   36.6 | 4.8% | 0.552 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.4 | 0.0% | 0.496 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   90 |   60.6 | 3.3% | 0.554 | 0.0 |       86 | 0.0% |   0.0% |    - | 2.4% |   0.0465 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.5 | 18.2% | 0.542 | 0.3 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|       OK |    8 |   38.9 | 0.0% | 0.482 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.1 | 0.0% | 0.607 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.4167 |
|      ALL |   31 |   49.7 | 6.5% | 0.552 | 0.1 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.5 | 0.0% | 0.410 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    8 |   38.9 | 0.0% | 0.319 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.1 | 0.0% | 0.383 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   49.7 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.5 | 9.1% | 0.603 | 0.1 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    8 |   38.9 | 0.0% | 0.580 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.1 | 0.0% | 0.576 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.7 | 3.2% | 0.587 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available