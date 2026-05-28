# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.3%) is 2.3× the overall rate (10.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 23.3% | 0.570 | 0.4 |       30 | 85.7% |  40.0% | 1.7× | 6.7% |   0.5000 |
|       OK |   19 |   35.8 | 5.3% | 0.494 | 0.1 |       19 | 0.0% |   0.0% |    - | 6.2% |   0.1579 |
| DEGRADED |   31 |  125.9 | 0.0% | 0.470 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   80 |   62.0 | 10.0% | 0.513 | 0.1 |       76 | 75.0% |  25.0% | 2.4× | 3.9% |   0.3158 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 0.0% | 0.476 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   19 |   35.8 | 0.0% | 0.375 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   31 |  125.9 | 0.0% | 0.361 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   80 |   62.0 | 0.0% | 0.407 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0789 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 3.3% | 0.599 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   19 |   35.8 | 5.3% | 0.538 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   31 |  125.9 | 0.0% | 0.488 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   80 |   62.0 | 2.5% | 0.542 | 0.0 |       76 | 0.0% |   0.0% |    - | 2.7% |   0.0395 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 20.0% | 0.510 | 0.3 |       10 | 50.0% |  33.3% | 1.7× | 14.3% |   0.3000 |
|       OK |    8 |   36.2 | 0.0% | 0.468 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.4 | 0.0% | 0.549 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   46.7 | 6.5% | 0.515 | 0.1 |       27 | 50.0% |  16.7% | 2.2× | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 0.0% | 0.461 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.341 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.4 | 0.0% | 0.362 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   46.7 | 0.0% | 0.389 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 0.0% | 0.586 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.541 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.4 | 0.0% | 0.566 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.7 | 0.0% | 0.566 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available