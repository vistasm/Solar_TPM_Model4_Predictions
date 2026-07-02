# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (66.7%) is 66.7% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **X+**: FRESH alert rate (8.9%) is 2.0× the overall rate (4.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   45 |   12.2 | 26.7% | 0.607 | 0.5 |       42 | 66.7% |  31.6% | 1.5× | 13.0% |   0.4524 |
|       OK |   25 |   37.1 | 8.0% | 0.510 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       44 | 0.0% |   0.0% |    - | 11.8% |   0.2273 |
|      ALL |  115 |   59.8 | 16.5% | 0.554 | 0.2 |      111 | 40.0% |  18.8% | 1.4× | 11.4% |   0.2883 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   45 |   12.2 | 0.0% | 0.513 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   25 |   37.1 | 0.0% | 0.357 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  115 |   59.8 | 0.0% | 0.437 | 0.0 |      111 |    - |   0.0% |    - | 0.0% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   45 |   12.2 | 8.9% | 0.628 | 0.1 |       42 | 0.0% |   0.0% |    - | 5.1% |   0.0714 |
|       OK |   25 |   37.1 | 4.0% | 0.550 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |
|      ALL |  115 |   59.8 | 4.3% | 0.569 | 0.0 |      111 | 0.0% |   0.0% |    - | 2.8% |   0.0360 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   10.5 | 35.7% | 0.686 | 0.8 |       11 | 0.0% |   0.0% |    - | 28.6% |   0.3636 |
|       OK |    5 |   40.0 | 20.0% | 0.547 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   12 |  105.5 | 41.7% | 0.646 | 0.4 |       11 | 0.0% |   0.0% |    - | 44.4% |   0.1818 |
|      ALL |   31 |   52.0 | 35.5% | 0.648 | 0.6 |       27 | 0.0% |   0.0% |    - | 33.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   10.5 | 0.0% | 0.601 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.0 | 0.0% | 0.307 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  105.5 | 0.0% | 0.529 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   52.0 | 0.0% | 0.526 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   10.5 | 21.4% | 0.695 | 0.2 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.0 | 0.0% | 0.590 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  105.5 | 0.0% | 0.592 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.0 | 9.7% | 0.638 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available