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

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.6× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.3× the overall rate (4.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   84 |  124.1 | 8.3% | 0.456 | 0.1 |       84 | 28.6% |  13.3% | 1.6× | 7.2% |   0.1786 |
|      ALL |  203 |   63.6 | 16.8% | 0.530 | 0.3 |      203 | 55.9% |  34.5% | 2.1× | 10.1% |   0.2709 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   84 |  124.1 | 0.0% | 0.345 | 0.0 |       84 |    - |   0.0% |    - | 0.0% |   0.0357 |
|      ALL |  203 |   63.6 | 1.0% | 0.433 | 0.0 |      203 | 100.0% |  12.5% | 12.7× | 0.0% |   0.0788 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   84 |  124.1 | 0.0% | 0.483 | 0.0 |       84 |    - |   0.0% |    - | 0.0% |   0.0119 |
|      ALL |  203 |   63.6 | 4.4% | 0.541 | 0.0 |      203 | 11.1% |  16.7% | 3.8× | 4.1% |   0.0296 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    1 |  251.1 | 0.0% | 0.174 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    1 |  251.1 | 0.0% | 0.174 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    1 |  251.1 | 0.0% | 0.099 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    1 |  251.1 | 0.0% | 0.099 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    1 |  251.1 | 0.0% | 0.326 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    1 |  251.1 | 0.0% | 0.326 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available