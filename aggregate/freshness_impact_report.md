# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.0%) is 2.1× the overall rate (4.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 10.0% | 0.512 | 0.1 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|       OK |    7 |   37.2 | 0.0% | 0.465 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   21 |   35.8 | 4.8% | 0.458 | 0.1 |       17 |    - |   0.0% |    - | 0.0% |   0.3529 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 0.0% | 0.426 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.2 | 0.0% | 0.425 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   21 |   35.8 | 0.0% | 0.422 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 0.0% | 0.529 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.2 | 0.0% | 0.519 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   21 |   35.8 | 0.0% | 0.515 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 10.0% | 0.512 | 0.1 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|       OK |    7 |   37.2 | 0.0% | 0.465 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.312 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   21 |   35.8 | 4.8% | 0.458 | 0.1 |       17 |    - |   0.0% |    - | 0.0% |   0.3529 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 0.0% | 0.426 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.2 | 0.0% | 0.425 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.404 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   21 |   35.8 | 0.0% | 0.422 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 0.0% | 0.529 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.2 | 0.0% | 0.519 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   85.8 | 0.0% | 0.472 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   21 |   35.8 | 0.0% | 0.515 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available