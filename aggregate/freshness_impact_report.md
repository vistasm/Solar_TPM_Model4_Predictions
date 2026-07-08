# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 58.6% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.0%) is 2.4× the overall rate (1.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (16.0%) is 2.2× the overall rate (7.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   11.7 | 32.0% | 0.639 | 0.7 |       47 | 78.6% |  45.8% | 1.5× | 13.0% |   0.5106 |
|       OK |   26 |   36.6 | 7.7% | 0.520 | 0.1 |       25 | 0.0% |   0.0% |    - | 9.1% |   0.1200 |
| DEGRADED |   45 |  120.0 | 11.1% | 0.524 | 0.1 |       45 | 20.0% |   9.1% | 0.8× | 11.8% |   0.2444 |
|      ALL |  121 |   57.3 | 19.0% | 0.571 | 0.3 |      117 | 57.1% |  31.6% | 1.8× | 11.4% |   0.3248 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   11.7 | 4.0% | 0.549 | 0.0 |       47 | 100.0% |  20.0% | 4.7× | 0.0% |   0.2128 |
|       OK |   26 |   36.6 | 0.0% | 0.365 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.406 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  121 |   57.3 | 1.7% | 0.456 | 0.0 |      117 | 100.0% |  15.4% | 9.0× | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   11.7 | 16.0% | 0.658 | 0.2 |       47 | 16.7% |  20.0% | 1.6× | 11.9% |   0.1064 |
|       OK |   26 |   36.6 | 3.9% | 0.555 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.0 | 0.0% | 0.520 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  121 |   57.3 | 7.4% | 0.585 | 0.1 |      117 | 14.3% |  16.7% | 2.8× | 5.4% |   0.0513 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    8.9 | 53.3% | 0.758 | 1.4 |       12 | 83.3% |  71.4% | 1.4× | 20.0% |   0.5833 |
|       OK |    5 |   36.5 | 20.0% | 0.570 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 45.5% | 0.645 | 0.5 |       11 | 20.0% |  50.0% | 1.1× | 44.4% |   0.1818 |
|      ALL |   31 |   48.0 | 45.2% | 0.687 | 0.9 |       27 | 50.0% |  66.7% | 1.5× | 33.3% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    8.9 | 13.3% | 0.713 | 0.1 |       12 | 100.0% |  40.0% | 2.4× | 0.0% |   0.4167 |
|       OK |    5 |   36.5 | 0.0% | 0.330 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.545 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.0 | 6.5% | 0.592 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    8.9 | 40.0% | 0.766 | 0.4 |       12 | 25.0% |  50.0% | 1.5× | 30.0% |   0.1667 |
|       OK |    5 |   36.5 | 0.0% | 0.571 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.5 | 0.0% | 0.595 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.0 | 19.4% | 0.674 | 0.2 |       27 | 25.0% |  50.0% | 3.4× | 12.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available