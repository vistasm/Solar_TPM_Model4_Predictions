# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-05 UTC
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
|    FRESH |   15 |   12.9 | 6.7% | 0.520 | 0.1 |       11 | 100.0% |  20.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    8 |   35.8 | 12.5% | 0.509 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   27 |   30.5 | 7.4% | 0.486 | 0.1 |       23 | 50.0% |  12.5% | 1.4× | 6.7% |   0.3478 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.419 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.8 | 0.0% | 0.416 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.5 | 0.0% | 0.416 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.549 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.8 | 12.5% | 0.568 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.5 | 3.7% | 0.543 | 0.0 |       23 | 0.0% |   0.0% |    - | 4.5% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 6.7% | 0.520 | 0.1 |       11 | 100.0% |  20.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    8 |   35.8 | 12.5% | 0.509 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   27 |   30.5 | 7.4% | 0.486 | 0.1 |       23 | 50.0% |  12.5% | 1.4× | 6.7% |   0.3478 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.419 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.8 | 0.0% | 0.416 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.5 | 0.0% | 0.416 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.549 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.8 | 12.5% | 0.568 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.5 | 3.7% | 0.543 | 0.0 |       23 | 0.0% |   0.0% |    - | 4.5% |   0.0435 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available