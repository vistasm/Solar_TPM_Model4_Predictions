# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.2× the overall rate (4.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       76 | 70.8% |  48.6% | 1.5× | 17.1% |   0.4605 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       41 | 0.0% |   0.0% |    - | 8.3% |   0.1220 |
| DEGRADED |   72 |  121.4 | 9.7% | 0.475 | 0.1 |       70 | 28.6% |  13.3% | 1.3× | 9.1% |   0.2143 |
|      ALL |  191 |   58.8 | 17.8% | 0.542 | 0.3 |      187 | 55.9% |  34.5% | 1.9× | 11.4% |   0.2941 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       76 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1711 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   72 |  121.4 | 0.0% | 0.361 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0429 |
|      ALL |  191 |   58.8 | 1.1% | 0.445 | 0.0 |      187 | 100.0% |  12.5% | 11.7× | 0.0% |   0.0856 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       76 | 12.5% |  20.0% | 1.9× | 9.9% |   0.0658 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   72 |  121.4 | 0.0% | 0.500 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0143 |
|      ALL |  191 |   58.8 | 4.7% | 0.551 | 0.1 |      187 | 11.1% |  16.7% | 3.5× | 4.4% |   0.0321 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   12.9 | 36.4% | 0.451 | 0.4 |       10 | 50.0% |  50.0% | 1.2× | 33.3% |   0.4000 |
|       OK |    7 |   35.8 | 14.3% | 0.433 | 0.1 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   11 |  129.1 | 9.1% | 0.371 | 0.1 |        9 | 100.0% | 100.0% | 9.0× | 0.0% |   0.1111 |
|      ALL |   29 |   62.5 | 20.7% | 0.416 | 0.2 |       25 | 50.0% |  60.0% | 2.5× | 15.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   12.9 | 0.0% | 0.494 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    7 |   35.8 | 0.0% | 0.380 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  129.1 | 0.0% | 0.241 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   62.5 | 0.0% | 0.370 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   12.9 | 0.0% | 0.485 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   35.8 | 0.0% | 0.467 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  129.1 | 0.0% | 0.433 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   62.5 | 0.0% | 0.461 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available