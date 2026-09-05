# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-05 UTC
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
🟡 **X+**: FRESH alert rate (11.0%) is 2.1× the overall rate (5.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   73 |   12.1 | 32.9% | 0.646 | 0.6 |       70 | 70.8% |  51.5% | 1.5× | 18.9% |   0.4714 |
|       OK |   39 |   36.4 | 7.7% | 0.524 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.8% |   0.1282 |
| DEGRADED |   64 |  117.6 | 10.9% | 0.502 | 0.1 |       64 | 28.6% |  13.3% | 1.2× | 10.2% |   0.2344 |
|      ALL |  176 |   55.8 | 19.3% | 0.567 | 0.3 |      173 | 55.9% |  35.9% | 1.8× | 12.5% |   0.3064 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   73 |   12.1 | 2.7% | 0.579 | 0.0 |       70 | 100.0% |  15.4% | 5.4× | 0.0% |   0.1857 |
|       OK |   39 |   36.4 | 0.0% | 0.392 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.384 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  176 |   55.8 | 1.1% | 0.467 | 0.0 |      173 | 100.0% |  12.5% | 10.8× | 0.0% |   0.0925 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   73 |   12.1 | 11.0% | 0.623 | 0.1 |       70 | 12.5% |  20.0% | 1.8× | 10.8% |   0.0714 |
|       OK |   39 |   36.4 | 2.6% | 0.544 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.515 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  176 |   55.8 | 5.1% | 0.567 | 0.1 |      173 | 11.1% |  16.7% | 3.2× | 4.8% |   0.0347 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.0 | 45.5% | 0.618 | 0.5 |        8 | 60.0% |  75.0% | 1.2× | 50.0% |   0.5000 |
|       OK |    7 |   35.9 | 14.3% | 0.511 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    9 |  135.5 | 11.1% | 0.378 | 0.1 |        9 | 100.0% | 100.0% | 9.0× | 0.0% |   0.1111 |
|      ALL |   27 |   59.0 | 25.9% | 0.510 | 0.3 |       24 | 57.1% |  66.7% | 2.3× | 16.7% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.0 | 0.0% | 0.686 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    7 |   35.9 | 0.0% | 0.501 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  135.5 | 0.0% | 0.287 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   59.0 | 0.0% | 0.505 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.0 | 0.0% | 0.569 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   35.9 | 0.0% | 0.548 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  135.5 | 0.0% | 0.530 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   59.0 | 0.0% | 0.551 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available