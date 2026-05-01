# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (27.3%) is 2.1× the overall rate (13.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 27.3% | 0.624 | 0.5 |       20 | 100.0% |  41.7% | 1.7× | 0.0% |   0.6000 |
|       OK |   12 |   35.9 | 8.3% | 0.529 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   19 |  155.1 | 0.0% | 0.425 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   53 |   69.0 | 13.2% | 0.531 | 0.2 |       49 | 83.3% |  27.8% | 2.3× | 3.2% |   0.3673 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 0.0% | 0.516 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |   12 |   35.9 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  155.1 | 0.0% | 0.360 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   53 |   69.0 | 0.0% | 0.434 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.1020 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 4.5% | 0.622 | 0.1 |       20 | 0.0% |   0.0% |    - | 5.6% |   0.1000 |
|       OK |   12 |   35.9 | 8.3% | 0.534 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   19 |  155.1 | 0.0% | 0.438 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   53 |   69.0 | 3.8% | 0.536 | 0.0 |       49 | 0.0% |   0.0% |    - | 4.3% |   0.0612 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.9 | 41.7% | 0.717 | 0.8 |       10 | 100.0% |  57.1% | 1.4× | 0.0% |   0.7000 |
|       OK |    4 |   36.0 | 0.0% | 0.567 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   15 |  173.5 | 0.0% | 0.456 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   92.8 | 16.1% | 0.571 | 0.3 |       27 | 100.0% |  40.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.9 | 0.0% | 0.591 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    4 |   36.0 | 0.0% | 0.368 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  173.5 | 0.0% | 0.349 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   92.8 | 0.0% | 0.445 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.9 | 8.3% | 0.700 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    4 |   36.0 | 0.0% | 0.467 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  173.5 | 0.0% | 0.429 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   92.8 | 3.2% | 0.539 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available