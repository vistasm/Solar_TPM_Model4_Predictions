# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-12 UTC
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
|       OK |   11 |   35.6 | 9.1% | 0.513 | 0.1 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
| DEGRADED |    7 |   77.8 | 0.0% | 0.372 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   34 |   33.8 | 5.9% | 0.486 | 0.1 |       30 | 50.0% |   9.1% | 1.4× | 5.3% |   0.3667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.404 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   11 |   35.6 | 0.0% | 0.400 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   77.8 | 0.0% | 0.347 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   34 |   33.8 | 0.0% | 0.391 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.544 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|       OK |   11 |   35.6 | 9.1% | 0.536 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |
| DEGRADED |    7 |   77.8 | 0.0% | 0.460 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   34 |   33.8 | 2.9% | 0.524 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.5% |   0.0333 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 6.7% | 0.529 | 0.1 |       14 | 100.0% |  12.5% | 1.8× | 0.0% |   0.5714 |
|       OK |    9 |   34.9 | 11.1% | 0.537 | 0.1 |        7 | 0.0% |   0.0% |    - | 20.0% |   0.2857 |
| DEGRADED |    7 |   77.8 | 0.0% | 0.372 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   34.0 | 6.5% | 0.496 | 0.1 |       27 | 50.0% |   9.1% | 1.2× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.413 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   34.9 | 0.0% | 0.420 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   77.8 | 0.0% | 0.347 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.0 | 0.0% | 0.400 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.1 | 0.0% | 0.552 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   34.9 | 11.1% | 0.547 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |    7 |   77.8 | 0.0% | 0.460 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.0 | 3.2% | 0.530 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available