# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.3%) is 2.3× the overall rate (10.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 23.3% | 0.570 | 0.4 |       29 | 85.7% |  40.0% | 1.7× | 7.1% |   0.5172 |
|       OK |   19 |   35.8 | 5.3% | 0.494 | 0.1 |       18 | 0.0% |   0.0% |    - | 6.7% |   0.1667 |
| DEGRADED |   29 |  125.8 | 0.0% | 0.458 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   78 |   60.4 | 10.3% | 0.510 | 0.1 |       74 | 75.0% |  25.0% | 2.3× | 4.0% |   0.3243 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 0.0% | 0.476 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   19 |   35.8 | 0.0% | 0.375 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   29 |  125.8 | 0.0% | 0.360 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   78 |   60.4 | 0.0% | 0.408 | 0.0 |       74 |    - |   0.0% |    - | 0.0% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 3.3% | 0.599 | 0.0 |       29 | 0.0% |   0.0% |    - | 3.7% |   0.0690 |
|       OK |   19 |   35.8 | 5.3% | 0.538 | 0.1 |       18 | 0.0% |      - |    - | 5.6% |   0.0000 |
| DEGRADED |   29 |  125.8 | 0.0% | 0.481 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   78 |   60.4 | 2.6% | 0.540 | 0.0 |       74 | 0.0% |   0.0% |    - | 2.8% |   0.0405 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.5 | 33.3% | 0.580 | 0.6 |       11 | 75.0% |  60.0% | 1.6× | 16.7% |   0.4545 |
|       OK |    8 |   36.2 | 0.0% | 0.468 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   69.6 | 0.0% | 0.532 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   38.9 | 12.9% | 0.534 | 0.2 |       27 | 75.0% |  37.5% | 2.5× | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.5 | 0.0% | 0.501 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   36.2 | 0.0% | 0.341 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   69.6 | 0.0% | 0.361 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   38.9 | 0.0% | 0.410 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.5 | 0.0% | 0.629 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.541 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   69.6 | 0.0% | 0.561 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.9 | 0.0% | 0.582 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available