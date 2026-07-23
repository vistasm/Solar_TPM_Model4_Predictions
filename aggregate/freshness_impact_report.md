# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 55.0% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.4%) is 2.3× the overall rate (1.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.6%) is 2.0× the overall rate (6.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   12.2 | 32.2% | 0.649 | 0.6 |       56 | 75.0% |  44.4% | 1.6× | 13.8% |   0.4821 |
|       OK |   28 |   37.1 | 7.1% | 0.511 | 0.1 |       28 | 0.0% |   0.0% |    - | 8.3% |   0.1429 |
| DEGRADED |   49 |  118.5 | 10.2% | 0.496 | 0.1 |       48 | 20.0% |   9.1% | 0.9× | 10.8% |   0.2292 |
|      ALL |  136 |   55.6 | 19.1% | 0.566 | 0.3 |      132 | 56.5% |  30.9% | 1.8× | 11.1% |   0.3182 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   12.2 | 3.4% | 0.558 | 0.0 |       56 | 100.0% |  18.2% | 5.1× | 0.0% |   0.1964 |
|       OK |   28 |   37.1 | 0.0% | 0.365 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   49 |  118.5 | 0.0% | 0.382 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  136 |   55.6 | 1.5% | 0.455 | 0.0 |      132 | 100.0% |  14.3% | 9.4× | 0.0% |   0.1061 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   12.2 | 13.6% | 0.638 | 0.1 |       56 | 12.5% |  20.0% | 1.4× | 13.7% |   0.0893 |
|       OK |   28 |   37.1 | 3.6% | 0.547 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   49 |  118.5 | 0.0% | 0.506 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0208 |
|      ALL |  136 |   55.6 | 6.6% | 0.572 | 0.1 |      132 | 11.1% |  16.7% | 2.4× | 6.3% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.9 | 58.8% | 0.819 | 1.4 |       14 | 85.7% |  75.0% | 1.5× | 16.7% |   0.5714 |
|       OK |    4 |   36.0 | 25.0% | 0.594 | 0.2 |        4 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
| DEGRADED |   10 |  111.1 | 50.0% | 0.591 | 0.5 |        9 | 20.0% | 100.0% | 1.8× | 50.0% |   0.1111 |
|      ALL |   31 |   46.4 | 51.6% | 0.716 | 0.9 |       27 | 53.8% |  70.0% | 1.4× | 35.3% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.9 | 11.8% | 0.736 | 0.1 |       14 | 100.0% |  40.0% | 2.8× | 0.0% |   0.3571 |
|       OK |    4 |   36.0 | 0.0% | 0.426 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.1 | 0.0% | 0.456 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 6.5% | 0.606 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.9 | 35.3% | 0.718 | 0.3 |       14 | 16.7% |  50.0% | 1.2× | 41.7% |   0.1429 |
|       OK |    4 |   36.0 | 0.0% | 0.562 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.1 | 0.0% | 0.588 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 19.4% | 0.656 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available