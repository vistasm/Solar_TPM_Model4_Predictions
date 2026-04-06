# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-06 UTC
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
|    FRESH |   15 |   12.9 | 6.7% | 0.520 | 0.1 |       12 | 100.0% |  16.7% | 2.0× | 0.0% |   0.5000 |
|       OK |    9 |   35.2 | 11.1% | 0.536 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   28 |   30.5 | 7.1% | 0.496 | 0.1 |       24 | 50.0% |  11.1% | 1.3× | 6.7% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.419 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.2 | 0.0% | 0.435 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   30.5 | 0.0% | 0.422 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.549 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.2 | 11.1% | 0.554 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   30.5 | 3.6% | 0.540 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 6.7% | 0.520 | 0.1 |       12 | 100.0% |  16.7% | 2.0× | 0.0% |   0.5000 |
|       OK |    9 |   35.2 | 11.1% | 0.536 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   28 |   30.5 | 7.1% | 0.496 | 0.1 |       24 | 50.0% |  11.1% | 1.3× | 6.7% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.419 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.2 | 0.0% | 0.435 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   30.5 | 0.0% | 0.422 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.549 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    9 |   35.2 | 11.1% | 0.554 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   30.5 | 3.6% | 0.540 | 0.0 |       24 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available