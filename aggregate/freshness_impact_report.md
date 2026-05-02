# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (27.3%) is 2.1× the overall rate (13.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 27.3% | 0.624 | 0.5 |       21 | 100.0% |  46.2% | 1.6× | 0.0% |   0.6190 |
|       OK |   12 |   35.9 | 8.3% | 0.529 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.437 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   54 |   69.3 | 13.0% | 0.533 | 0.2 |       50 | 85.7% |  31.6% | 2.3× | 3.2% |   0.3800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 0.0% | 0.516 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1905 |
|       OK |   12 |   35.9 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.364 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   54 |   69.3 | 0.0% | 0.434 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 4.5% | 0.622 | 0.1 |       21 | 0.0% |   0.0% |    - | 5.3% |   0.0952 |
|       OK |   12 |   35.9 | 8.3% | 0.534 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.444 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   54 |   69.3 | 3.7% | 0.536 | 0.0 |       50 | 0.0% |   0.0% |    - | 4.3% |   0.0600 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.2 | 45.5% | 0.733 | 0.8 |       10 | 100.0% |  62.5% | 1.2× | 0.0% |   0.8000 |
|       OK |    4 |   36.0 | 0.0% | 0.567 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.468 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   95.0 | 16.1% | 0.575 | 0.3 |       27 | 100.0% |  45.5% | 2.5× | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.2 | 0.0% | 0.619 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    4 |   36.0 | 0.0% | 0.368 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.354 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.0 | 0.0% | 0.450 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.2 | 9.1% | 0.693 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    4 |   36.0 | 0.0% | 0.467 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.437 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.0 | 3.2% | 0.532 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available