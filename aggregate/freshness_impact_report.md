# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (24.0%) is 2.1× the overall rate (11.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.3 | 24.0% | 0.592 | 0.4 |       24 | 100.0% |  42.9% | 1.7× | 0.0% |   0.5833 |
|       OK |   14 |   35.5 | 7.1% | 0.516 | 0.1 |       13 | 0.0% |   0.0% |    - | 10.0% |   0.2308 |
| DEGRADED |   23 |  140.1 | 0.0% | 0.430 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   62 |   64.9 | 11.3% | 0.515 | 0.2 |       58 | 85.7% |  30.0% | 2.5× | 2.6% |   0.3448 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.3 | 0.0% | 0.496 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |   14 |   35.5 | 0.0% | 0.410 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  140.1 | 0.0% | 0.365 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |   62 |   64.9 | 0.0% | 0.428 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0862 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.3 | 4.0% | 0.612 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.5% |   0.0833 |
|       OK |   14 |   35.5 | 7.1% | 0.533 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   23 |  140.1 | 0.0% | 0.458 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |   62 |   64.9 | 3.2% | 0.537 | 0.0 |       58 | 0.0% |   0.0% |    - | 3.6% |   0.0517 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 50.0% | 0.699 | 0.9 |        9 | 100.0% |  83.3% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   37.4 | 0.0% | 0.449 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.440 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   97.1 | 16.1% | 0.525 | 0.3 |       27 | 100.0% |  62.5% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 0.0% | 0.611 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   37.4 | 0.0% | 0.389 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.364 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.1 | 0.0% | 0.447 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 10.0% | 0.705 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    4 |   37.4 | 0.0% | 0.476 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.447 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.1 | 3.2% | 0.534 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available