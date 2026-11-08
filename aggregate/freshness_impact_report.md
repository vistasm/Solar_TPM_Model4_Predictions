# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 31.9% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.5%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.1%) is 2.7× the overall rate (3.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.3 | 32.9% | 0.629 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   43 |   36.7 | 9.3% | 0.515 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  122 |  118.7 | 14.8% | 0.462 | 0.1 |      121 | 38.9% |  30.4% | 2.0× | 11.2% |   0.1901 |
|      ALL |  244 |   69.8 | 19.7% | 0.526 | 0.3 |      240 | 53.3% |  38.1% | 2.0× | 11.9% |   0.2625 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.3 | 2.5% | 0.567 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   43 |   36.7 | 0.0% | 0.396 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.375 | 0.0 |      121 |    - |   0.0% |    - | 0.0% |   0.0413 |
|      ALL |  244 |   69.8 | 0.8% | 0.441 | 0.0 |      240 | 100.0% |  11.1% | 13.3× | 0.0% |   0.0750 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   79 |   12.3 | 10.1% | 0.610 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   43 |   36.7 | 2.3% | 0.534 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.491 | 0.0 |      121 |    - |   0.0% |    - | 0.0% |   0.0083 |
|      ALL |  244 |   69.8 | 3.7% | 0.537 | 0.0 |      240 | 11.1% |  16.7% | 4.4× | 3.4% |   0.0250 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   10.7 | 100.0% | 0.877 | 1.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   34.8 | 100.0% | 0.845 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  110.7 | 32.1% | 0.532 | 0.3 |       27 | 44.4% | 100.0% | 3.0× | 21.7% |   0.1481 |
|      ALL |   31 |  101.8 | 38.7% | 0.564 | 0.4 |       27 | 44.4% | 100.0% | 3.0× | 21.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   10.7 | 0.0% | 0.958 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   34.8 | 0.0% | 0.912 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  110.7 | 0.0% | 0.485 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   31 |  101.8 | 0.0% | 0.529 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   10.7 | 0.0% | 0.653 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   34.8 | 0.0% | 0.593 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  110.7 | 0.0% | 0.542 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  101.8 | 0.0% | 0.551 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available