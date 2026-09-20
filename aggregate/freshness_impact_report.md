# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-20 UTC
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
|       OK |   41 |   36.8 | 7.3% | 0.513 | 0.1 |       41 | 0.0% |   0.0% |    - | 8.3% |   0.1220 |
| DEGRADED |   72 |  121.4 | 9.7% | 0.475 | 0.1 |       69 | 28.6% |  13.3% | 1.3× | 9.3% |   0.2174 |
|      ALL |  190 |   58.9 | 17.9% | 0.543 | 0.3 |      186 | 55.9% |  34.5% | 1.9× | 11.5% |   0.2957 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       76 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1711 |
|       OK |   41 |   36.8 | 0.0% | 0.387 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   72 |  121.4 | 0.0% | 0.361 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |  190 |   58.9 | 1.1% | 0.446 | 0.0 |      186 | 100.0% |  12.5% | 11.6× | 0.0% |   0.0860 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       76 | 12.5% |  20.0% | 1.9× | 9.9% |   0.0658 |
|       OK |   41 |   36.8 | 2.4% | 0.537 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   72 |  121.4 | 0.0% | 0.500 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0145 |
|      ALL |  190 |   58.9 | 4.7% | 0.552 | 0.1 |      186 | 11.1% |  16.7% | 3.4× | 4.4% |   0.0323 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 41.7% | 0.484 | 0.4 |       11 | 60.0% |  60.0% | 1.3× | 33.3% |   0.4545 |
|       OK |    6 |   35.9 | 16.7% | 0.463 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   11 |  129.1 | 9.1% | 0.371 | 0.1 |        8 | 100.0% | 100.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   29 |   61.8 | 24.1% | 0.437 | 0.2 |       25 | 57.1% |  66.7% | 2.4× | 15.8% |   0.2400 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.517 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    6 |   35.9 | 0.0% | 0.402 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  129.1 | 0.0% | 0.241 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   61.8 | 0.0% | 0.388 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.9 | 0.0% | 0.495 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.9 | 0.0% | 0.484 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  129.1 | 0.0% | 0.433 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   61.8 | 0.0% | 0.469 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available