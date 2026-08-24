# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 57.0% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.0%) is 2.5× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.9%) is 2.2× the overall rate (5.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.3 | 31.3% | 0.654 | 0.6 |       65 | 73.7% |  46.7% | 1.6× | 14.3% |   0.4615 |
|       OK |   36 |   37.1 | 5.6% | 0.528 | 0.1 |       35 | 0.0% |   0.0% |    - | 6.7% |   0.1429 |
| DEGRADED |   62 |  119.2 | 11.3% | 0.500 | 0.1 |       61 | 16.7% |   7.1% | 0.7× | 10.6% |   0.2295 |
|      ALL |  165 |   57.9 | 18.2% | 0.569 | 0.3 |      161 | 55.6% |  30.6% | 1.8× | 10.7% |   0.3043 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.3 | 3.0% | 0.571 | 0.0 |       65 | 100.0% |  16.7% | 5.4× | 0.0% |   0.1846 |
|       OK |   36 |   37.1 | 0.0% | 0.391 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.390 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  165 |   57.9 | 1.2% | 0.464 | 0.0 |      161 | 100.0% |  13.3% | 10.7× | 0.0% |   0.0932 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.3 | 11.9% | 0.629 | 0.1 |       65 | 12.5% |  20.0% | 1.6× | 11.7% |   0.0769 |
|       OK |   36 |   37.1 | 2.8% | 0.547 | 0.0 |       35 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.514 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0164 |
|      ALL |  165 |   57.9 | 5.5% | 0.568 | 0.1 |      161 | 11.1% |  16.7% | 3.0× | 5.2% |   0.0373 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.1 | 28.6% | 0.696 | 0.3 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    8 |   37.2 | 0.0% | 0.587 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
| DEGRADED |   13 |  122.1 | 15.4% | 0.513 | 0.1 |       12 | 0.0% |   0.0% |    - | 10.0% |   0.1667 |
|      ALL |   28 |   70.6 | 14.3% | 0.580 | 0.1 |       24 | 0.0% |   0.0% |    - | 5.0% |   0.1667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.1 | 0.0% | 0.684 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    8 |   37.2 | 0.0% | 0.480 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  122.1 | 0.0% | 0.420 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   70.6 | 0.0% | 0.503 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.1 | 0.0% | 0.576 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.2 | 0.0% | 0.547 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  122.1 | 0.0% | 0.543 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   70.6 | 0.0% | 0.553 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available