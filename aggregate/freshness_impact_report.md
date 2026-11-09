# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 31.9% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.5%) is 3.0× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.0%) is 2.7× the overall rate (3.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 33.8% | 0.634 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   43 |   36.7 | 9.3% | 0.515 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  122 |  118.7 | 14.8% | 0.462 | 0.1 |      122 | 38.9% |  29.2% | 2.0× | 11.2% |   0.1967 |
|      ALL |  245 |   69.5 | 20.0% | 0.527 | 0.3 |      241 | 53.3% |  37.5% | 2.0× | 11.9% |   0.2656 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 2.5% | 0.572 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   43 |   36.7 | 0.0% | 0.396 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.375 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0410 |
|      ALL |  245 |   69.5 | 0.8% | 0.443 | 0.0 |      241 | 100.0% |  11.1% | 13.4× | 0.0% |   0.0747 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 10.0% | 0.613 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   43 |   36.7 | 2.3% | 0.534 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.491 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0082 |
|      ALL |  245 |   69.5 | 3.7% | 0.538 | 0.0 |      241 | 11.1% |  16.7% | 4.5× | 3.4% |   0.0249 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 100.0% | 0.907 | 1.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   34.8 | 100.0% | 0.845 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   27 |  111.3 | 29.6% | 0.517 | 0.3 |       27 | 37.5% |  75.0% | 2.5× | 21.7% |   0.1481 |
|      ALL |   31 |   99.1 | 38.7% | 0.566 | 0.4 |       27 | 37.5% |  75.0% | 2.5× | 21.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 0.0% | 0.965 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   34.8 | 0.0% | 0.912 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   27 |  111.3 | 0.0% | 0.469 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   31 |   99.1 | 0.0% | 0.532 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 0.0% | 0.718 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   34.8 | 0.0% | 0.593 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   27 |  111.3 | 0.0% | 0.529 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   99.1 | 0.0% | 0.550 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available