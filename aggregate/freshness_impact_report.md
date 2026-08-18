# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 57.0% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.1%) is 2.5× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.5%) is 2.2× the overall rate (5.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.2 | 29.7% | 0.650 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   34 |   36.9 | 5.9% | 0.517 | 0.1 |       33 | 0.0% |   0.0% |    - | 6.9% |   0.1212 |
| DEGRADED |   61 |  120.1 | 9.8% | 0.494 | 0.1 |       61 | 16.7% |   7.1% | 0.7× | 10.6% |   0.2295 |
|      ALL |  159 |   58.9 | 17.0% | 0.562 | 0.3 |      156 | 55.6% |  31.9% | 1.8× | 11.0% |   0.3013 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.2 | 3.1% | 0.563 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   34 |   36.9 | 0.0% | 0.376 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   61 |  120.1 | 0.0% | 0.383 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  159 |   58.9 | 1.3% | 0.454 | 0.0 |      156 | 100.0% |  14.3% | 11.1× | 0.0% |   0.0897 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.2 | 12.5% | 0.630 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   34 |   36.9 | 2.9% | 0.544 | 0.0 |       33 | 0.0% |      - |    - | 3.0% |   0.0000 |
| DEGRADED |   61 |  120.1 | 0.0% | 0.512 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0164 |
|      ALL |  159 |   58.9 | 5.7% | 0.567 | 0.1 |      156 | 11.1% |  16.7% | 2.9× | 5.3% |   0.0385 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.0 | 37.5% | 0.738 | 0.4 |        6 | 66.7% | 100.0% | 2.0× | 25.0% |   0.3333 |
|       OK |    6 |   36.4 | 0.0% | 0.549 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.4 | 7.1% | 0.443 | 0.1 |       14 | 0.0% |   0.0% |    - | 9.1% |   0.2143 |
|      ALL |   28 |   74.7 | 14.3% | 0.550 | 0.1 |       25 | 50.0% |  40.0% | 2.5× | 10.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.0 | 0.0% | 0.743 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.429 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.4 | 0.0% | 0.349 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.7 | 0.0% | 0.479 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.0 | 0.0% | 0.535 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.4 | 0.0% | 0.532 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.4 | 0.0% | 0.509 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   74.7 | 0.0% | 0.521 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available