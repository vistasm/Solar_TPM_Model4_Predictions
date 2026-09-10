# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-10 UTC
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
🟡 **X+**: FRESH alert rate (10.5%) is 2.1× the overall rate (5.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 31.6% | 0.631 | 0.6 |       73 | 70.8% |  48.6% | 1.5× | 18.4% |   0.4795 |
|       OK |   40 |   36.6 | 7.5% | 0.518 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.8% |   0.1282 |
| DEGRADED |   64 |  117.6 | 10.9% | 0.502 | 0.1 |       64 | 28.6% |  13.3% | 1.2× | 10.2% |   0.2344 |
|      ALL |  180 |   55.1 | 18.9% | 0.560 | 0.3 |      176 | 55.9% |  34.5% | 1.8× | 12.4% |   0.3125 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 2.6% | 0.564 | 0.0 |       73 | 100.0% |  15.4% | 5.6× | 0.0% |   0.1781 |
|       OK |   40 |   36.6 | 0.0% | 0.387 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.384 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  180 |   55.1 | 1.1% | 0.461 | 0.0 |      176 | 100.0% |  12.5% | 11.0× | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 10.5% | 0.614 | 0.1 |       73 | 12.5% |  20.0% | 1.8× | 10.3% |   0.0685 |
|       OK |   40 |   36.6 | 2.5% | 0.542 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.515 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  180 |   55.1 | 5.0% | 0.563 | 0.1 |      176 | 11.1% |  16.7% | 3.3× | 4.7% |   0.0341 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 35.7% | 0.541 | 0.4 |       11 | 60.0% |  50.0% | 1.1× | 40.0% |   0.5455 |
|       OK |    8 |   36.8 | 12.5% | 0.482 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    5 |   70.9 | 20.0% | 0.522 | 0.2 |        5 | 100.0% | 100.0% | 5.0× | 0.0% |   0.2000 |
|      ALL |   27 |   30.6 | 25.9% | 0.520 | 0.3 |       23 | 57.1% |  50.0% | 1.6× | 20.0% |   0.3478 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.578 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    8 |   36.8 | 0.0% | 0.464 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   70.9 | 0.0% | 0.426 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.6 | 0.0% | 0.516 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.532 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.8 | 0.0% | 0.533 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   70.9 | 0.0% | 0.561 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.6 | 0.0% | 0.538 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available