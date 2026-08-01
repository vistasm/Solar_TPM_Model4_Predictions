# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.3× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.1× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       61 | 73.7% |  48.3% | 1.6× | 15.6% |   0.4754 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       30 | 0.0% |   0.0% |    - | 7.7% |   0.1333 |
| DEGRADED |   51 |  116.1 | 9.8% | 0.504 | 0.1 |       50 | 20.0% |   7.7% | 0.8× | 10.8% |   0.2600 |
|      ALL |  145 |   54.1 | 17.9% | 0.572 | 0.3 |      141 | 57.7% |  32.6% | 1.8× | 11.6% |   0.3262 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       61 | 100.0% |  18.2% | 5.5× | 0.0% |   0.1803 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       30 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   51 |  116.1 | 0.0% | 0.388 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  145 |   54.1 | 1.4% | 0.457 | 0.0 |      141 | 100.0% |  14.3% | 10.1× | 0.0% |   0.0993 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       61 | 12.5% |  20.0% | 1.5× | 12.5% |   0.0820 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       30 | 0.0% |      - |    - | 3.3% |   0.0000 |
| DEGRADED |   51 |  116.1 | 0.0% | 0.509 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  145 |   54.1 | 6.2% | 0.569 | 0.1 |      141 | 11.1% |  16.7% | 2.6× | 5.9% |   0.0426 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.8 | 44.4% | 0.778 | 1.0 |       17 | 75.0% |  75.0% | 1.6× | 22.2% |   0.4706 |
|       OK |    7 |   34.6 | 0.0% | 0.588 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.352 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   31.4 | 25.8% | 0.653 | 0.6 |       27 | 75.0% |  54.5% | 1.8× | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.8 | 11.1% | 0.702 | 0.1 |       17 | 100.0% |  66.7% | 5.7× | 0.0% |   0.1765 |
|       OK |    7 |   34.6 | 0.0% | 0.405 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.257 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.4 | 6.5% | 0.549 | 0.1 |       27 | 100.0% |  66.7% | 9.0× | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.8 | 27.8% | 0.662 | 0.3 |       17 | 20.0% | 100.0% | 3.4× | 25.0% |   0.0588 |
|       OK |    7 |   34.6 | 0.0% | 0.522 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.423 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.4 | 16.1% | 0.584 | 0.2 |       27 | 20.0% | 100.0% | 5.4× | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available