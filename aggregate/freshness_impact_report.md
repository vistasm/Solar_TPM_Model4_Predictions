# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 42.3% HIGHER than DEGRADED (28.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.8%) is 2.5× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.3%) is 2.2× the overall rate (5.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   71 |   12.1 | 33.8% | 0.656 | 0.6 |       70 | 70.8% |  51.5% | 1.5× | 18.9% |   0.4714 |
|       OK |   39 |   36.4 | 7.7% | 0.524 | 0.1 |       37 | 0.0% |   0.0% |    - | 9.4% |   0.1351 |
| DEGRADED |   64 |  117.6 | 10.9% | 0.502 | 0.1 |       63 | 28.6% |  13.3% | 1.2× | 10.4% |   0.2381 |
|      ALL |  174 |   56.4 | 19.5% | 0.570 | 0.3 |      170 | 55.9% |  35.9% | 1.8× | 12.8% |   0.3118 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   71 |   12.1 | 2.8% | 0.579 | 0.0 |       70 | 100.0% |  15.4% | 5.4× | 0.0% |   0.1857 |
|       OK |   39 |   36.4 | 0.0% | 0.392 | 0.0 |       37 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.384 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  174 |   56.4 | 1.1% | 0.465 | 0.0 |      170 | 100.0% |  12.5% | 10.6× | 0.0% |   0.0941 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   71 |   12.1 | 11.3% | 0.626 | 0.1 |       70 | 12.5% |  20.0% | 1.8× | 10.8% |   0.0714 |
|       OK |   39 |   36.4 | 2.6% | 0.544 | 0.0 |       37 | 0.0% |      - |    - | 2.7% |   0.0000 |
| DEGRADED |   64 |  117.6 | 0.0% | 0.515 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0159 |
|      ALL |  174 |   56.4 | 5.2% | 0.567 | 0.1 |      170 | 11.1% |  16.7% | 3.1× | 4.9% |   0.0353 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.3 | 55.6% | 0.690 | 0.6 |        8 | 60.0% |  75.0% | 1.2× | 50.0% |   0.5000 |
|       OK |    7 |   35.9 | 14.3% | 0.511 | 0.1 |        5 | 0.0% |   0.0% |    - | 25.0% |   0.2000 |
| DEGRADED |   12 |  128.7 | 16.7% | 0.473 | 0.2 |       11 | 50.0% | 100.0% | 5.5× | 10.0% |   0.0909 |
|      ALL |   28 |   67.8 | 28.6% | 0.553 | 0.3 |       24 | 50.0% |  66.7% | 2.0× | 22.2% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.3 | 0.0% | 0.706 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    7 |   35.9 | 0.0% | 0.501 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  128.7 | 0.0% | 0.352 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.8 | 0.0% | 0.503 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.3 | 0.0% | 0.581 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   35.9 | 0.0% | 0.548 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  128.7 | 0.0% | 0.541 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   28 |   67.8 | 0.0% | 0.555 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available