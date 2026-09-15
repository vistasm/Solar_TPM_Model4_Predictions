# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-15 UTC
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
|       OK |   41 |   36.8 | 7.3% | 0.513 | 0.1 |       41 | 0.0% |   0.0% |    - | 8.3% |   0.1220 |
| DEGRADED |   68 |  116.8 | 10.3% | 0.496 | 0.1 |       64 | 28.6% |  13.3% | 1.2× | 10.2% |   0.2344 |
|      ALL |  185 |   56.1 | 18.4% | 0.555 | 0.3 |      181 | 55.9% |  34.5% | 1.8× | 11.9% |   0.3039 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 2.6% | 0.564 | 0.0 |       76 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1711 |
|       OK |   41 |   36.8 | 0.0% | 0.387 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   68 |  116.8 | 0.0% | 0.374 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0469 |
|      ALL |  185 |   56.1 | 1.1% | 0.455 | 0.0 |      181 | 100.0% |  12.5% | 11.3× | 0.0% |   0.0884 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 10.5% | 0.614 | 0.1 |       76 | 12.5% |  20.0% | 1.9× | 9.9% |   0.0658 |
|       OK |   41 |   36.8 | 2.4% | 0.537 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   68 |  116.8 | 0.0% | 0.509 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  185 |   56.1 | 4.9% | 0.558 | 0.1 |      181 | 11.1% |  16.7% | 3.4× | 4.6% |   0.0331 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 35.7% | 0.541 | 0.4 |       14 | 60.0% |  50.0% | 1.4× | 25.0% |   0.4286 |
|       OK |    8 |   37.3 | 12.5% | 0.492 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
| DEGRADED |    7 |   88.5 | 14.3% | 0.513 | 0.1 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
|      ALL |   29 |   37.7 | 24.1% | 0.521 | 0.2 |       25 | 57.1% |  50.0% | 1.8× | 17.6% |   0.3200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.578 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.3 | 0.0% | 0.464 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   88.5 | 0.0% | 0.294 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   37.7 | 0.0% | 0.478 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.7 | 0.0% | 0.532 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.3 | 0.0% | 0.506 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   88.5 | 0.0% | 0.484 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   37.7 | 0.0% | 0.513 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available