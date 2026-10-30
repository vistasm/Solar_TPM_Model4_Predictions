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

🟢 **M+**: FRESH precision (70.8%) is 31.9% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.9× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.6× the overall rate (4.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  105 |  118.4 | 17.1% | 0.484 | 0.2 |      105 | 38.9% |  30.4% | 1.8× | 13.4% |   0.2190 |
|      ALL |  224 |   66.6 | 20.1% | 0.536 | 0.3 |      224 | 53.3% |  38.1% | 1.9× | 13.0% |   0.2812 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  105 |  118.4 | 0.0% | 0.390 | 0.0 |      105 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  224 |   66.6 | 0.9% | 0.446 | 0.0 |      224 | 100.0% |  11.1% | 12.4× | 0.0% |   0.0804 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  105 |  118.4 | 0.0% | 0.504 | 0.0 |      105 |    - |   0.0% |    - | 0.0% |   0.0095 |
|      ALL |  224 |   66.6 | 4.0% | 0.545 | 0.0 |      224 | 11.1% |  16.7% | 4.2× | 3.7% |   0.0268 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   20 |  103.2 | 55.0% | 0.615 | 0.6 |       20 | 45.5% |  71.4% | 1.3× | 46.2% |   0.3500 |
|      ALL |   20 |  103.2 | 55.0% | 0.615 | 0.6 |       20 | 45.5% |  71.4% | 1.3× | 46.2% |   0.3500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   20 |  103.2 | 0.0% | 0.580 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   20 |  103.2 | 0.0% | 0.580 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   20 |  103.2 | 0.0% | 0.594 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   20 |  103.2 | 0.0% | 0.594 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available