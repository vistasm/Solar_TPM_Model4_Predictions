# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 57.0% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.5× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.2× the overall rate (5.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   33 |   36.6 | 6.1% | 0.519 | 0.1 |       32 | 0.0% |   0.0% |    - | 7.1% |   0.1250 |
| DEGRADED |   59 |  121.6 | 10.2% | 0.500 | 0.1 |       57 | 16.7% |   7.1% | 0.7× | 11.6% |   0.2456 |
|      ALL |  154 |   59.3 | 17.5% | 0.565 | 0.3 |      151 | 55.6% |  31.9% | 1.8× | 11.5% |   0.3113 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   33 |   36.6 | 0.0% | 0.368 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |  121.6 | 0.0% | 0.381 | 0.0 |       57 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |  154 |   59.3 | 1.3% | 0.450 | 0.0 |      151 | 100.0% |  14.3% | 10.8× | 0.0% |   0.0927 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   33 |   36.6 | 3.0% | 0.544 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   59 |  121.6 | 0.0% | 0.512 | 0.0 |       57 |    - |   0.0% |    - | 0.0% |   0.0175 |
|      ALL |  154 |   59.3 | 5.8% | 0.567 | 0.1 |      151 | 11.1% |  16.7% | 2.8× | 5.5% |   0.0397 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.0 | 37.5% | 0.714 | 0.4 |        8 | 66.7% | 100.0% | 2.7× | 16.7% |   0.2500 |
|       OK |    7 |   36.8 | 0.0% | 0.513 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.5 | 7.1% | 0.424 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
|      ALL |   29 |   74.1 | 13.8% | 0.525 | 0.1 |       26 | 50.0% |  40.0% | 2.6× | 9.5% |   0.1923 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.0 | 0.0% | 0.654 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.8 | 0.0% | 0.380 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.5 | 0.0% | 0.301 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   74.1 | 0.0% | 0.417 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.0 | 0.0% | 0.521 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.8 | 0.0% | 0.502 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.5 | 0.0% | 0.485 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   74.1 | 0.0% | 0.499 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available