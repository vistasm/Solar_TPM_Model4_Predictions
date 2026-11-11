# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (68.0%) is 29.1% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.5%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.0%) is 2.7× the overall rate (3.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 33.8% | 0.634 | 0.6 |       78 | 68.0% |  48.6% | 1.5× | 18.6% |   0.4487 |
|       OK |   44 |   36.6 | 11.4% | 0.525 | 0.1 |       43 | 25.0% |  16.7% | 1.8× | 8.1% |   0.1395 |
| DEGRADED |  123 |  118.2 | 15.4% | 0.466 | 0.1 |      122 | 38.9% |  29.2% | 2.0× | 11.2% |   0.1967 |
|      ALL |  247 |   69.4 | 20.6% | 0.531 | 0.3 |      243 | 53.2% |  38.5% | 2.0× | 12.4% |   0.2675 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 2.5% | 0.572 | 0.0 |       78 | 100.0% |  15.4% | 6.0× | 0.0% |   0.1667 |
|       OK |   44 |   36.6 | 0.0% | 0.407 | 0.0 |       43 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  123 |  118.2 | 0.0% | 0.379 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0410 |
|      ALL |  247 |   69.4 | 0.8% | 0.447 | 0.0 |      243 | 100.0% |  11.1% | 13.5× | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 10.0% | 0.613 | 0.1 |       78 | 12.5% |  20.0% | 1.9× | 9.6% |   0.0641 |
|       OK |   44 |   36.6 | 2.3% | 0.541 | 0.0 |       43 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  123 |  118.2 | 0.0% | 0.493 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0082 |
|      ALL |  247 |   69.4 | 3.6% | 0.541 | 0.0 |      243 | 11.1% |  16.7% | 4.5× | 3.4% |   0.0247 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 100.0% | 0.907 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   34.8 | 100.0% | 0.902 | 1.0 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   26 |  110.5 | 26.9% | 0.502 | 0.3 |       25 | 33.3% |  66.7% | 2.8× | 18.2% |   0.1200 |
|      ALL |   31 |   96.0 | 38.7% | 0.567 | 0.4 |       27 | 37.5% |  75.0% | 2.5× | 21.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 0.0% | 0.965 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   34.8 | 0.0% | 0.913 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  110.5 | 0.0% | 0.453 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   96.0 | 0.0% | 0.532 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 0.0% | 0.718 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   34.8 | 0.0% | 0.725 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  110.5 | 0.0% | 0.509 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   96.0 | 0.0% | 0.544 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available