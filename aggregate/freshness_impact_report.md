# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-25 UTC
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
|    FRESH |   42 |   12.7 | 21.4% | 0.581 | 0.3 |       41 | 75.0% |  31.6% | 1.6× | 9.1% |   0.4634 |
|       OK |   25 |   37.1 | 8.0% | 0.510 | 0.1 |       24 | 0.0% |   0.0% |    - | 4.8% |   0.1250 |
| DEGRADED |   41 |  117.9 | 2.4% | 0.486 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  108 |   58.3 | 11.1% | 0.528 | 0.2 |      104 | 66.7% |  18.8% | 2.2× | 4.2% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 0.0% | 0.485 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.1463 |
|       OK |   25 |   37.1 | 0.0% | 0.357 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   41 |  117.9 | 0.0% | 0.374 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  108 |   58.3 | 0.0% | 0.413 | 0.0 |      104 |    - |   0.0% |    - | 0.0% |   0.0865 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   12.7 | 4.8% | 0.605 | 0.1 |       41 | 0.0% |   0.0% |    - | 5.3% |   0.0732 |
|       OK |   25 |   37.1 | 4.0% | 0.550 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   41 |  117.9 | 0.0% | 0.493 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  108 |   58.3 | 2.8% | 0.550 | 0.0 |      104 | 0.0% |   0.0% |    - | 3.0% |   0.0385 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 16.7% | 0.607 | 0.2 |       11 | 0.0% |   0.0% |    - | 14.3% |   0.3636 |
|       OK |    6 |   41.1 | 16.7% | 0.559 | 0.2 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.1 | 7.7% | 0.559 | 0.1 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   54.1 | 12.9% | 0.578 | 0.2 |       27 | 0.0% |   0.0% |    - | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 0.0% | 0.509 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   41.1 | 0.0% | 0.301 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.1 | 0.0% | 0.395 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.1 | 0.0% | 0.421 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 8.3% | 0.621 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    6 |   41.1 | 0.0% | 0.587 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.1 | 0.0% | 0.526 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.1 | 3.2% | 0.575 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available