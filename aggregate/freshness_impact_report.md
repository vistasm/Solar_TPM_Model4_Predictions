# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (71.4%) is 42.9% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.9%) is 2.4× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.4%) is 2.1× the overall rate (5.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 34.3% | 0.663 | 0.6 |       67 | 71.4% |  48.4% | 1.5× | 16.7% |   0.4627 |
|       OK |   37 |   36.9 | 8.1% | 0.535 | 0.1 |       36 | 0.0% |   0.0% |    - | 6.5% |   0.1389 |
| DEGRADED |   62 |  119.2 | 11.3% | 0.500 | 0.1 |       62 | 28.6% |  13.3% | 1.2× | 10.6% |   0.2419 |
|      ALL |  169 |   56.9 | 20.1% | 0.575 | 0.3 |      165 | 56.7% |  33.3% | 1.8× | 11.4% |   0.3091 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 2.9% | 0.583 | 0.0 |       67 | 100.0% |  16.7% | 5.6× | 0.0% |   0.1791 |
|       OK |   37 |   36.9 | 0.0% | 0.399 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.390 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  169 |   56.9 | 1.2% | 0.472 | 0.0 |      165 | 100.0% |  13.3% | 11.0× | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 11.4% | 0.630 | 0.1 |       67 | 12.5% |  20.0% | 1.7× | 11.3% |   0.0746 |
|       OK |   37 |   36.9 | 2.7% | 0.549 | 0.0 |       36 | 0.0% |      - |    - | 2.8% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.514 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  169 |   56.9 | 5.3% | 0.570 | 0.1 |      165 | 11.1% |  16.7% | 3.1× | 5.0% |   0.0364 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 55.6% | 0.746 | 0.6 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
|       OK |    7 |   37.8 | 14.3% | 0.606 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |   12 |  127.0 | 16.7% | 0.498 | 0.2 |       12 | 50.0% |  50.0% | 3.0× | 10.0% |   0.1667 |
|      ALL |   28 |   67.7 | 28.6% | 0.605 | 0.3 |       24 | 50.0% |  40.0% | 2.4× | 10.5% |   0.2083 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 0.0% | 0.756 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   37.8 | 0.0% | 0.572 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  127.0 | 0.0% | 0.427 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.7 | 0.0% | 0.569 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 0.0% | 0.605 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.8 | 0.0% | 0.578 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  127.0 | 0.0% | 0.540 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.7 | 0.0% | 0.571 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available