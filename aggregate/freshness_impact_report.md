# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (26.9%) is 2.2× the overall rate (12.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.4 | 26.9% | 0.602 | 0.4 |       25 | 100.0% |  42.9% | 1.8× | 0.0% |   0.5600 |
|       OK |   15 |   35.7 | 6.7% | 0.535 | 0.1 |       14 | 0.0% |   0.0% |    - | 9.1% |   0.2143 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.452 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.2174 |
|      ALL |   66 |   64.1 | 12.1% | 0.529 | 0.2 |       62 | 85.7% |  27.3% | 2.4× | 2.5% |   0.3548 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.4 | 0.0% | 0.498 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1600 |
|       OK |   15 |   35.7 | 0.0% | 0.413 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.369 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|      ALL |   66 |   64.1 | 0.0% | 0.430 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0968 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.4 | 3.9% | 0.611 | 0.0 |       25 | 0.0% |   0.0% |    - | 4.3% |   0.0800 |
|       OK |   15 |   35.7 | 6.7% | 0.537 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.468 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   66 |   64.1 | 3.0% | 0.540 | 0.0 |       62 | 0.0% |   0.0% |    - | 3.4% |   0.0484 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.9 | 60.0% | 0.736 | 1.0 |        9 | 100.0% |  83.3% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.2 | 0.0% | 0.594 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.0 | 0.0% | 0.489 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2667 |
|      ALL |   31 |   96.5 | 19.4% | 0.583 | 0.3 |       27 | 100.0% |  50.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.9 | 0.0% | 0.648 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   36.2 | 0.0% | 0.450 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.0 | 0.0% | 0.383 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   96.5 | 0.0% | 0.477 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.9 | 10.0% | 0.717 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    4 |   36.2 | 0.0% | 0.541 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.0 | 0.0% | 0.481 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   96.5 | 3.2% | 0.565 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available