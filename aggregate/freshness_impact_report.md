# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-31 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 2.3× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.1× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 30.6% | 0.651 | 0.6 |       61 | 73.7% |  48.3% | 1.6× | 15.6% |   0.4754 |
|       OK |   31 |   36.5 | 6.5% | 0.519 | 0.1 |       29 | 0.0% |   0.0% |    - | 8.0% |   0.1379 |
| DEGRADED |   51 |  116.1 | 9.8% | 0.504 | 0.1 |       50 | 20.0% |   7.7% | 0.8× | 10.8% |   0.2600 |
|      ALL |  144 |   54.3 | 18.1% | 0.571 | 0.3 |      140 | 57.7% |  32.6% | 1.8× | 11.7% |   0.3286 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 3.2% | 0.560 | 0.0 |       61 | 100.0% |  18.2% | 5.5× | 0.0% |   0.1803 |
|       OK |   31 |   36.5 | 0.0% | 0.359 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   51 |  116.1 | 0.0% | 0.388 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  144 |   54.3 | 1.4% | 0.456 | 0.0 |      140 | 100.0% |  14.3% | 10.0× | 0.0% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.2 | 12.9% | 0.632 | 0.1 |       61 | 12.5% |  20.0% | 1.5× | 12.5% |   0.0820 |
|       OK |   31 |   36.5 | 3.2% | 0.543 | 0.0 |       29 | 0.0% |      - |    - | 3.5% |   0.0000 |
| DEGRADED |   51 |  116.1 | 0.0% | 0.509 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  144 |   54.3 | 6.2% | 0.569 | 0.1 |      140 | 11.1% |  16.7% | 2.6× | 6.0% |   0.0429 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.7 | 47.4% | 0.790 | 1.1 |       18 | 77.8% |  77.8% | 1.6× | 22.2% |   0.5000 |
|       OK |    6 |   34.3 | 0.0% | 0.558 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.352 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   30.5 | 29.0% | 0.660 | 0.7 |       27 | 77.8% |  58.3% | 1.8× | 13.3% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.7 | 10.5% | 0.713 | 0.1 |       18 | 100.0% |  50.0% | 4.5× | 0.0% |   0.2222 |
|       OK |    6 |   34.3 | 0.0% | 0.367 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.257 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.5 | 6.5% | 0.558 | 0.1 |       27 | 100.0% |  50.0% | 6.8× | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.7 | 31.6% | 0.679 | 0.3 |       18 | 16.7% | 100.0% | 3.0× | 29.4% |   0.0556 |
|       OK |    6 |   34.3 | 0.0% | 0.513 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.423 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.5 | 19.4% | 0.598 | 0.2 |       27 | 16.7% | 100.0% | 4.5× | 19.2% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available