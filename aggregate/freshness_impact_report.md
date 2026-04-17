# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-17 UTC
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
| DEGRADED |   12 |  103.9 | 0.0% | 0.376 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   39 |   47.5 | 5.1% | 0.472 | 0.1 |       35 | 50.0% |   8.3% | 1.5× | 4.3% |   0.3429 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.404 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.6 | 0.0% | 0.400 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  103.9 | 0.0% | 0.339 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   39 |   47.5 | 0.0% | 0.383 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0571 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.544 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.6 | 9.1% | 0.536 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   12 |  103.9 | 0.0% | 0.424 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   39 |   47.5 | 2.6% | 0.505 | 0.0 |       35 | 0.0% |   0.0% |    - | 2.9% |   0.0286 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 8.3% | 0.542 | 0.1 |       12 | 100.0% |  16.7% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   35.1 | 12.5% | 0.558 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |   11 |  107.5 | 0.0% | 0.359 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.2 | 6.5% | 0.481 | 0.1 |       27 | 50.0% |  12.5% | 1.7× | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.406 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    8 |   35.1 | 0.0% | 0.410 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  107.5 | 0.0% | 0.319 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.2 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.572 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    8 |   35.1 | 12.5% | 0.558 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |   11 |  107.5 | 0.0% | 0.414 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.2 | 3.2% | 0.512 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available