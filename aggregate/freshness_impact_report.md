# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-22 UTC
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
|    FRESH |   85 |   12.1 | 32.9% | 0.629 | 0.5 |       84 | 64.3% |  48.6% | 1.5× | 21.3% |   0.4405 |
|       OK |   48 |   36.3 | 10.4% | 0.519 | 0.1 |       46 | 20.0% |  16.7% | 1.5× | 10.0% |   0.1304 |
| DEGRADED |  125 |  117.3 | 15.2% | 0.461 | 0.1 |      124 | 42.1% |  32.0% | 2.1× | 11.1% |   0.2016 |
|      ALL |  258 |   67.6 | 20.2% | 0.527 | 0.3 |      254 | 51.9% |  39.7% | 1.9× | 13.4% |   0.2677 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 2.4% | 0.567 | 0.0 |       84 | 100.0% |  15.4% | 6.5× | 0.0% |   0.1548 |
|       OK |   48 |   36.3 | 0.0% | 0.399 | 0.0 |       46 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  125 |  117.3 | 0.0% | 0.375 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0403 |
|      ALL |  258 |   67.6 | 0.8% | 0.443 | 0.0 |      254 | 100.0% |  11.1% | 14.1× | 0.0% |   0.0709 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.1 | 9.4% | 0.606 | 0.1 |       84 | 12.5% |  20.0% | 2.1× | 8.9% |   0.0595 |
|       OK |   48 |   36.3 | 2.1% | 0.534 | 0.0 |       46 | 0.0% |      - |    - | 2.2% |   0.0000 |
| DEGRADED |  125 |  117.3 | 0.0% | 0.491 | 0.0 |      124 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  258 |   67.6 | 3.5% | 0.537 | 0.0 |      254 | 11.1% |  16.7% | 4.7× | 3.2% |   0.0236 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 50.0% | 0.689 | 0.5 |        7 | 25.0% |  50.0% | 0.9× | 60.0% |   0.2857 |
|       OK |    6 |   33.1 | 33.3% | 0.602 | 0.3 |        4 | 50.0% | 100.0% | 2.0× | 33.3% |   0.2500 |
| DEGRADED |   17 |  114.3 | 5.9% | 0.302 | 0.1 |       16 | 100.0% |  50.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   31 |   71.8 | 22.6% | 0.460 | 0.2 |       27 | 42.9% |  60.0% | 2.3× | 18.2% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.667 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.508 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  114.3 | 0.0% | 0.266 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   71.8 | 0.0% | 0.416 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.6 | 0.0% | 0.581 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.545 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  114.3 | 0.0% | 0.394 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   71.8 | 0.0% | 0.472 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available