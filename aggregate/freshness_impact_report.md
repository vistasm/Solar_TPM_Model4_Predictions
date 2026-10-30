# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 30.8% HIGHER than DEGRADED (40.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.9× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.6× the overall rate (4.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  102 |  119.0 | 14.7% | 0.473 | 0.1 |      102 | 40.0% |  27.3% | 1.9× | 11.2% |   0.2157 |
|      ALL |  221 |   66.2 | 19.0% | 0.532 | 0.3 |      221 | 54.8% |  37.1% | 1.9× | 11.9% |   0.2805 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  102 |  119.0 | 0.0% | 0.382 | 0.0 |      102 |    - |   0.0% |    - | 0.0% |   0.0490 |
|      ALL |  221 |   66.2 | 0.9% | 0.443 | 0.0 |      221 | 100.0% |  11.1% | 12.3× | 0.0% |   0.0814 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  102 |  119.0 | 0.0% | 0.500 | 0.0 |      102 |    - |   0.0% |    - | 0.0% |   0.0098 |
|      ALL |  221 |   66.2 | 4.1% | 0.544 | 0.0 |      221 | 11.1% |  16.7% | 4.1× | 3.7% |   0.0271 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |  104.6 | 47.1% | 0.576 | 0.5 |       17 | 50.0% |  66.7% | 1.4× | 36.4% |   0.3529 |
|      ALL |   17 |  104.6 | 47.1% | 0.576 | 0.5 |       17 | 50.0% |  66.7% | 1.4× | 36.4% |   0.3529 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |  104.6 | 0.0% | 0.562 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |
|      ALL |   17 |  104.6 | 0.0% | 0.562 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |  104.6 | 0.0% | 0.582 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   17 |  104.6 | 0.0% | 0.582 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available