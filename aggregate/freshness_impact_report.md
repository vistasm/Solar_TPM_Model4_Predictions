# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-09 UTC
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
🟡 **X+**: FRESH alert rate (12.9%) is 2.2× the overall rate (5.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       32 | 0.0% |   0.0% |    - | 7.1% |   0.1250 |
| DEGRADED |   58 |  119.3 | 10.3% | 0.507 | 0.1 |       55 | 16.7% |   7.1% | 0.7× | 12.2% |   0.2545 |
|      ALL |  152 |   58.2 | 17.8% | 0.570 | 0.3 |      149 | 55.6% |  31.9% | 1.8× | 11.8% |   0.3154 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   58 |  119.3 | 0.0% | 0.385 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0545 |
|      ALL |  152 |   58.2 | 1.3% | 0.453 | 0.0 |      149 | 100.0% |  14.3% | 10.6× | 0.0% |   0.0940 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   58 |  119.3 | 0.0% | 0.512 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0182 |
|      ALL |  152 |   58.2 | 5.9% | 0.568 | 0.1 |      149 | 11.1% |  16.7% | 2.8× | 5.6% |   0.0403 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.6 | 27.3% | 0.707 | 0.3 |       11 | 66.7% |  66.7% | 2.4× | 12.5% |   0.2727 |
|       OK |    6 |   36.3 | 0.0% | 0.557 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  116.8 | 7.7% | 0.446 | 0.1 |       10 | 0.0% |   0.0% |    - | 14.3% |   0.3000 |
|      ALL |   30 |   63.2 | 13.3% | 0.564 | 0.1 |       27 | 50.0% |  33.3% | 2.2× | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.6 | 0.0% | 0.623 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.3 | 0.0% | 0.380 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  116.8 | 0.0% | 0.316 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   63.2 | 0.0% | 0.441 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.6 | 0.0% | 0.522 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.3 | 0.0% | 0.494 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  116.8 | 0.0% | 0.484 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   63.2 | 0.0% | 0.500 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available