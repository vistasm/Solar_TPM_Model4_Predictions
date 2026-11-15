# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 24.6% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.8%) is 2.7× the overall rate (3.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.1 | 34.2% | 0.633 | 0.6 |       80 | 66.7% |  50.0% | 1.5× | 20.4% |   0.4500 |
|       OK |   45 |   36.5 | 11.1% | 0.529 | 0.1 |       44 | 20.0% |  16.7% | 1.5× | 10.5% |   0.1364 |
| DEGRADED |  124 |  117.7 | 15.3% | 0.464 | 0.1 |      123 | 42.1% |  32.0% | 2.1× | 11.2% |   0.2033 |
|      ALL |  251 |   68.7 | 20.7% | 0.531 | 0.3 |      247 | 52.9% |  40.3% | 1.9× | 13.3% |   0.2713 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.1 | 2.4% | 0.570 | 0.0 |       80 | 100.0% |  15.4% | 6.2× | 0.0% |   0.1625 |
|       OK |   45 |   36.5 | 0.0% | 0.407 | 0.0 |       44 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.378 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0406 |
|      ALL |  251 |   68.7 | 0.8% | 0.446 | 0.0 |      247 | 100.0% |  11.1% | 13.7× | 0.0% |   0.0729 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.1 | 9.8% | 0.612 | 0.1 |       80 | 12.5% |  20.0% | 2.0× | 9.3% |   0.0625 |
|       OK |   45 |   36.5 | 2.2% | 0.543 | 0.0 |       44 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.492 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  251 |   68.7 | 3.6% | 0.540 | 0.0 |      247 | 11.1% |  16.7% | 4.6× | 3.3% |   0.0243 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.6 | 80.0% | 0.784 | 0.8 |        3 | 33.3% | 100.0% | 1.0× | 100.0% |   0.3333 |
|       OK |    3 |   33.9 | 66.7% | 0.838 | 0.7 |        2 | 50.0% | 100.0% | 1.0× | 100.0% |   0.5000 |
| DEGRADED |   23 |  110.8 | 21.7% | 0.439 | 0.2 |       22 | 60.0% |  75.0% | 3.3× | 11.1% |   0.1818 |
|      ALL |   31 |   87.0 | 35.5% | 0.533 | 0.3 |       27 | 50.0% |  83.3% | 2.2× | 23.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.6 | 0.0% | 0.777 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   33.9 | 0.0% | 0.733 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  110.8 | 0.0% | 0.377 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   87.0 | 0.0% | 0.476 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |    9.6 | 0.0% | 0.664 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   33.9 | 0.0% | 0.684 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  110.8 | 0.0% | 0.467 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   87.0 | 0.0% | 0.520 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available