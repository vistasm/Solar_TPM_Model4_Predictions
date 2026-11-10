# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-10 UTC
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
🟡 **X+**: FRESH alert rate (10.0%) is 2.7× the overall rate (3.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 33.8% | 0.634 | 0.6 |       78 | 68.0% |  48.6% | 1.5× | 18.6% |   0.4487 |
|       OK |   44 |   36.6 | 11.4% | 0.525 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  122 |  118.7 | 14.8% | 0.462 | 0.1 |      122 | 38.9% |  29.2% | 2.0× | 11.2% |   0.1967 |
|      ALL |  246 |   69.4 | 20.3% | 0.529 | 0.3 |      242 | 52.2% |  37.5% | 2.0× | 12.4% |   0.2645 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 2.5% | 0.572 | 0.0 |       78 | 100.0% |  15.4% | 6.0× | 0.0% |   0.1667 |
|       OK |   44 |   36.6 | 0.0% | 0.407 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.375 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0410 |
|      ALL |  246 |   69.4 | 0.8% | 0.445 | 0.0 |      242 | 100.0% |  11.1% | 13.4× | 0.0% |   0.0744 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.2 | 10.0% | 0.613 | 0.1 |       78 | 12.5% |  20.0% | 1.9× | 9.6% |   0.0641 |
|       OK |   44 |   36.6 | 2.3% | 0.541 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.491 | 0.0 |      122 |    - |   0.0% |    - | 0.0% |   0.0082 |
|      ALL |  246 |   69.4 | 3.7% | 0.540 | 0.0 |      242 | 11.1% |  16.7% | 4.5× | 3.4% |   0.0248 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 100.0% | 0.907 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   34.8 | 100.0% | 0.902 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  111.9 | 26.9% | 0.502 | 0.3 |       26 | 28.6% |  66.7% | 2.5× | 21.7% |   0.1154 |
|      ALL |   31 |   97.1 | 38.7% | 0.567 | 0.4 |       27 | 25.0% |  66.7% | 2.2× | 25.0% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 0.0% | 0.965 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   34.8 | 0.0% | 0.913 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  111.9 | 0.0% | 0.452 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   97.1 | 0.0% | 0.531 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   10.8 | 0.0% | 0.718 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   34.8 | 0.0% | 0.725 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  111.9 | 0.0% | 0.515 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   97.1 | 0.0% | 0.548 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available