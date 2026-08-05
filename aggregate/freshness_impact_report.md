# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.4× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.1× the overall rate (6.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       32 | 0.0% |   0.0% |    - | 7.1% |   0.1250 |
| DEGRADED |   55 |  114.7 | 10.9% | 0.522 | 0.1 |       51 | 20.0% |   7.1% | 0.7× | 10.8% |   0.2745 |
|      ALL |  149 |   55.3 | 18.1% | 0.577 | 0.3 |      145 | 57.7% |  31.9% | 1.8× | 11.2% |   0.3241 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   55 |  114.7 | 0.0% | 0.400 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  149 |   55.3 | 1.3% | 0.460 | 0.0 |      145 | 100.0% |  14.3% | 10.4× | 0.0% |   0.0966 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   55 |  114.7 | 0.0% | 0.513 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0196 |
|      ALL |  149 |   55.3 | 6.0% | 0.569 | 0.1 |      145 | 11.1% |  16.7% | 2.7× | 5.8% |   0.0414 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.9 | 28.6% | 0.717 | 0.4 |       14 | 50.0% |  50.0% | 1.8× | 20.0% |   0.2857 |
|       OK |    7 |   34.6 | 0.0% | 0.588 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
| DEGRADED |   10 |   90.5 | 10.0% | 0.513 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   43.3 | 16.1% | 0.622 | 0.2 |       27 | 50.0% |  25.0% | 1.7× | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.9 | 0.0% | 0.621 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   34.6 | 0.0% | 0.405 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   90.5 | 0.0% | 0.376 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.3 | 0.0% | 0.493 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.9 | 7.1% | 0.568 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|       OK |    7 |   34.6 | 0.0% | 0.522 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   90.5 | 0.0% | 0.482 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.3 | 3.2% | 0.530 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available