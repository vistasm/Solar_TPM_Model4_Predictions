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

🟢 **M+**: FRESH precision (70.8%) is 32.4% HIGHER than DEGRADED (38.5%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.8× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.5× the overall rate (4.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   98 |  120.0 | 13.3% | 0.461 | 0.1 |       98 | 38.5% |  23.8% | 1.8× | 10.4% |   0.2143 |
|      ALL |  217 |   65.7 | 18.4% | 0.527 | 0.3 |      217 | 55.0% |  36.1% | 2.0× | 11.5% |   0.2811 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   98 |  120.0 | 0.0% | 0.365 | 0.0 |       98 |    - |   0.0% |    - | 0.0% |   0.0510 |
|      ALL |  217 |   65.7 | 0.9% | 0.437 | 0.0 |      217 | 100.0% |  11.1% | 12.1× | 0.0% |   0.0829 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   98 |  120.0 | 0.0% | 0.493 | 0.0 |       98 |    - |   0.0% |    - | 0.0% |   0.0102 |
|      ALL |  217 |   65.7 | 4.2% | 0.542 | 0.0 |      217 | 11.1% |  16.7% | 4.0× | 3.8% |   0.0277 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   13 |  107.4 | 46.2% | 0.511 | 0.5 |       13 | 50.0% |  60.0% | 1.3× | 37.5% |   0.3846 |
|      ALL |   13 |  107.4 | 46.2% | 0.511 | 0.5 |       13 | 50.0% |  60.0% | 1.3× | 37.5% |   0.3846 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   13 |  107.4 | 0.0% | 0.492 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   13 |  107.4 | 0.0% | 0.492 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   13 |  107.4 | 0.0% | 0.562 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   13 |  107.4 | 0.0% | 0.562 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available