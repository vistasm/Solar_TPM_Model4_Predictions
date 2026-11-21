# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (64.3%) is 22.2% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.4%) is 3.0× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.4%) is 2.7× the overall rate (3.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 32.9% | 0.629 | 0.5 |       83 | 64.3% |  48.6% | 1.4× | 21.7% |   0.4458 |
|       OK |   48 |   36.3 | 10.4% | 0.519 | 0.1 |       46 | 20.0% |  16.7% | 1.5× | 10.0% |   0.1304 |
| DEGRADED |  124 |  117.7 | 15.3% | 0.464 | 0.1 |      124 | 42.1% |  32.0% | 2.1× | 11.1% |   0.2016 |
|      ALL |  257 |   67.6 | 20.2% | 0.529 | 0.3 |      253 | 51.9% |  39.7% | 1.9× | 13.5% |   0.2688 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 2.4% | 0.567 | 0.0 |       83 | 100.0% |  15.4% | 6.4× | 0.0% |   0.1566 |
|       OK |   48 |   36.3 | 0.0% | 0.399 | 0.0 |       46 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.378 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0403 |
|      ALL |  257 |   67.6 | 0.8% | 0.444 | 0.0 |      253 | 100.0% |  11.1% | 14.1× | 0.0% |   0.0711 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 9.4% | 0.606 | 0.1 |       83 | 12.5% |  20.0% | 2.1× | 9.0% |   0.0602 |
|       OK |   48 |   36.3 | 2.1% | 0.534 | 0.0 |       46 | 0.0% |      - |    - | 2.2% |   0.0000 |
| DEGRADED |  124 |  117.7 | 0.0% | 0.492 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  257 |   67.6 | 3.5% | 0.538 | 0.0 |      253 | 11.1% |  16.7% | 4.7× | 3.2% |   0.0237 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 50.0% | 0.689 | 0.5 |        6 | 25.0% |  50.0% | 0.8× | 75.0% |   0.3333 |
|       OK |    6 |   33.1 | 33.3% | 0.602 | 0.3 |        4 | 50.0% | 100.0% | 2.0× | 33.3% |   0.2500 |
| DEGRADED |   17 |  116.2 | 5.9% | 0.322 | 0.1 |       17 | 100.0% |  50.0% | 8.5× | 0.0% |   0.1176 |
|      ALL |   31 |   72.8 | 22.6% | 0.471 | 0.2 |       27 | 42.9% |  60.0% | 2.3× | 18.2% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.667 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.508 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  116.2 | 0.0% | 0.279 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.8 | 0.0% | 0.423 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.581 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.545 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  116.2 | 0.0% | 0.406 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.8 | 0.0% | 0.478 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available