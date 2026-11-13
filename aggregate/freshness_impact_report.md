# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 27.8% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.5%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.9%) is 2.7× the overall rate (3.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.2 | 34.6% | 0.636 | 0.6 |       80 | 66.7% |  50.0% | 1.5× | 20.4% |   0.4500 |
|       OK |   45 |   36.5 | 11.1% | 0.529 | 0.1 |       43 | 25.0% |  16.7% | 1.8× | 8.1% |   0.1395 |
| DEGRADED |  123 |  118.2 | 15.4% | 0.466 | 0.1 |      122 | 38.9% |  29.2% | 2.0× | 11.2% |   0.1967 |
|      ALL |  249 |   69.0 | 20.9% | 0.532 | 0.3 |      245 | 53.1% |  39.4% | 2.0× | 12.8% |   0.2694 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.2 | 2.5% | 0.573 | 0.0 |       80 | 100.0% |  15.4% | 6.2× | 0.0% |   0.1625 |
|       OK |   45 |   36.5 | 0.0% | 0.407 | 0.0 |       43 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  123 |  118.2 | 0.0% | 0.379 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0410 |
|      ALL |  249 |   69.0 | 0.8% | 0.447 | 0.0 |      245 | 100.0% |  11.1% | 13.6× | 0.0% |   0.0735 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.2 | 9.9% | 0.613 | 0.1 |       80 | 12.5% |  20.0% | 2.0× | 9.3% |   0.0625 |
|       OK |   45 |   36.5 | 2.2% | 0.543 | 0.0 |       43 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  123 |  118.2 | 0.0% | 0.493 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0082 |
|      ALL |  249 |   69.0 | 3.6% | 0.541 | 0.0 |      245 | 11.1% |  16.7% | 4.5× | 3.4% |   0.0245 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.1 | 100.0% | 0.882 | 1.0 |        3 | 33.3% | 100.0% | 1.0× | 100.0% |   0.3333 |
|       OK |    3 |   33.9 | 66.7% | 0.838 | 0.7 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   24 |  111.8 | 25.0% | 0.474 | 0.2 |       23 | 40.0% |  66.7% | 3.1× | 15.0% |   0.1304 |
|      ALL |   31 |   91.1 | 38.7% | 0.562 | 0.4 |       27 | 44.4% |  80.0% | 2.4× | 22.7% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.1 | 0.0% | 0.879 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   33.9 | 0.0% | 0.733 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  111.8 | 0.0% | 0.420 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   91.1 | 0.0% | 0.510 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.1 | 0.0% | 0.704 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   33.9 | 0.0% | 0.684 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  111.8 | 0.0% | 0.483 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   91.1 | 0.0% | 0.531 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available