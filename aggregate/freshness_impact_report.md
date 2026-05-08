# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (24.0%) is 2.1× the overall rate (11.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.3 | 24.0% | 0.592 | 0.4 |       24 | 100.0% |  42.9% | 1.7× | 0.0% |   0.5833 |
|       OK |   13 |   35.2 | 7.7% | 0.524 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
| DEGRADED |   22 |  143.7 | 0.0% | 0.419 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   60 |   65.4 | 11.7% | 0.514 | 0.2 |       56 | 85.7% |  30.0% | 2.4× | 2.8% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.3 | 0.0% | 0.496 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |   13 |   35.2 | 0.0% | 0.406 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  143.7 | 0.0% | 0.348 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   60 |   65.4 | 0.0% | 0.422 | 0.0 |       56 |    - |   0.0% |    - | 0.0% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.3 | 4.0% | 0.612 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.5% |   0.0833 |
|       OK |   13 |   35.2 | 7.7% | 0.534 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   22 |  143.7 | 0.0% | 0.452 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   60 |   65.4 | 3.3% | 0.536 | 0.0 |       56 | 0.0% |   0.0% |    - | 3.8% |   0.0536 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 50.0% | 0.699 | 0.9 |        9 | 100.0% |  83.3% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   35.4 | 0.0% | 0.496 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   17 |  162.6 | 0.0% | 0.432 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   97.4 | 16.1% | 0.526 | 0.3 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 0.0% | 0.611 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   35.4 | 0.0% | 0.341 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  162.6 | 0.0% | 0.333 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.4 | 0.0% | 0.424 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 10.0% | 0.705 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    4 |   35.4 | 0.0% | 0.489 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  162.6 | 0.0% | 0.444 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.4 | 3.2% | 0.534 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available