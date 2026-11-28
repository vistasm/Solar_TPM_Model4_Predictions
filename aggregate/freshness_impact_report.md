# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (64.3%) is 22.2% HIGHER than DEGRADED (42.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.3%) is 3.0× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.2%) is 2.7× the overall rate (3.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.2 | 32.2% | 0.619 | 0.5 |       85 | 64.3% |  48.6% | 1.5× | 20.8% |   0.4353 |
|       OK |   48 |   36.3 | 10.4% | 0.519 | 0.1 |       48 | 20.0% |  14.3% | 1.4× | 9.8% |   0.1458 |
| DEGRADED |  129 |  117.5 | 14.7% | 0.451 | 0.1 |      127 | 42.1% |  32.0% | 2.1× | 10.8% |   0.1968 |
|      ALL |  264 |   68.0 | 19.7% | 0.519 | 0.3 |      260 | 51.9% |  39.1% | 2.0× | 13.1% |   0.2654 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.2 | 2.3% | 0.558 | 0.0 |       85 | 100.0% |  15.4% | 6.5× | 0.0% |   0.1529 |
|       OK |   48 |   36.3 | 0.0% | 0.399 | 0.0 |       48 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  129 |  117.5 | 0.0% | 0.366 | 0.0 |      127 |    - |   0.0% |    - | 0.0% |   0.0394 |
|      ALL |  264 |   68.0 | 0.8% | 0.435 | 0.0 |      260 | 100.0% |  11.1% | 14.4× | 0.0% |   0.0692 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   87 |   12.2 | 9.2% | 0.600 | 0.1 |       85 | 12.5% |  20.0% | 2.1× | 8.8% |   0.0588 |
|       OK |   48 |   36.3 | 2.1% | 0.534 | 0.0 |       48 | 0.0% |      - |    - | 2.1% |   0.0000 |
| DEGRADED |  129 |  117.5 | 0.0% | 0.486 | 0.0 |      127 |    - |   0.0% |    - | 0.0% |   0.0079 |
|      ALL |  264 |   68.0 | 3.4% | 0.532 | 0.0 |      260 | 11.1% |  16.7% | 4.8× | 3.1% |   0.0231 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 40.0% | 0.584 | 0.4 |        8 | 25.0% |  50.0% | 1.0× | 50.0% |   0.2500 |
|       OK |    6 |   33.1 | 33.3% | 0.602 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   15 |  124.2 | 6.7% | 0.246 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   70.2 | 22.6% | 0.424 | 0.2 |       27 | 42.9% |  50.0% | 1.9× | 19.1% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 0.0% | 0.566 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.508 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  124.2 | 0.0% | 0.191 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.2 | 0.0% | 0.374 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.4 | 0.0% | 0.534 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.1 | 0.0% | 0.545 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  124.2 | 0.0% | 0.380 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.2 | 0.0% | 0.462 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available