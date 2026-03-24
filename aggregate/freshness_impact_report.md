# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-24 UTC
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
|    FRESH |    6 |   16.6 | 0.0% | 0.387 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    5 |   36.8 | 0.0% | 0.350 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        1 |    - |   0.0% |    - |   - |   1.0000 |
|      ALL |   15 |   41.8 | 0.0% | 0.355 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.4545 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.6 | 0.0% | 0.390 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.8 | 0.0% | 0.384 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   15 |   41.8 | 0.0% | 0.392 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.6 | 0.0% | 0.415 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.8 | 0.0% | 0.437 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   15 |   41.8 | 0.0% | 0.438 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.6 | 0.0% | 0.387 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    5 |   36.8 | 0.0% | 0.350 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        1 |    - |   0.0% |    - |   - |   1.0000 |
|      ALL |   15 |   41.8 | 0.0% | 0.355 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.4545 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.6 | 0.0% | 0.390 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.8 | 0.0% | 0.384 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   15 |   41.8 | 0.0% | 0.392 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.6 | 0.0% | 0.415 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.8 | 0.0% | 0.437 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   15 |   41.8 | 0.0% | 0.438 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available