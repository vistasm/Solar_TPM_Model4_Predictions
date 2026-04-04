# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-04 UTC
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
|    FRESH |   14 |   13.4 | 7.1% | 0.505 | 0.1 |       10 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   35.8 | 12.5% | 0.509 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   26 |   31.4 | 7.7% | 0.477 | 0.1 |       22 | 50.0% |  12.5% | 1.4× | 7.1% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 0.0% | 0.408 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.8 | 0.0% | 0.416 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.4 | 0.0% | 0.410 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 0.0% | 0.553 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.8 | 12.5% | 0.568 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.4 | 3.9% | 0.545 | 0.0 |       22 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 7.1% | 0.505 | 0.1 |       10 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   35.8 | 12.5% | 0.509 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   26 |   31.4 | 7.7% | 0.477 | 0.1 |       22 | 50.0% |  12.5% | 1.4× | 7.1% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 0.0% | 0.408 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.8 | 0.0% | 0.416 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.4 | 0.0% | 0.410 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.4 | 0.0% | 0.553 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.8 | 12.5% | 0.568 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.4 | 3.9% | 0.545 | 0.0 |       22 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available