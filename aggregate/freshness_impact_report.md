# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.3%) is 2.2× the overall rate (10.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 23.3% | 0.570 | 0.4 |       29 | 85.7% |  40.0% | 1.7× | 7.1% |   0.5172 |
|       OK |   19 |   35.8 | 5.3% | 0.494 | 0.1 |       18 | 0.0% |   0.0% |    - | 6.7% |   0.1667 |
| DEGRADED |   28 |  127.1 | 0.0% | 0.452 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1923 |
|      ALL |   77 |   60.0 | 10.4% | 0.508 | 0.2 |       73 | 75.0% |  26.1% | 2.4× | 4.0% |   0.3151 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 0.0% | 0.476 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   19 |   35.8 | 0.0% | 0.375 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   28 |  127.1 | 0.0% | 0.364 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   77 |   60.0 | 0.0% | 0.410 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0822 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 3.3% | 0.599 | 0.0 |       29 | 0.0% |   0.0% |    - | 3.7% |   0.0690 |
|       OK |   19 |   35.8 | 5.3% | 0.538 | 0.1 |       18 | 0.0% |      - |    - | 5.6% |   0.0000 |
| DEGRADED |   28 |  127.1 | 0.0% | 0.477 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
|      ALL |   77 |   60.0 | 2.6% | 0.540 | 0.0 |       73 | 0.0% |   0.0% |    - | 2.9% |   0.0411 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.4 | 38.5% | 0.609 | 0.7 |       12 | 80.0% |  66.7% | 1.6× | 16.7% |   0.5000 |
|       OK |    8 |   36.2 | 0.0% | 0.468 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.5 | 0.0% | 0.521 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   36.3 | 16.1% | 0.544 | 0.3 |       27 | 80.0% |  50.0% | 2.7× | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.4 | 0.0% | 0.529 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    8 |   36.2 | 0.0% | 0.341 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.5 | 0.0% | 0.372 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   36.3 | 0.0% | 0.430 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.4 | 7.7% | 0.651 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.541 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.5 | 0.0% | 0.560 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.3 | 3.2% | 0.593 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available