# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-13 UTC
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
|    FRESH |   16 |   13.4 | 6.2% | 0.517 | 0.1 |       15 | 100.0% |  12.5% | 1.9× | 0.0% |   0.5333 |
|       OK |   11 |   35.6 | 9.1% | 0.513 | 0.1 |       10 | 0.0% |   0.0% |    - | 14.3% |   0.3000 |
| DEGRADED |    8 |   79.6 | 0.0% | 0.371 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   35 |   35.5 | 5.7% | 0.483 | 0.1 |       31 | 50.0% |   8.3% | 1.3× | 5.3% |   0.3871 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.404 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   11 |   35.6 | 0.0% | 0.400 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   79.6 | 0.0% | 0.340 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   35 |   35.5 | 0.0% | 0.388 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0645 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.544 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|       OK |   11 |   35.6 | 9.1% | 0.536 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
| DEGRADED |    8 |   79.6 | 0.0% | 0.441 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   35 |   35.5 | 2.9% | 0.518 | 0.0 |       31 | 0.0% |   0.0% |    - | 3.3% |   0.0323 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 6.7% | 0.529 | 0.1 |       14 | 100.0% |  12.5% | 1.8× | 0.0% |   0.5714 |
|       OK |    9 |   34.9 | 11.1% | 0.537 | 0.1 |        8 | 0.0% |   0.0% |    - | 20.0% |   0.3750 |
| DEGRADED |    7 |   81.7 | 0.0% | 0.344 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.9 | 6.5% | 0.489 | 0.1 |       27 | 50.0% |   9.1% | 1.2× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.413 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   34.9 | 0.0% | 0.420 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   81.7 | 0.0% | 0.309 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.9 | 0.0% | 0.392 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.552 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   34.9 | 11.1% | 0.547 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    7 |   81.7 | 0.0% | 0.427 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.9 | 3.2% | 0.522 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available