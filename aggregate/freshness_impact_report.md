# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-28 UTC
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
🟡 **X+**: FRESH alert rate (10.4%) is 2.3× the overall rate (4.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   79 |  122.3 | 8.9% | 0.463 | 0.1 |       75 | 28.6% |  13.3% | 1.4× | 8.3% |   0.2000 |
|      ALL |  198 |   61.4 | 17.2% | 0.535 | 0.3 |      194 | 55.9% |  34.5% | 2.0× | 10.8% |   0.2835 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   79 |  122.3 | 0.0% | 0.351 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |  198 |   61.4 | 1.0% | 0.438 | 0.0 |      194 | 100.0% |  12.5% | 12.1× | 0.0% |   0.0825 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   79 |  122.3 | 0.0% | 0.488 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0133 |
|      ALL |  198 |   61.4 | 4.5% | 0.544 | 0.1 |      194 | 11.1% |  16.7% | 3.6× | 4.3% |   0.0309 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.6 | 0.0% | 0.226 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    5 |   35.1 | 0.0% | 0.301 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  133.6 | 0.0% | 0.331 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   87.6 | 0.0% | 0.300 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.6 | 0.0% | 0.298 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.1 | 0.0% | 0.270 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  133.6 | 0.0% | 0.211 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   87.6 | 0.0% | 0.242 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.6 | 0.0% | 0.395 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.1 | 0.0% | 0.407 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  133.6 | 0.0% | 0.396 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   87.6 | 0.0% | 0.398 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available