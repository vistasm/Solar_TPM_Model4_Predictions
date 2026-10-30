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
| DEGRADED |  106 |  118.2 | 17.0% | 0.486 | 0.2 |      106 | 38.9% |  30.4% | 1.8× | 13.2% |   0.2170 |
|      ALL |  225 |   66.7 | 20.0% | 0.537 | 0.3 |      225 | 53.3% |  38.1% | 1.9× | 13.0% |   0.2800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  106 |  118.2 | 0.0% | 0.392 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0472 |
|      ALL |  225 |   66.7 | 0.9% | 0.447 | 0.0 |      225 | 100.0% |  11.1% | 12.5× | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  106 |  118.2 | 0.0% | 0.506 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0094 |
|      ALL |  225 |   66.7 | 4.0% | 0.546 | 0.0 |      225 | 11.1% |  16.7% | 4.2× | 3.6% |   0.0267 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   21 |  102.8 | 52.4% | 0.621 | 0.5 |       21 | 45.5% |  71.4% | 1.4× | 42.9% |   0.3333 |
|      ALL |   21 |  102.8 | 52.4% | 0.621 | 0.5 |       21 | 45.5% |  71.4% | 1.4× | 42.9% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   21 |  102.8 | 0.0% | 0.578 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0952 |
|      ALL |   21 |  102.8 | 0.0% | 0.578 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0952 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   21 |  102.8 | 0.0% | 0.598 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   21 |  102.8 | 0.0% | 0.598 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available