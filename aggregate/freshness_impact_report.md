# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (25.0%) is 2.1× the overall rate (12.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 25.0% | 0.610 | 0.4 |       22 | 100.0% |  46.2% | 1.7× | 0.0% |   0.5909 |
|       OK |   13 |   35.2 | 7.7% | 0.524 | 0.1 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
| DEGRADED |   21 |  146.9 | 0.0% | 0.429 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   58 |   66.1 | 12.1% | 0.525 | 0.2 |       54 | 85.7% |  31.6% | 2.4× | 2.9% |   0.3519 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 0.0% | 0.510 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   13 |   35.2 | 0.0% | 0.406 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  146.9 | 0.0% | 0.358 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   58 |   66.1 | 0.0% | 0.432 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0926 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.2 | 4.2% | 0.615 | 0.0 |       22 | 0.0% |   0.0% |    - | 5.0% |   0.0909 |
|       OK |   13 |   35.2 | 7.7% | 0.534 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   21 |  146.9 | 0.0% | 0.448 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   58 |   66.1 | 3.5% | 0.536 | 0.0 |       54 | 0.0% |   0.0% |    - | 3.9% |   0.0556 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.1 | 55.6% | 0.759 | 1.0 |        7 | 100.0% | 100.0% | 1.4× | 0.0% |   0.7143 |
|       OK |    5 |   34.4 | 0.0% | 0.547 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   17 |  161.3 | 0.0% | 0.457 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   97.2 | 16.1% | 0.559 | 0.3 |       27 | 100.0% |  62.5% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.1 | 0.0% | 0.662 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    5 |   34.4 | 0.0% | 0.390 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.3 | 0.0% | 0.348 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.2 | 0.0% | 0.446 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.1 | 11.1% | 0.725 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
|       OK |    5 |   34.4 | 0.0% | 0.479 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.3 | 0.0% | 0.443 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.2 | 3.2% | 0.530 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available