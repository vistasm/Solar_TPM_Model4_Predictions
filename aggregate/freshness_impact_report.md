# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.3× the overall rate (4.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   77 |  120.5 | 9.1% | 0.471 | 0.1 |       73 | 28.6% |  13.3% | 1.4× | 8.6% |   0.2055 |
|      ALL |  196 |   60.0 | 17.3% | 0.538 | 0.3 |      192 | 55.9% |  34.5% | 1.9× | 10.9% |   0.2865 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   77 |  120.5 | 0.0% | 0.357 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0411 |
|      ALL |  196 |   60.0 | 1.0% | 0.441 | 0.0 |      192 | 100.0% |  12.5% | 12.0× | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   77 |  120.5 | 0.0% | 0.492 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0137 |
|      ALL |  196 |   60.0 | 4.6% | 0.547 | 0.1 |      192 | 11.1% |  16.7% | 3.6× | 4.3% |   0.0312 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   12.8 | 12.5% | 0.300 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|       OK |    6 |   34.6 | 16.7% | 0.386 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   15 |  125.9 | 0.0% | 0.351 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.8 | 6.9% | 0.344 | 0.1 |       25 | 0.0% |   0.0% |    - | 8.7% |   0.0800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   12.8 | 0.0% | 0.365 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.6 | 0.0% | 0.340 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  125.9 | 0.0% | 0.223 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.8 | 0.0% | 0.286 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   12.8 | 0.0% | 0.426 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.6 | 0.0% | 0.445 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  125.9 | 0.0% | 0.404 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.8 | 0.0% | 0.418 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available