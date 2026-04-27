# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (25.0%) is 2.0× the overall rate (12.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   12.0 | 25.0% | 0.600 | 0.4 |       16 | 100.0% |  12.5% | 2.0× | 0.0% |   0.5000 |
|       OK |   11 |   35.6 | 9.1% | 0.513 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.413 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   49 |   71.7 | 12.2% | 0.512 | 0.2 |       45 | 50.0% |   7.1% | 1.6× | 3.2% |   0.3111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   12.0 | 0.0% | 0.484 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.6 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.359 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   49 |   71.7 | 0.0% | 0.419 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   12.0 | 5.0% | 0.606 | 0.1 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.6 | 9.1% | 0.536 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.432 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   49 |   71.7 | 4.1% | 0.526 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.3% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.4 | 33.3% | 0.692 | 0.6 |        8 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    5 |   35.6 | 20.0% | 0.639 | 0.2 |        5 | 0.0% |   0.0% |    - | 25.0% |   0.2000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.442 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   91.3 | 16.1% | 0.571 | 0.3 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.4 | 0.0% | 0.522 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    5 |   35.6 | 0.0% | 0.410 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.347 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   91.3 | 0.0% | 0.425 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.4 | 8.3% | 0.691 | 0.1 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   35.6 | 20.0% | 0.611 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.420 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   91.3 | 6.5% | 0.556 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available