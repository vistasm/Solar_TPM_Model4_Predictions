# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.3× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.1%) is 2.1× the overall rate (6.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 31.1% | 0.650 | 0.6 |       60 | 73.7% |  48.3% | 1.5× | 16.1% |   0.4833 |
|       OK |   30 |   36.7 | 6.7% | 0.519 | 0.1 |       28 | 0.0% |   0.0% |    - | 8.3% |   0.1429 |
| DEGRADED |   50 |  117.3 | 10.0% | 0.500 | 0.1 |       49 | 20.0% |   8.3% | 0.8× | 10.8% |   0.2449 |
|      ALL |  141 |   54.7 | 18.4% | 0.569 | 0.3 |      137 | 57.7% |  33.3% | 1.8× | 12.0% |   0.3285 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 3.3% | 0.557 | 0.0 |       60 | 100.0% |  18.2% | 5.5× | 0.0% |   0.1833 |
|       OK |   30 |   36.7 | 0.0% | 0.358 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  117.3 | 0.0% | 0.381 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  141 |   54.7 | 1.4% | 0.452 | 0.0 |      137 | 100.0% |  14.3% | 9.8× | 0.0% |   0.1022 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 13.1% | 0.634 | 0.1 |       60 | 12.5% |  20.0% | 1.5× | 12.7% |   0.0833 |
|       OK |   30 |   36.7 | 3.3% | 0.543 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   50 |  117.3 | 0.0% | 0.507 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  141 |   54.7 | 6.4% | 0.570 | 0.1 |      137 | 11.1% |  16.7% | 2.5× | 6.1% |   0.0438 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 52.6% | 0.805 | 1.2 |       18 | 80.0% |  80.0% | 1.4× | 25.0% |   0.5556 |
|       OK |    5 |   35.0 | 0.0% | 0.562 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    7 |  113.9 | 28.6% | 0.468 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
|      ALL |   31 |   38.2 | 38.7% | 0.690 | 0.8 |       27 | 75.0% |  69.2% | 1.6× | 21.4% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 10.5% | 0.715 | 0.1 |       18 | 100.0% |  40.0% | 3.6× | 0.0% |   0.2778 |
|       OK |    5 |   35.0 | 0.0% | 0.364 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  113.9 | 0.0% | 0.323 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.2 | 6.5% | 0.570 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 31.6% | 0.696 | 0.3 |       18 | 16.7% |  50.0% | 1.5× | 31.2% |   0.1111 |
|       OK |    5 |   35.0 | 0.0% | 0.508 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  113.9 | 0.0% | 0.503 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.2 | 19.4% | 0.622 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available