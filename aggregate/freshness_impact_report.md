# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.2× the overall rate (4.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       41 | 0.0% |   0.0% |    - | 8.3% |   0.1220 |
| DEGRADED |   75 |  119.9 | 9.3% | 0.475 | 0.1 |       72 | 28.6% |  13.3% | 1.4× | 8.8% |   0.2083 |
|      ALL |  194 |   59.2 | 17.5% | 0.541 | 0.3 |      190 | 55.9% |  34.5% | 1.9× | 11.1% |   0.2895 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   75 |  119.9 | 0.0% | 0.362 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |  194 |   59.2 | 1.0% | 0.444 | 0.0 |      190 | 100.0% |  12.5% | 11.9× | 0.0% |   0.0842 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   75 |  119.9 | 0.0% | 0.495 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0139 |
|      ALL |  194 |   59.2 | 4.6% | 0.548 | 0.1 |      190 | 11.1% |  16.7% | 3.5× | 4.3% |   0.0316 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 30.0% | 0.414 | 0.3 |       10 | 66.7% |  50.0% | 1.7× | 16.7% |   0.4000 |
|       OK |    6 |   34.6 | 16.7% | 0.386 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |  123.2 | 0.0% | 0.357 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.6 | 13.8% | 0.382 | 0.1 |       25 | 50.0% |  50.0% | 3.1× | 9.5% |   0.1600 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 0.0% | 0.459 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   34.6 | 0.0% | 0.340 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  123.2 | 0.0% | 0.227 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.6 | 0.0% | 0.331 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 0.0% | 0.471 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.6 | 0.0% | 0.445 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  123.2 | 0.0% | 0.407 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.6 | 0.0% | 0.437 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available