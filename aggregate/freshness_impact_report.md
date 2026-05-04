# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-04 UTC
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
|    FRESH |   24 |   12.2 | 25.0% | 0.610 | 0.4 |       22 | 100.0% |  46.2% | 1.7× | 0.0% |   0.5909 |
|       OK |   12 |   35.9 | 8.3% | 0.529 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.437 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   56 |   67.1 | 12.5% | 0.531 | 0.2 |       52 | 85.7% |  31.6% | 2.4× | 3.0% |   0.3654 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 0.0% | 0.510 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   12 |   35.9 | 0.0% | 0.400 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.364 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   56 |   67.1 | 0.0% | 0.434 | 0.0 |       52 |    - |   0.0% |    - | 0.0% |   0.0962 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 4.2% | 0.615 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   12 |   35.9 | 8.3% | 0.534 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.444 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   56 |   67.1 | 3.6% | 0.537 | 0.0 |       52 | 0.0% |   0.0% |    - | 4.1% |   0.0577 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.0 | 45.5% | 0.730 | 0.8 |        9 | 100.0% |  83.3% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.0 | 0.0% | 0.567 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.468 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   95.0 | 16.1% | 0.574 | 0.3 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.0 | 0.0% | 0.645 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   36.0 | 0.0% | 0.368 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.354 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.0 | 0.0% | 0.459 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.0 | 9.1% | 0.683 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    4 |   36.0 | 0.0% | 0.467 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.437 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.0 | 3.2% | 0.528 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available