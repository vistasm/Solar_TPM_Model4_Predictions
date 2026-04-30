# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (27.3%) is 2.0× the overall rate (13.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 27.3% | 0.624 | 0.5 |       19 | 100.0% |  36.4% | 1.7× | 0.0% |   0.5789 |
|       OK |   12 |   35.9 | 8.3% | 0.529 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.413 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   52 |   69.1 | 13.5% | 0.529 | 0.2 |       48 | 80.0% |  23.5% | 2.3× | 3.2% |   0.3542 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 0.0% | 0.516 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.2105 |
|       OK |   12 |   35.9 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.359 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   52 |   69.1 | 0.0% | 0.435 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.1042 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   12.7 | 4.5% | 0.622 | 0.1 |       19 | 0.0% |   0.0% |    - | 5.9% |   0.1053 |
|       OK |   12 |   35.9 | 8.3% | 0.534 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.432 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   52 |   69.1 | 3.9% | 0.536 | 0.0 |       48 | 0.0% |   0.0% |    - | 4.4% |   0.0625 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.9 | 41.7% | 0.717 | 0.8 |        9 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
|       OK |    5 |   34.0 | 20.0% | 0.618 | 0.2 |        4 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.442 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   91.6 | 19.4% | 0.577 | 0.3 |       27 | 75.0% |  33.3% | 2.2× | 5.6% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.9 | 0.0% | 0.591 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    5 |   34.0 | 0.0% | 0.365 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.347 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   91.6 | 0.0% | 0.444 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.9 | 8.3% | 0.700 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    5 |   34.0 | 20.0% | 0.557 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.420 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   91.6 | 6.5% | 0.550 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available