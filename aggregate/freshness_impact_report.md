# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.3%) is 2.2× the overall rate (10.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 23.3% | 0.570 | 0.4 |       29 | 85.7% |  40.0% | 1.7× | 7.1% |   0.5172 |
|       OK |   19 |   35.8 | 5.3% | 0.494 | 0.1 |       17 | 0.0% |   0.0% |    - | 7.1% |   0.1765 |
| DEGRADED |   27 |  129.3 | 0.0% | 0.441 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1923 |
|      ALL |   76 |   59.9 | 10.5% | 0.505 | 0.2 |       72 | 75.0% |  26.1% | 2.4× | 4.1% |   0.3194 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 0.0% | 0.476 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   19 |   35.8 | 0.0% | 0.375 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   27 |  129.3 | 0.0% | 0.358 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   76 |   59.9 | 0.0% | 0.409 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 3.3% | 0.599 | 0.0 |       29 | 0.0% |   0.0% |    - | 3.7% |   0.0690 |
|       OK |   19 |   35.8 | 5.3% | 0.538 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   27 |  129.3 | 0.0% | 0.473 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
|      ALL |   76 |   59.9 | 2.6% | 0.539 | 0.0 |       72 | 0.0% |   0.0% |    - | 2.9% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.8 | 42.9% | 0.630 | 0.7 |       13 | 83.3% |  71.4% | 1.6× | 16.7% |   0.5385 |
|       OK |    8 |   36.2 | 0.0% | 0.468 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.6 | 0.0% | 0.495 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   34.3 | 19.4% | 0.549 | 0.3 |       27 | 83.3% |  55.6% | 2.5× | 5.6% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.8 | 0.0% | 0.559 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   36.2 | 0.0% | 0.341 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.6 | 0.0% | 0.356 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   34.3 | 0.0% | 0.444 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.8 | 7.1% | 0.663 | 0.1 |       13 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |    8 |   36.2 | 0.0% | 0.541 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.6 | 0.0% | 0.554 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.3 | 3.2% | 0.600 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available