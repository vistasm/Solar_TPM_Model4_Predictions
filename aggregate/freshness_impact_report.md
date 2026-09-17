# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.5× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.5%) is 2.2× the overall rate (4.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 31.6% | 0.631 | 0.6 |       76 | 70.8% |  48.6% | 1.5× | 17.1% |   0.4605 |
|       OK |   41 |   36.8 | 7.3% | 0.513 | 0.1 |       41 | 0.0% |   0.0% |    - | 8.3% |   0.1220 |
| DEGRADED |   70 |  118.5 | 10.0% | 0.487 | 0.1 |       66 | 28.6% |  13.3% | 1.3× | 9.8% |   0.2273 |
|      ALL |  187 |   57.4 | 18.2% | 0.551 | 0.3 |      183 | 55.9% |  34.5% | 1.9× | 11.7% |   0.3005 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 2.6% | 0.564 | 0.0 |       76 | 100.0% |  15.4% | 5.8× | 0.0% |   0.1711 |
|       OK |   41 |   36.8 | 0.0% | 0.387 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   70 |  118.5 | 0.0% | 0.367 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |  187 |   57.4 | 1.1% | 0.451 | 0.0 |      183 | 100.0% |  12.5% | 11.4× | 0.0% |   0.0874 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   76 |   12.3 | 10.5% | 0.614 | 0.1 |       76 | 12.5% |  20.0% | 1.9× | 9.9% |   0.0658 |
|       OK |   41 |   36.8 | 2.4% | 0.537 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   70 |  118.5 | 0.0% | 0.505 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0152 |
|      ALL |  187 |   57.4 | 4.8% | 0.556 | 0.1 |      183 | 11.1% |  16.7% | 3.4× | 4.5% |   0.0328 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.9 | 38.5% | 0.541 | 0.4 |       13 | 60.0% |  50.0% | 1.3× | 28.6% |   0.4615 |
|       OK |    7 |   36.0 | 14.3% | 0.494 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    9 |  108.0 | 11.1% | 0.437 | 0.1 |        5 | 100.0% | 100.0% | 5.0× | 0.0% |   0.2000 |
|      ALL |   29 |   48.0 | 24.1% | 0.497 | 0.2 |       25 | 57.1% |  50.0% | 1.8× | 17.6% |   0.3200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.9 | 0.0% | 0.573 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    7 |   36.0 | 0.0% | 0.437 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  108.0 | 0.0% | 0.264 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   48.0 | 0.0% | 0.444 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.9 | 0.0% | 0.530 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.0 | 0.0% | 0.499 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  108.0 | 0.0% | 0.458 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   48.0 | 0.0% | 0.500 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available