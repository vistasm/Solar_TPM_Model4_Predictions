# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.4× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.5%) is 2.2× the overall rate (4.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 31.6% | 0.631 | 0.6 |       76 | 70.8% |  48.6% | 1.5× | 17.1% |   0.4605 |
|       OK |   41 |   36.8 | 7.3% | 0.513 | 0.1 |       40 | 0.0% |   0.0% |    - | 8.6% |   0.1250 |
| DEGRADED |   67 |  116.5 | 10.4% | 0.500 | 0.1 |       64 | 28.6% |  13.3% | 1.2× | 10.2% |   0.2344 |
|      ALL |  184 |   55.7 | 18.5% | 0.557 | 0.3 |      180 | 55.9% |  34.5% | 1.8× | 12.0% |   0.3056 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 2.6% | 0.564 | 0.0 |       76 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1711 |
|       OK |   41 |   36.8 | 0.0% | 0.387 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   67 |  116.5 | 0.0% | 0.377 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  184 |   55.7 | 1.1% | 0.456 | 0.0 |      180 | 100.0% |  12.5% | 11.2× | 0.0% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 10.5% | 0.614 | 0.1 |       76 | 12.5% |  20.0% | 1.9× | 9.9% |   0.0658 |
|       OK |   41 |   36.8 | 2.4% | 0.537 | 0.0 |       40 | 0.0% |      - |    - | 2.5% |   0.0000 |
| DEGRADED |   67 |  116.5 | 0.0% | 0.511 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  184 |   55.7 | 4.9% | 0.559 | 0.1 |      180 | 11.1% |  16.7% | 3.3× | 4.6% |   0.0333 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 35.7% | 0.541 | 0.4 |       14 | 60.0% |  50.0% | 1.4× | 25.0% |   0.4286 |
|       OK |    8 |   37.3 | 12.5% | 0.492 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    6 |   79.8 | 16.7% | 0.563 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
|      ALL |   28 |   34.1 | 25.0% | 0.532 | 0.2 |       24 | 57.1% |  50.0% | 1.7× | 18.8% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.578 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.3 | 0.0% | 0.464 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.8 | 0.0% | 0.321 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   34.1 | 0.0% | 0.490 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.532 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.506 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   79.8 | 0.0% | 0.505 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   34.1 | 0.0% | 0.519 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available