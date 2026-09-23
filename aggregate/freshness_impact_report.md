# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-23 UTC
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
🟡 **X+**: FRESH alert rate (10.4%) is 2.2× the overall rate (4.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       76 | 70.8% |  48.6% | 1.5× | 17.1% |   0.4605 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       41 | 0.0% |   0.0% |    - | 8.3% |   0.1220 |
| DEGRADED |   74 |  120.1 | 9.5% | 0.473 | 0.1 |       72 | 28.6% |  13.3% | 1.4× | 8.8% |   0.2083 |
|      ALL |  193 |   58.9 | 17.6% | 0.540 | 0.3 |      189 | 55.9% |  34.5% | 1.9× | 11.2% |   0.2910 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       76 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1711 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   74 |  120.1 | 0.0% | 0.360 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |  193 |   58.9 | 1.0% | 0.444 | 0.0 |      189 | 100.0% |  12.5% | 11.8× | 0.0% |   0.0847 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       76 | 12.5% |  20.0% | 1.9× | 9.9% |   0.0658 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   74 |  120.1 | 0.0% | 0.496 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0139 |
|      ALL |  193 |   58.9 | 4.7% | 0.549 | 0.1 |      189 | 11.1% |  16.7% | 3.5× | 4.4% |   0.0317 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 30.0% | 0.414 | 0.3 |        9 | 66.7% |  50.0% | 1.5× | 20.0% |   0.4444 |
|       OK |    6 |   34.6 | 16.7% | 0.386 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   13 |  120.2 | 7.7% | 0.376 | 0.1 |       11 | 100.0% | 100.0% | 11.0× | 0.0% |   0.0909 |
|      ALL |   29 |   65.3 | 17.2% | 0.391 | 0.2 |       25 | 60.0% |  60.0% | 3.0× | 10.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 0.0% | 0.459 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    6 |   34.6 | 0.0% | 0.340 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  120.2 | 0.0% | 0.255 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   65.3 | 0.0% | 0.343 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 0.0% | 0.471 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.6 | 0.0% | 0.445 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  120.2 | 0.0% | 0.424 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   65.3 | 0.0% | 0.444 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available