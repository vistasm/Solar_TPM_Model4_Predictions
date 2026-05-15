# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (26.9%) is 2.3× the overall rate (11.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.4 | 26.9% | 0.602 | 0.4 |       26 | 85.7% |  42.9% | 1.6× | 8.3% |   0.5385 |
|       OK |   16 |   35.6 | 6.2% | 0.529 | 0.1 |       14 | 0.0% |   0.0% |    - | 9.1% |   0.2143 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.452 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.2174 |
|      ALL |   67 |   63.7 | 11.9% | 0.528 | 0.2 |       63 | 75.0% |  27.3% | 2.1× | 4.9% |   0.3492 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.4 | 0.0% | 0.498 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |   16 |   35.6 | 0.0% | 0.398 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.369 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|      ALL |   67 |   63.7 | 0.0% | 0.426 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0952 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.4 | 3.9% | 0.611 | 0.0 |       26 | 0.0% |   0.0% |    - | 4.2% |   0.0769 |
|       OK |   16 |   35.6 | 6.2% | 0.538 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   25 |  135.0 | 0.0% | 0.468 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   67 |   63.7 | 3.0% | 0.540 | 0.0 |       63 | 0.0% |   0.0% |    - | 3.3% |   0.0476 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.9 | 60.0% | 0.736 | 1.0 |       10 | 83.3% |  83.3% | 1.4× | 25.0% |   0.6000 |
|       OK |    5 |   35.7 | 0.0% | 0.562 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  163.8 | 0.0% | 0.501 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.2857 |
|      ALL |   31 |   93.8 | 19.4% | 0.587 | 0.3 |       27 | 83.3% |  50.0% | 2.2× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.9 | 0.0% | 0.648 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    5 |   35.7 | 0.0% | 0.395 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  163.8 | 0.0% | 0.385 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   93.8 | 0.0% | 0.472 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.9 | 10.0% | 0.717 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    5 |   35.7 | 0.0% | 0.543 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  163.8 | 0.0% | 0.486 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   93.8 | 3.2% | 0.570 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available