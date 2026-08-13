# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-13 UTC
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
| DEGRADED |   60 |  120.6 | 10.0% | 0.497 | 0.1 |       58 | 16.7% |   7.1% | 0.7× | 11.4% |   0.2414 |
|      ALL |  155 |   59.4 | 17.4% | 0.563 | 0.3 |      152 | 55.6% |  31.9% | 1.8× | 11.4% |   0.3092 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   33 |   36.6 | 0.0% | 0.368 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   60 |  120.6 | 0.0% | 0.381 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0517 |
|      ALL |  155 |   59.4 | 1.3% | 0.450 | 0.0 |      152 | 100.0% |  14.3% | 10.9× | 0.0% |   0.0921 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   33 |   36.6 | 3.0% | 0.544 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   60 |  120.6 | 0.0% | 0.512 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0172 |
|      ALL |  155 |   59.4 | 5.8% | 0.567 | 0.1 |      152 | 11.1% |  16.7% | 2.8× | 5.5% |   0.0395 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.1 | 42.9% | 0.724 | 0.4 |        7 | 66.7% | 100.0% | 2.3× | 20.0% |   0.2857 |
|       OK |    7 |   36.8 | 0.0% | 0.513 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  122.3 | 6.7% | 0.418 | 0.1 |       13 | 0.0% |   0.0% |    - | 10.0% |   0.2308 |
|      ALL |   29 |   75.6 | 13.8% | 0.515 | 0.1 |       26 | 50.0% |  40.0% | 2.6× | 9.5% |   0.1923 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.1 | 0.0% | 0.682 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.8 | 0.0% | 0.380 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  122.3 | 0.0% | 0.307 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.6 | 0.0% | 0.415 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.1 | 0.0% | 0.517 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.8 | 0.0% | 0.502 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  122.3 | 0.0% | 0.487 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.6 | 0.0% | 0.498 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available