# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (26.1%) is 2.0× the overall rate (12.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   12.6 | 26.1% | 0.617 | 0.4 |       22 | 100.0% |  46.2% | 1.7× | 0.0% |   0.5909 |
|       OK |   12 |   35.9 | 8.3% | 0.529 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.437 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   55 |   68.2 | 12.7% | 0.532 | 0.2 |       51 | 85.7% |  31.6% | 2.3× | 3.1% |   0.3725 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   12.6 | 0.0% | 0.518 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   12 |   35.9 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.364 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   55 |   68.2 | 0.0% | 0.436 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0980 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   12.6 | 4.3% | 0.619 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   12 |   35.9 | 8.3% | 0.534 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.444 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   55 |   68.2 | 3.6% | 0.537 | 0.0 |       51 | 0.0% |   0.0% |    - | 4.2% |   0.0588 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.7 | 45.5% | 0.737 | 0.8 |       10 | 100.0% |  71.4% | 1.4× | 0.0% |   0.7000 |
|       OK |    4 |   36.0 | 0.0% | 0.567 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.468 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   95.2 | 16.1% | 0.576 | 0.3 |       27 | 100.0% |  50.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.7 | 0.0% | 0.653 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    4 |   36.0 | 0.0% | 0.368 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.354 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.2 | 0.0% | 0.462 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.7 | 9.1% | 0.684 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    4 |   36.0 | 0.0% | 0.467 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.437 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.2 | 3.2% | 0.528 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available