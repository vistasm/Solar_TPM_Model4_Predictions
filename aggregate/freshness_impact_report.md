# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.4× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.1× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       61 | 73.7% |  48.3% | 1.6× | 15.6% |   0.4754 |
|       OK |   32 |   36.5 | 6.2% | 0.527 | 0.1 |       31 | 0.0% |   0.0% |    - | 7.4% |   0.1290 |
| DEGRADED |   52 |  115.0 | 9.6% | 0.509 | 0.1 |       50 | 20.0% |   7.7% | 0.8× | 10.8% |   0.2600 |
|      ALL |  146 |   54.2 | 17.8% | 0.573 | 0.3 |      142 | 57.7% |  32.6% | 1.8× | 11.5% |   0.3239 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       61 | 100.0% |  18.2% | 5.5× | 0.0% |   0.1803 |
|       OK |   32 |   36.5 | 0.0% | 0.367 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   52 |  115.0 | 0.0% | 0.392 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  146 |   54.2 | 1.4% | 0.458 | 0.0 |      142 | 100.0% |  14.3% | 10.1× | 0.0% |   0.0986 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       61 | 12.5% |  20.0% | 1.5× | 12.5% |   0.0820 |
|       OK |   32 |   36.5 | 3.1% | 0.544 | 0.0 |       31 | 0.0% |      - |    - | 3.2% |   0.0000 |
| DEGRADED |   52 |  115.0 | 0.0% | 0.510 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  146 |   54.2 | 6.2% | 0.569 | 0.1 |      142 | 11.1% |  16.7% | 2.6× | 5.9% |   0.0423 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.3 | 41.2% | 0.766 | 0.9 |       16 | 71.4% |  71.4% | 1.6× | 22.2% |   0.4375 |
|       OK |    7 |   34.6 | 0.0% | 0.588 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    7 |   82.9 | 0.0% | 0.408 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   33.3 | 22.6% | 0.645 | 0.5 |       27 | 71.4% |  50.0% | 1.9× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.3 | 11.8% | 0.686 | 0.1 |       16 | 100.0% |  66.7% | 5.3× | 0.0% |   0.1875 |
|       OK |    7 |   34.6 | 0.0% | 0.405 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   82.9 | 0.0% | 0.302 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.3 | 6.5% | 0.536 | 0.1 |       27 | 100.0% |  66.7% | 9.0× | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.3 | 23.5% | 0.643 | 0.2 |       16 | 25.0% | 100.0% | 4.0× | 20.0% |   0.0625 |
|       OK |    7 |   34.6 | 0.0% | 0.522 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   82.9 | 0.0% | 0.444 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.3 | 12.9% | 0.571 | 0.1 |       27 | 25.0% | 100.0% | 6.8× | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available