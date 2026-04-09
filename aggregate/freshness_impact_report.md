# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-09 UTC
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
|    FRESH |   15 |   12.9 | 6.7% | 0.520 | 0.1 |       15 | 100.0% |  12.5% | 1.9× | 0.0% |   0.5333 |
|       OK |   10 |   34.7 | 10.0% | 0.543 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    6 |   79.3 | 0.0% | 0.404 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   32.8 | 6.5% | 0.505 | 0.1 |       27 | 50.0% |   9.1% | 1.2× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.419 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   10 |   34.7 | 0.0% | 0.418 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.3 | 0.0% | 0.370 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.8 | 0.0% | 0.409 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.549 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|       OK |   10 |   34.7 | 10.0% | 0.556 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    6 |   79.3 | 0.0% | 0.488 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.8 | 3.2% | 0.540 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 6.7% | 0.520 | 0.1 |       15 | 100.0% |  12.5% | 1.9× | 0.0% |   0.5333 |
|       OK |   10 |   34.7 | 10.0% | 0.543 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
| DEGRADED |    6 |   79.3 | 0.0% | 0.404 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   32.8 | 6.5% | 0.505 | 0.1 |       27 | 50.0% |   9.1% | 1.2× | 6.2% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.419 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   10 |   34.7 | 0.0% | 0.418 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.3 | 0.0% | 0.370 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.8 | 0.0% | 0.409 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.9 | 0.0% | 0.549 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|       OK |   10 |   34.7 | 10.0% | 0.556 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    6 |   79.3 | 0.0% | 0.488 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.8 | 3.2% | 0.540 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available