# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.4× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.1× the overall rate (6.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       31 | 0.0% |   0.0% |    - | 7.4% |   0.1290 |
| DEGRADED |   54 |  114.3 | 11.1% | 0.518 | 0.1 |       51 | 20.0% |   7.1% | 0.7× | 10.8% |   0.2745 |
|      ALL |  148 |   54.7 | 18.2% | 0.576 | 0.3 |      144 | 57.7% |  31.9% | 1.8× | 11.3% |   0.3264 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   54 |  114.3 | 0.0% | 0.400 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  148 |   54.7 | 1.4% | 0.460 | 0.0 |      144 | 100.0% |  14.3% | 10.3× | 0.0% |   0.0972 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       31 | 0.0% |      - |    - | 3.2% |   0.0000 |
| DEGRADED |   54 |  114.3 | 0.0% | 0.512 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0196 |
|      ALL |  148 |   54.7 | 6.1% | 0.569 | 0.1 |      144 | 11.1% |  16.7% | 2.7× | 5.8% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.3 | 33.3% | 0.735 | 0.6 |       15 | 60.0% |  60.0% | 1.8× | 20.0% |   0.3333 |
|       OK |    7 |   34.6 | 0.0% | 0.588 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    9 |   85.9 | 11.1% | 0.489 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   39.2 | 19.4% | 0.630 | 0.3 |       27 | 60.0% |  33.3% | 1.8× | 11.1% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.3 | 0.0% | 0.645 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|       OK |    7 |   34.6 | 0.0% | 0.405 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   85.9 | 0.0% | 0.370 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   39.2 | 0.0% | 0.511 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.3 | 13.3% | 0.596 | 0.1 |       15 | 0.0% |      - |    - | 13.3% |   0.0000 |
|       OK |    7 |   34.6 | 0.0% | 0.522 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   85.9 | 0.0% | 0.472 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   39.2 | 6.5% | 0.543 | 0.1 |       27 | 0.0% |      - |    - | 7.4% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available