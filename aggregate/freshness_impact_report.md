# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (73.7%) is 53.7% HIGHER than DEGRADED (20.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 2.3× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.1%) is 2.1× the overall rate (6.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 31.1% | 0.650 | 0.6 |       60 | 73.7% |  48.3% | 1.5× | 16.1% |   0.4833 |
|       OK |   31 |   36.5 | 6.5% | 0.519 | 0.1 |       29 | 0.0% |   0.0% |    - | 8.0% |   0.1379 |
| DEGRADED |   51 |  116.1 | 9.8% | 0.504 | 0.1 |       50 | 20.0% |   7.7% | 0.8× | 10.8% |   0.2600 |
|      ALL |  143 |   54.5 | 18.2% | 0.570 | 0.3 |      139 | 57.7% |  32.6% | 1.7× | 11.8% |   0.3309 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 3.3% | 0.557 | 0.0 |       60 | 100.0% |  18.2% | 5.5× | 0.0% |   0.1833 |
|       OK |   31 |   36.5 | 0.0% | 0.359 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   51 |  116.1 | 0.0% | 0.388 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  143 |   54.5 | 1.4% | 0.454 | 0.0 |      139 | 100.0% |  14.3% | 9.9× | 0.0% |   0.1007 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.2 | 13.1% | 0.634 | 0.1 |       60 | 12.5% |  20.0% | 1.5× | 12.7% |   0.0833 |
|       OK |   31 |   36.5 | 3.2% | 0.543 | 0.0 |       29 | 0.0% |      - |    - | 3.5% |   0.0000 |
| DEGRADED |   51 |  116.1 | 0.0% | 0.509 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  143 |   54.5 | 6.3% | 0.569 | 0.1 |      139 | 11.1% |  16.7% | 2.6× | 6.0% |   0.0432 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 52.6% | 0.805 | 1.2 |       18 | 80.0% |  80.0% | 1.4× | 25.0% |   0.5556 |
|       OK |    6 |   34.3 | 0.0% | 0.558 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.352 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   30.3 | 32.3% | 0.670 | 0.7 |       27 | 80.0% |  61.5% | 1.7× | 14.3% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 10.5% | 0.715 | 0.1 |       18 | 100.0% |  40.0% | 3.6× | 0.0% |   0.2778 |
|       OK |    6 |   34.3 | 0.0% | 0.367 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.257 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.3 | 6.5% | 0.559 | 0.1 |       27 | 100.0% |  40.0% | 5.4× | 0.0% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.2 | 31.6% | 0.696 | 0.3 |       18 | 16.7% |  50.0% | 1.5× | 31.2% |   0.1111 |
|       OK |    6 |   34.3 | 0.0% | 0.513 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   86.7 | 0.0% | 0.423 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.3 | 19.4% | 0.608 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available