# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (23.3%) is 2.4× the overall rate (9.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 23.3% | 0.570 | 0.4 |       30 | 85.7% |  40.0% | 1.7× | 6.7% |   0.5000 |
|       OK |   19 |   35.8 | 5.3% | 0.494 | 0.1 |       19 | 0.0% |   0.0% |    - | 6.2% |   0.1579 |
| DEGRADED |   32 |  127.0 | 0.0% | 0.474 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.2143 |
|      ALL |   81 |   63.3 | 9.9% | 0.514 | 0.1 |       77 | 75.0% |  25.0% | 2.4× | 3.8% |   0.3117 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 0.0% | 0.476 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   19 |   35.8 | 0.0% | 0.375 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   32 |  127.0 | 0.0% | 0.363 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   81 |   63.3 | 0.0% | 0.408 | 0.0 |       77 |    - |   0.0% |    - | 0.0% |   0.0779 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   12.7 | 3.3% | 0.599 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.6% |   0.0667 |
|       OK |   19 |   35.8 | 5.3% | 0.538 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   32 |  127.0 | 0.0% | 0.491 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |
|      ALL |   81 |   63.3 | 2.5% | 0.542 | 0.0 |       77 | 0.0% |   0.0% |    - | 2.7% |   0.0390 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.9 | 11.1% | 0.465 | 0.1 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|       OK |    8 |   36.2 | 0.0% | 0.468 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.5 | 0.0% | 0.553 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|      ALL |   31 |   51.2 | 3.2% | 0.506 | 0.0 |       27 | 0.0% |   0.0% |    - | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.9 | 0.0% | 0.422 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.341 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.5 | 0.0% | 0.367 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   51.2 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.9 | 0.0% | 0.559 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.2 | 0.0% | 0.541 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.5 | 0.0% | 0.567 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.2 | 0.0% | 0.558 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available