# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-19 UTC
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
|    FRESH |   16 |   13.4 | 6.2% | 0.517 | 0.1 |       16 | 100.0% |  12.5% | 2.0× | 0.0% |   0.5000 |
|       OK |   11 |   35.6 | 9.1% | 0.513 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
| DEGRADED |   14 |  121.2 | 0.0% | 0.393 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   41 |   56.1 | 4.9% | 0.474 | 0.1 |       37 | 50.0% |   8.3% | 1.5× | 4.0% |   0.3243 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.404 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.6 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  121.2 | 0.0% | 0.351 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   41 |   56.1 | 0.0% | 0.384 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0541 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.544 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.6 | 9.1% | 0.536 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   14 |  121.2 | 0.0% | 0.440 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   41 |   56.1 | 2.4% | 0.506 | 0.0 |       37 | 0.0% |   0.0% |    - | 2.8% |   0.0270 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 10.0% | 0.595 | 0.1 |       10 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   35.1 | 12.5% | 0.558 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |   13 |  125.5 | 0.0% | 0.381 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.4 | 6.5% | 0.496 | 0.1 |       27 | 50.0% |  14.3% | 1.9× | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 0.0% | 0.412 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    8 |   35.1 | 0.0% | 0.410 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  125.5 | 0.0% | 0.335 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.4 | 0.0% | 0.379 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 0.0% | 0.621 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.1 | 12.5% | 0.558 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |   13 |  125.5 | 0.0% | 0.433 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.4 | 3.2% | 0.526 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available