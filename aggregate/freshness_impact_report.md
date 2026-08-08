# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 57.0% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.4× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.2× the overall rate (6.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       32 | 0.0% |   0.0% |    - | 7.1% |   0.1250 |
| DEGRADED |   57 |  117.4 | 10.5% | 0.513 | 0.1 |       54 | 16.7% |   7.1% | 0.6× | 12.5% |   0.2593 |
|      ALL |  151 |   57.1 | 17.9% | 0.572 | 0.3 |      148 | 55.6% |  31.9% | 1.8× | 11.9% |   0.3176 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   57 |  117.4 | 0.0% | 0.391 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |  151 |   57.1 | 1.3% | 0.456 | 0.0 |      148 | 100.0% |  14.3% | 10.6× | 0.0% |   0.0946 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   57 |  117.4 | 0.0% | 0.513 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0185 |
|      ALL |  151 |   57.1 | 6.0% | 0.568 | 0.1 |      148 | 11.1% |  16.7% | 2.7× | 5.6% |   0.0405 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.4 | 25.0% | 0.699 | 0.2 |       12 | 66.7% |  66.7% | 2.7× | 11.1% |   0.2500 |
|       OK |    6 |   36.3 | 0.0% | 0.557 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  107.5 | 8.3% | 0.469 | 0.1 |        9 | 0.0% |   0.0% |    - | 16.7% |   0.3333 |
|      ALL |   30 |   56.0 | 13.3% | 0.579 | 0.1 |       27 | 50.0% |  33.3% | 2.2× | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.4 | 0.0% | 0.609 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.3 | 0.0% | 0.380 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  107.5 | 0.0% | 0.335 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   56.0 | 0.0% | 0.454 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.4 | 0.0% | 0.527 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.3 | 0.0% | 0.494 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  107.5 | 0.0% | 0.485 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   56.0 | 0.0% | 0.503 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available