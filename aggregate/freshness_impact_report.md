# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-10 UTC
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
|       OK |    1 |   36.2 | 0.0% | 0.426 | 0.0 |        0 |    - |      - |    - |   - |        - |
|      ALL |    1 |   36.2 | 0.0% | 0.426 | 0.0 |        0 |    - |      - |    - |   - |        - |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|       OK |    1 |   36.2 | 0.0% | 0.398 | 0.0 |        0 |    - |      - |    - |   - |        - |
|      ALL |    1 |   36.2 | 0.0% | 0.398 | 0.0 |        0 |    - |      - |    - |   - |        - |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|       OK |    1 |   36.2 | 0.0% | 0.443 | 0.0 |        0 |    - |      - |    - |   - |        - |
|      ALL |    1 |   36.2 | 0.0% | 0.443 | 0.0 |        0 |    - |      - |    - |   - |        - |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|       OK |    1 |   36.2 | 0.0% | 0.426 | 0.0 |        0 |    - |      - |    - |   - |        - |
|      ALL |    1 |   36.2 | 0.0% | 0.426 | 0.0 |        0 |    - |      - |    - |   - |        - |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|       OK |    1 |   36.2 | 0.0% | 0.398 | 0.0 |        0 |    - |      - |    - |   - |        - |
|      ALL |    1 |   36.2 | 0.0% | 0.398 | 0.0 |        0 |    - |      - |    - |   - |        - |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|       OK |    1 |   36.2 | 0.0% | 0.443 | 0.0 |        0 |    - |      - |    - |   - |        - |
|      ALL |    1 |   36.2 | 0.0% | 0.443 | 0.0 |        0 |    - |      - |    - |   - |        - |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available