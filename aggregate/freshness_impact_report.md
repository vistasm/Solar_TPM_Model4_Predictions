# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 57.0% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.1%) is 2.5× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.3%) is 2.2× the overall rate (5.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   12.2 | 29.2% | 0.649 | 0.6 |       62 | 73.7% |  48.3% | 1.6× | 15.2% |   0.4677 |
|       OK |   35 |   36.9 | 5.7% | 0.522 | 0.1 |       34 | 0.0% |   0.0% |    - | 6.7% |   0.1176 |
| DEGRADED |   61 |  120.1 | 9.8% | 0.494 | 0.1 |       61 | 16.7% |   7.1% | 0.7× | 10.6% |   0.2295 |
|      ALL |  161 |   58.4 | 16.8% | 0.563 | 0.3 |      157 | 55.6% |  31.9% | 1.9× | 10.9% |   0.2994 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   12.2 | 3.1% | 0.564 | 0.0 |       62 | 100.0% |  18.2% | 5.6× | 0.0% |   0.1774 |
|       OK |   35 |   36.9 | 0.0% | 0.384 | 0.0 |       34 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   61 |  120.1 | 0.0% | 0.383 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  161 |   58.4 | 1.2% | 0.456 | 0.0 |      157 | 100.0% |  14.3% | 11.2× | 0.0% |   0.0892 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   12.2 | 12.3% | 0.630 | 0.1 |       62 | 12.5% |  20.0% | 1.6× | 12.3% |   0.0806 |
|       OK |   35 |   36.9 | 2.9% | 0.546 | 0.0 |       34 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   61 |  120.1 | 0.0% | 0.512 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0164 |
|      ALL |  161 |   58.4 | 5.6% | 0.567 | 0.1 |      157 | 11.1% |  16.7% | 2.9× | 5.3% |   0.0382 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.7 | 33.3% | 0.717 | 0.3 |        6 | 66.7% | 100.0% | 2.0× | 25.0% |   0.3333 |
|       OK |    7 |   36.4 | 0.0% | 0.568 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  126.6 | 8.3% | 0.487 | 0.1 |       12 | 0.0% |   0.0% |    - | 10.0% |   0.1667 |
|      ALL |   28 |   67.5 | 14.3% | 0.581 | 0.1 |       24 | 50.0% |  50.0% | 3.0× | 10.0% |   0.1667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.7 | 0.0% | 0.728 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.4 | 0.0% | 0.461 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  126.6 | 0.0% | 0.386 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.5 | 0.0% | 0.514 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.7 | 0.0% | 0.540 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.4 | 0.0% | 0.539 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  126.6 | 0.0% | 0.537 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.5 | 0.0% | 0.539 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available