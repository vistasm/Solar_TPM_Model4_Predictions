# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 33.3% HIGHER than DEGRADED (37.5%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.9× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.6× the overall rate (4.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  103 |  118.8 | 15.5% | 0.477 | 0.2 |      103 | 37.5% |  27.3% | 1.8× | 12.3% |   0.2136 |
|      ALL |  222 |   66.3 | 19.4% | 0.533 | 0.3 |      222 | 53.5% |  37.1% | 1.9× | 12.5% |   0.2793 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  103 |  118.8 | 0.0% | 0.385 | 0.0 |      103 |    - |   0.0% |    - | 0.0% |   0.0485 |
|      ALL |  222 |   66.3 | 0.9% | 0.444 | 0.0 |      222 | 100.0% |  11.1% | 12.3× | 0.0% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  103 |  118.8 | 0.0% | 0.500 | 0.0 |      103 |    - |   0.0% |    - | 0.0% |   0.0097 |
|      ALL |  222 |   66.3 | 4.0% | 0.544 | 0.0 |      222 | 11.1% |  16.7% | 4.1× | 3.7% |   0.0270 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   18 |  104.0 | 50.0% | 0.591 | 0.5 |       18 | 44.4% |  66.7% | 1.3× | 41.7% |   0.3333 |
|      ALL |   18 |  104.0 | 50.0% | 0.591 | 0.5 |       18 | 44.4% |  66.7% | 1.3× | 41.7% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   18 |  104.0 | 0.0% | 0.570 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   18 |  104.0 | 0.0% | 0.570 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   18 |  104.0 | 0.0% | 0.583 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   18 |  104.0 | 0.0% | 0.583 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available