# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (64.3%) is 22.2% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.4%) is 2.7× the overall rate (3.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 32.9% | 0.629 | 0.5 |       85 | 64.3% |  48.6% | 1.5× | 20.8% |   0.4353 |
|       OK |   48 |   36.3 | 10.4% | 0.519 | 0.1 |       48 | 20.0% |  14.3% | 1.4× | 9.8% |   0.1458 |
| DEGRADED |  128 |  117.1 | 14.8% | 0.454 | 0.1 |      124 | 42.1% |  32.0% | 2.1× | 11.1% |   0.2016 |
|      ALL |  261 |   68.1 | 19.9% | 0.523 | 0.3 |      257 | 51.9% |  39.1% | 1.9× | 13.3% |   0.2685 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 2.4% | 0.567 | 0.0 |       85 | 100.0% |  15.4% | 6.5× | 0.0% |   0.1529 |
|       OK |   48 |   36.3 | 0.0% | 0.399 | 0.0 |       48 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  128 |  117.1 | 0.0% | 0.369 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0403 |
|      ALL |  261 |   68.1 | 0.8% | 0.439 | 0.0 |      257 | 100.0% |  11.1% | 14.3× | 0.0% |   0.0700 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 9.4% | 0.606 | 0.1 |       85 | 12.5% |  20.0% | 2.1× | 8.8% |   0.0588 |
|       OK |   48 |   36.3 | 2.1% | 0.534 | 0.0 |       48 | 0.0% |      - |    - | 2.1% |   0.0000 |
| DEGRADED |  128 |  117.1 | 0.0% | 0.487 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  261 |   68.1 | 3.5% | 0.535 | 0.0 |      257 | 11.1% |  16.7% | 4.8× | 3.2% |   0.0233 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 50.0% | 0.689 | 0.5 |        8 | 25.0% |  50.0% | 1.0× | 50.0% |   0.2500 |
|       OK |    6 |   33.1 | 33.3% | 0.602 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   17 |  117.1 | 5.9% | 0.273 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   73.3 | 22.6% | 0.444 | 0.2 |       27 | 42.9% |  50.0% | 1.9× | 19.1% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.667 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.508 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  117.1 | 0.0% | 0.217 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   73.3 | 0.0% | 0.390 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.581 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.545 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  117.1 | 0.0% | 0.390 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   73.3 | 0.0% | 0.469 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available