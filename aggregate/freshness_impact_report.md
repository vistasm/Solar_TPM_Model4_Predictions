# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.7%) is 2.4× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.8%) is 2.1× the overall rate (5.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.1 | 32.4% | 0.642 | 0.6 |       72 | 70.8% |  50.0% | 1.5× | 18.4% |   0.4722 |
|       OK |   39 |   36.4 | 7.7% | 0.524 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.8% |   0.1282 |
| DEGRADED |   64 |  117.6 | 10.9% | 0.502 | 0.1 |       64 | 28.6% |  13.3% | 1.2× | 10.2% |   0.2344 |
|      ALL |  177 |   55.6 | 19.2% | 0.565 | 0.3 |      175 | 55.9% |  35.2% | 1.8× | 12.4% |   0.3086 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.1 | 2.7% | 0.575 | 0.0 |       72 | 100.0% |  15.4% | 5.5× | 0.0% |   0.1806 |
|       OK |   39 |   36.4 | 0.0% | 0.392 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.384 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  177 |   55.6 | 1.1% | 0.466 | 0.0 |      175 | 100.0% |  12.5% | 10.9× | 0.0% |   0.0914 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.1 | 10.8% | 0.620 | 0.1 |       72 | 12.5% |  20.0% | 1.8× | 10.4% |   0.0694 |
|       OK |   39 |   36.4 | 2.6% | 0.544 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.515 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  177 |   55.6 | 5.1% | 0.566 | 0.1 |      175 | 11.1% |  16.7% | 3.2× | 4.7% |   0.0343 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.7 | 41.7% | 0.594 | 0.4 |       10 | 60.0% |  60.0% | 1.2× | 40.0% |   0.5000 |
|       OK |    7 |   35.9 | 14.3% | 0.511 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    8 |  129.9 | 12.5% | 0.386 | 0.1 |        8 | 100.0% | 100.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   27 |   53.0 | 25.9% | 0.511 | 0.3 |       25 | 57.1% |  57.1% | 2.0× | 16.7% |   0.2800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.7 | 0.0% | 0.651 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    7 |   35.9 | 0.0% | 0.501 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  129.9 | 0.0% | 0.299 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   53.0 | 0.0% | 0.508 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.7 | 0.0% | 0.558 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   35.9 | 0.0% | 0.548 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  129.9 | 0.0% | 0.532 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   53.0 | 0.0% | 0.548 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available