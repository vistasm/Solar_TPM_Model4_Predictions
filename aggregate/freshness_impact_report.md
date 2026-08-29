# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.7%) is 44.2% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.9%) is 2.4× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.4%) is 2.2× the overall rate (5.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 34.3% | 0.663 | 0.6 |       68 | 72.7% |  50.0% | 1.6× | 16.7% |   0.4706 |
|       OK |   37 |   36.9 | 8.1% | 0.535 | 0.1 |       36 | 0.0% |   0.0% |    - | 6.5% |   0.1389 |
| DEGRADED |   63 |  118.2 | 11.1% | 0.501 | 0.1 |       62 | 28.6% |  13.3% | 1.2× | 10.6% |   0.2419 |
|      ALL |  170 |   56.9 | 20.0% | 0.575 | 0.3 |      166 | 58.1% |  34.6% | 1.9× | 11.4% |   0.3133 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 2.9% | 0.583 | 0.0 |       68 | 100.0% |  15.4% | 5.2× | 0.0% |   0.1912 |
|       OK |   37 |   36.9 | 0.0% | 0.399 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   63 |  118.2 | 0.0% | 0.387 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  170 |   56.9 | 1.2% | 0.470 | 0.0 |      166 | 100.0% |  12.5% | 10.4× | 0.0% |   0.0964 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.2 | 11.4% | 0.630 | 0.1 |       68 | 12.5% |  20.0% | 1.7× | 11.1% |   0.0735 |
|       OK |   37 |   36.9 | 2.7% | 0.549 | 0.0 |       36 | 0.0% |      - |    - | 2.8% |   0.0000 |
| DEGRADED |   63 |  118.2 | 0.0% | 0.515 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  170 |   56.9 | 5.3% | 0.570 | 0.1 |      166 | 11.1% |  16.7% | 3.1× | 5.0% |   0.0361 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 55.6% | 0.746 | 0.6 |        7 | 66.7% |  66.7% | 1.6× | 25.0% |   0.4286 |
|       OK |    6 |   39.0 | 16.7% | 0.618 | 0.2 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |   13 |  121.6 | 15.4% | 0.504 | 0.1 |       12 | 50.0% |  50.0% | 3.0× | 10.0% |   0.1667 |
|      ALL |   28 |   68.6 | 28.6% | 0.606 | 0.3 |       24 | 60.0% |  50.0% | 2.4× | 11.1% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 0.0% | 0.756 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    6 |   39.0 | 0.0% | 0.604 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  121.6 | 0.0% | 0.410 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   68.6 | 0.0% | 0.562 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.7 | 0.0% | 0.605 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   39.0 | 0.0% | 0.584 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  121.6 | 0.0% | 0.543 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   68.6 | 0.0% | 0.572 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available