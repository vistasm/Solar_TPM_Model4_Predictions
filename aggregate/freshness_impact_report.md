# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.4× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.5%) is 2.1× the overall rate (4.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 31.6% | 0.631 | 0.6 |       75 | 70.8% |  48.6% | 1.5× | 17.5% |   0.4667 |
|       OK |   41 |   36.8 | 7.3% | 0.513 | 0.1 |       40 | 0.0% |   0.0% |    - | 8.6% |   0.1250 |
| DEGRADED |   66 |  116.5 | 10.6% | 0.502 | 0.1 |       64 | 28.6% |  13.3% | 1.2× | 10.2% |   0.2344 |
|      ALL |  183 |   55.4 | 18.6% | 0.558 | 0.3 |      179 | 55.9% |  34.5% | 1.8× | 12.1% |   0.3073 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 2.6% | 0.564 | 0.0 |       75 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1733 |
|       OK |   41 |   36.8 | 0.0% | 0.387 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   66 |  116.5 | 0.0% | 0.381 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  183 |   55.4 | 1.1% | 0.458 | 0.0 |      179 | 100.0% |  12.5% | 11.2× | 0.0% |   0.0894 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 10.5% | 0.614 | 0.1 |       75 | 12.5% |  20.0% | 1.9× | 10.0% |   0.0667 |
|       OK |   41 |   36.8 | 2.4% | 0.537 | 0.0 |       40 | 0.0% |      - |    - | 2.5% |   0.0000 |
| DEGRADED |   66 |  116.5 | 0.0% | 0.513 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  183 |   55.4 | 4.9% | 0.560 | 0.1 |      179 | 11.1% |  16.7% | 3.3× | 4.6% |   0.0335 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 35.7% | 0.541 | 0.4 |       13 | 60.0% |  50.0% | 1.3× | 28.6% |   0.4615 |
|       OK |    8 |   37.3 | 12.5% | 0.492 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    6 |   75.1 | 16.7% | 0.549 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
|      ALL |   28 |   33.1 | 25.0% | 0.529 | 0.2 |       24 | 57.1% |  50.0% | 1.7× | 18.8% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.578 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   37.3 | 0.0% | 0.464 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   75.1 | 0.0% | 0.378 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   33.1 | 0.0% | 0.503 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.532 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.506 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   75.1 | 0.0% | 0.522 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   33.1 | 0.0% | 0.523 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available