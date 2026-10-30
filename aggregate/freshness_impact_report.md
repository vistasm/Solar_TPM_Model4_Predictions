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

🟢 **M+**: FRESH precision (70.8%) is 37.5% HIGHER than DEGRADED (33.3%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.8× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.5× the overall rate (4.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   94 |  121.1 | 9.6% | 0.441 | 0.1 |       94 | 33.3% |  15.8% | 1.6× | 8.0% |   0.2021 |
|      ALL |  213 |   65.1 | 16.9% | 0.520 | 0.2 |      213 | 55.6% |  33.9% | 2.0× | 10.4% |   0.2770 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   94 |  121.1 | 0.0% | 0.343 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0426 |
|      ALL |  213 |   65.1 | 0.9% | 0.428 | 0.0 |      213 | 100.0% |  11.8% | 12.5× | 0.0% |   0.0798 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   94 |  121.1 | 0.0% | 0.476 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0106 |
|      ALL |  213 |   65.1 | 4.2% | 0.535 | 0.0 |      213 | 11.1% |  16.7% | 3.9× | 3.9% |   0.0282 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |  112.7 | 22.2% | 0.332 | 0.2 |        9 | 50.0% |  33.3% | 1.5× | 16.7% |   0.3333 |
|      ALL |    9 |  112.7 | 22.2% | 0.332 | 0.2 |        9 | 50.0% |  33.3% | 1.5× | 16.7% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |  112.7 | 0.0% | 0.315 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |    9 |  112.7 | 0.0% | 0.315 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |  112.7 | 0.0% | 0.412 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    9 |  112.7 | 0.0% | 0.412 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available