# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-17 UTC
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
|    FRESH |    4 |   14.7 | 0.0% | 0.443 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   36.8 | 0.0% | 0.394 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    1 |   65.3 | 0.0% | 0.558 | 0.0 |        1 |    - |   0.0% |    - |   - |   1.0000 |
|      ALL |    8 |   29.3 | 0.0% | 0.439 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   14.7 | 0.0% | 0.397 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   36.8 | 0.0% | 0.370 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    1 |   65.3 | 0.0% | 0.561 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    8 |   29.3 | 0.0% | 0.407 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   14.7 | 0.0% | 0.460 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   36.8 | 0.0% | 0.478 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    1 |   65.3 | 0.0% | 0.536 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    8 |   29.3 | 0.0% | 0.477 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   14.7 | 0.0% | 0.443 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   36.8 | 0.0% | 0.394 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    1 |   65.3 | 0.0% | 0.558 | 0.0 |        1 |    - |   0.0% |    - |   - |   1.0000 |
|      ALL |    8 |   29.3 | 0.0% | 0.439 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   14.7 | 0.0% | 0.397 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   36.8 | 0.0% | 0.370 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    1 |   65.3 | 0.0% | 0.561 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    8 |   29.3 | 0.0% | 0.407 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   14.7 | 0.0% | 0.460 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   36.8 | 0.0% | 0.478 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    1 |   65.3 | 0.0% | 0.536 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    8 |   29.3 | 0.0% | 0.477 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available