# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (19.5%) is 2.3× the overall rate (8.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   12.8 | 19.5% | 0.573 | 0.3 |       39 | 75.0% |  35.3% | 1.7× | 9.1% |   0.4359 |
|       OK |   24 |   37.2 | 4.2% | 0.497 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.8% |   0.1250 |
| DEGRADED |   39 |  120.4 | 0.0% | 0.472 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.2432 |
|      ALL |  104 |   58.8 | 8.6% | 0.518 | 0.1 |      100 | 66.7% |  20.7% | 2.3× | 4.2% |   0.2900 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   12.8 | 0.0% | 0.481 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   24 |   37.2 | 0.0% | 0.355 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  120.4 | 0.0% | 0.363 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0811 |
|      ALL |  104 |   58.8 | 0.0% | 0.408 | 0.0 |      100 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   12.8 | 4.9% | 0.604 | 0.1 |       39 | 0.0% |   0.0% |    - | 5.6% |   0.0769 |
|       OK |   24 |   37.2 | 4.2% | 0.545 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   39 |  120.4 | 0.0% | 0.485 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0270 |
|      ALL |  104 |   58.8 | 2.9% | 0.545 | 0.0 |      100 | 0.0% |   0.0% |    - | 3.1% |   0.0400 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.5 | 8.3% | 0.564 | 0.2 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|       OK |    6 |   42.6 | 0.0% | 0.502 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.7 | 0.0% | 0.528 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   54.4 | 3.2% | 0.537 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.5 | 0.0% | 0.491 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   42.6 | 0.0% | 0.294 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.7 | 0.0% | 0.372 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.4 | 0.0% | 0.403 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.5 | 8.3% | 0.607 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    6 |   42.6 | 0.0% | 0.571 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.7 | 0.0% | 0.515 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.4 | 3.2% | 0.562 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available