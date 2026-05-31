# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-31 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (22.6%) is 2.3× the overall rate (9.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.0 | 22.6% | 0.572 | 0.3 |       30 | 85.7% |  40.0% | 1.7× | 6.7% |   0.5000 |
|       OK |   20 |   36.4 | 5.0% | 0.501 | 0.1 |       19 | 0.0% |   0.0% |    - | 6.2% |   0.1579 |
| DEGRADED |   32 |  127.0 | 0.0% | 0.474 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   83 |   62.6 | 9.6% | 0.517 | 0.1 |       79 | 75.0% |  25.0% | 2.5× | 3.6% |   0.3038 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.0 | 0.0% | 0.473 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   20 |   36.4 | 0.0% | 0.369 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   32 |  127.0 | 0.0% | 0.363 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   83 |   62.6 | 0.0% | 0.406 | 0.0 |       79 |    - |   0.0% |    - | 0.0% |   0.0759 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.0 | 3.2% | 0.599 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   20 |   36.4 | 5.0% | 0.540 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   32 |  127.0 | 0.0% | 0.491 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0333 |
|      ALL |   83 |   62.6 | 2.4% | 0.543 | 0.0 |       79 | 0.0% |   0.0% |    - | 2.6% |   0.0380 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.7 | 11.1% | 0.446 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|       OK |    8 |   37.1 | 0.0% | 0.459 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.5 | 0.0% | 0.553 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   51.7 | 3.2% | 0.498 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.7 | 0.0% | 0.368 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.1 | 0.0% | 0.323 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.5 | 0.0% | 0.367 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   51.7 | 0.0% | 0.356 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.7 | 0.0% | 0.541 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.1 | 0.0% | 0.548 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.5 | 0.0% | 0.567 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.7 | 0.0% | 0.555 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available