# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (25.0%) is 2.0× the overall rate (12.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 25.0% | 0.610 | 0.4 |       22 | 100.0% |  46.2% | 1.7× | 0.0% |   0.5909 |
|       OK |   13 |   35.2 | 7.7% | 0.524 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.437 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1579 |
|      ALL |   57 |   66.4 | 12.3% | 0.529 | 0.2 |       53 | 85.7% |  31.6% | 2.4× | 2.9% |   0.3585 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 0.0% | 0.510 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   13 |   35.2 | 0.0% | 0.406 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.364 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |   57 |   66.4 | 0.0% | 0.435 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0943 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 4.2% | 0.615 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   13 |   35.2 | 7.7% | 0.534 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   20 |  151.7 | 0.0% | 0.444 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |   57 |   66.4 | 3.5% | 0.536 | 0.0 |       53 | 0.0% |   0.0% |    - | 4.0% |   0.0566 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.6 | 50.0% | 0.757 | 0.9 |        8 | 100.0% | 100.0% | 1.6× | 0.0% |   0.6250 |
|       OK |    5 |   34.4 | 0.0% | 0.547 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.468 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   95.7 | 16.1% | 0.574 | 0.3 |       27 | 100.0% |  62.5% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.6 | 0.0% | 0.654 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    5 |   34.4 | 0.0% | 0.390 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.354 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   95.7 | 0.0% | 0.457 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   10.6 | 10.0% | 0.703 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|       OK |    5 |   34.4 | 0.0% | 0.479 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.437 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   95.7 | 3.2% | 0.529 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available