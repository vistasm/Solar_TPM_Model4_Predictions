# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.9 | 11.8% | 0.540 | 0.1 |       16 | 100.0% |  12.5% | 2.0× | 0.0% |   0.5000 |
|       OK |   11 |   35.6 | 9.1% | 0.513 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.413 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   46 |   75.9 | 6.5% | 0.484 | 0.1 |       42 | 50.0% |   8.3% | 1.8× | 3.3% |   0.2857 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.9 | 0.0% | 0.435 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.6 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.359 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   46 |   75.9 | 0.0% | 0.397 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0476 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.9 | 0.0% | 0.560 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.6 | 9.1% | 0.536 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.2 | 0.0% | 0.432 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   46 |   75.9 | 2.2% | 0.504 | 0.0 |       42 | 0.0% |   0.0% |    - | 2.4% |   0.0238 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.8 | 18.2% | 0.624 | 0.2 |       10 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    6 |   34.5 | 16.7% | 0.649 | 0.2 |        6 | 0.0% |   0.0% |    - | 25.0% |   0.3333 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.442 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.4 | 9.7% | 0.546 | 0.1 |       27 | 50.0% |  14.3% | 1.9× | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.8 | 0.0% | 0.461 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    6 |   34.5 | 0.0% | 0.412 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.347 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.4 | 0.0% | 0.400 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.8 | 0.0% | 0.639 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   34.5 | 16.7% | 0.619 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   14 |  181.4 | 0.0% | 0.420 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.4 | 3.2% | 0.536 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available