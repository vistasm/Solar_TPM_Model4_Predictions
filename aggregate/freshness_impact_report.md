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

🟢 **M+**: FRESH precision (70.8%) is 35.1% HIGHER than DEGRADED (35.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.9× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.5× the overall rate (4.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  101 |  119.3 | 13.9% | 0.470 | 0.1 |      101 | 35.7% |  23.8% | 1.7× | 11.2% |   0.2079 |
|      ALL |  220 |   66.1 | 18.6% | 0.531 | 0.3 |      220 | 53.7% |  36.1% | 1.9× | 11.9% |   0.2773 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  101 |  119.3 | 0.0% | 0.378 | 0.0 |      101 |    - |   0.0% |    - | 0.0% |   0.0495 |
|      ALL |  220 |   66.1 | 0.9% | 0.441 | 0.0 |      220 | 100.0% |  11.1% | 12.2× | 0.0% |   0.0818 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  101 |  119.3 | 0.0% | 0.498 | 0.0 |      101 |    - |   0.0% |    - | 0.0% |   0.0099 |
|      ALL |  220 |   66.1 | 4.1% | 0.543 | 0.0 |      220 | 11.1% |  16.7% | 4.1× | 3.7% |   0.0273 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   16 |  105.1 | 43.8% | 0.560 | 0.4 |       16 | 42.9% |  60.0% | 1.4× | 36.4% |   0.3125 |
|      ALL |   16 |  105.1 | 43.8% | 0.560 | 0.4 |       16 | 42.9% |  60.0% | 1.4× | 36.4% |   0.3125 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   16 |  105.1 | 0.0% | 0.548 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   16 |  105.1 | 0.0% | 0.548 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   16 |  105.1 | 0.0% | 0.578 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   16 |  105.1 | 0.0% | 0.578 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available