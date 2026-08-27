# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (71.4%) is 54.8% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.9%) is 2.4× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.4%) is 2.1× the overall rate (5.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 34.3% | 0.663 | 0.6 |       67 | 71.4% |  48.4% | 1.5× | 16.7% |   0.4627 |
|       OK |   36 |   37.1 | 5.6% | 0.528 | 0.1 |       36 | 0.0% |   0.0% |    - | 6.5% |   0.1389 |
| DEGRADED |   62 |  119.2 | 11.3% | 0.500 | 0.1 |       61 | 16.7% |   7.1% | 0.7× | 10.6% |   0.2295 |
|      ALL |  168 |   57.0 | 19.6% | 0.574 | 0.3 |      164 | 55.2% |  32.0% | 1.8× | 11.4% |   0.3049 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 2.9% | 0.583 | 0.0 |       67 | 100.0% |  16.7% | 5.6× | 0.0% |   0.1791 |
|       OK |   36 |   37.1 | 0.0% | 0.391 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.390 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  168 |   57.0 | 1.2% | 0.470 | 0.0 |      164 | 100.0% |  13.3% | 10.9× | 0.0% |   0.0915 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 11.4% | 0.630 | 0.1 |       67 | 12.5% |  20.0% | 1.7× | 11.3% |   0.0746 |
|       OK |   36 |   37.1 | 2.8% | 0.547 | 0.0 |       36 | 0.0% |      - |    - | 2.8% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.514 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0164 |
|      ALL |  168 |   57.0 | 5.4% | 0.569 | 0.1 |      164 | 11.1% |  16.7% | 3.0× | 5.1% |   0.0366 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 55.6% | 0.746 | 0.6 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
|       OK |    7 |   37.1 | 0.0% | 0.576 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
| DEGRADED |   12 |  127.0 | 16.7% | 0.498 | 0.2 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|      ALL |   28 |   67.5 | 25.0% | 0.597 | 0.2 |       24 | 33.3% |  25.0% | 2.0× | 10.0% |   0.1667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 0.0% | 0.756 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   37.1 | 0.0% | 0.507 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  127.0 | 0.0% | 0.427 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.5 | 0.0% | 0.553 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 0.0% | 0.605 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.1 | 0.0% | 0.547 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  127.0 | 0.0% | 0.540 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.5 | 0.0% | 0.563 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available