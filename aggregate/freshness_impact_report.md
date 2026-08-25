# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 58.3% HIGHER than DEGRADED (16.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.9%) is 2.4× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.8%) is 2.2× the overall rate (5.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   68 |   12.2 | 32.4% | 0.657 | 0.6 |       66 | 75.0% |  48.4% | 1.6× | 14.3% |   0.4697 |
|       OK |   36 |   37.1 | 5.6% | 0.528 | 0.1 |       35 | 0.0% |   0.0% |    - | 6.7% |   0.1429 |
| DEGRADED |   62 |  119.2 | 11.3% | 0.500 | 0.1 |       61 | 16.7% |   7.1% | 0.7× | 10.6% |   0.2295 |
|      ALL |  166 |   57.6 | 18.7% | 0.570 | 0.3 |      162 | 57.1% |  32.0% | 1.9× | 10.7% |   0.3086 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   68 |   12.2 | 2.9% | 0.574 | 0.0 |       66 | 100.0% |  16.7% | 5.5× | 0.0% |   0.1818 |
|       OK |   36 |   37.1 | 0.0% | 0.391 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.390 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  166 |   57.6 | 1.2% | 0.466 | 0.0 |      162 | 100.0% |  13.3% | 10.8× | 0.0% |   0.0926 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   68 |   12.2 | 11.8% | 0.629 | 0.1 |       66 | 12.5% |  20.0% | 1.6× | 11.5% |   0.0758 |
|       OK |   36 |   37.1 | 2.8% | 0.547 | 0.0 |       35 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   62 |  119.2 | 0.0% | 0.514 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0164 |
|      ALL |  166 |   57.6 | 5.4% | 0.568 | 0.1 |      162 | 11.1% |  16.7% | 3.0× | 5.1% |   0.0370 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   11.9 | 37.5% | 0.712 | 0.4 |        6 | 100.0% |  50.0% | 3.0× | 0.0% |   0.3333 |
|       OK |    7 |   37.1 | 0.0% | 0.576 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |   13 |  122.1 | 15.4% | 0.513 | 0.1 |       12 | 0.0% |   0.0% |    - | 10.0% |   0.1667 |
|      ALL |   28 |   69.3 | 17.9% | 0.586 | 0.2 |       24 | 50.0% |  20.0% | 2.4× | 5.3% |   0.2083 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   11.9 | 0.0% | 0.696 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   37.1 | 0.0% | 0.507 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  122.1 | 0.0% | 0.420 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   69.3 | 0.0% | 0.521 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   11.9 | 0.0% | 0.582 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.1 | 0.0% | 0.547 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  122.1 | 0.0% | 0.543 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   69.3 | 0.0% | 0.555 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available