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

🟢 **M+**: FRESH precision (70.8%) is 35.5% HIGHER than DEGRADED (35.3%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.9× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.6× the overall rate (4.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  104 |  118.6 | 16.4% | 0.480 | 0.2 |      104 | 35.3% |  27.3% | 1.7× | 13.4% |   0.2115 |
|      ALL |  223 |   66.5 | 19.7% | 0.535 | 0.3 |      223 | 52.3% |  37.1% | 1.9× | 13.0% |   0.2780 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  104 |  118.6 | 0.0% | 0.387 | 0.0 |      104 |    - |   0.0% |    - | 0.0% |   0.0481 |
|      ALL |  223 |   66.5 | 0.9% | 0.445 | 0.0 |      223 | 100.0% |  11.1% | 12.4× | 0.0% |   0.0807 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  104 |  118.6 | 0.0% | 0.502 | 0.0 |      104 |    - |   0.0% |    - | 0.0% |   0.0096 |
|      ALL |  223 |   66.5 | 4.0% | 0.544 | 0.0 |      223 | 11.1% |  16.7% | 4.1× | 3.7% |   0.0269 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   19 |  103.6 | 52.6% | 0.603 | 0.5 |       19 | 40.0% |  66.7% | 1.3× | 46.2% |   0.3158 |
|      ALL |   19 |  103.6 | 52.6% | 0.603 | 0.5 |       19 | 40.0% |  66.7% | 1.3× | 46.2% |   0.3158 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   19 |  103.6 | 0.0% | 0.571 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1053 |
|      ALL |   19 |  103.6 | 0.0% | 0.571 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1053 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   19 |  103.6 | 0.0% | 0.586 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |  103.6 | 0.0% | 0.586 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available