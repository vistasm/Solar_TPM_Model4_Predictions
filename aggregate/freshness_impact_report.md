# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 31.9% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 3.1× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.3%) is 2.8× the overall rate (3.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.3 | 32.0% | 0.626 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  122 |  118.7 | 14.8% | 0.462 | 0.1 |      119 | 38.9% |  30.4% | 2.0× | 11.5% |   0.1933 |
|      ALL |  242 |   70.2 | 19.0% | 0.523 | 0.3 |      238 | 53.3% |  38.1% | 2.0× | 12.0% |   0.2647 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.3 | 2.6% | 0.562 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.375 | 0.0 |      119 |    - |   0.0% |    - | 0.0% |   0.0420 |
|      ALL |  242 |   70.2 | 0.8% | 0.437 | 0.0 |      238 | 100.0% |  11.1% | 13.2× | 0.0% |   0.0756 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.3 | 10.3% | 0.611 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  122 |  118.7 | 0.0% | 0.491 | 0.0 |      119 |    - |   0.0% |    - | 0.0% |   0.0084 |
|      ALL |  242 |   70.2 | 3.7% | 0.537 | 0.0 |      238 | 11.1% |  16.7% | 4.4× | 3.5% |   0.0252 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   10.8 | 100.0% | 0.890 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  109.7 | 36.7% | 0.557 | 0.4 |       27 | 45.5% | 100.0% | 2.5× | 27.3% |   0.1852 |
|      ALL |   31 |  106.5 | 38.7% | 0.568 | 0.4 |       27 | 45.5% | 100.0% | 2.5× | 27.3% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   10.8 | 0.0% | 0.944 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  109.7 | 0.0% | 0.516 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   31 |  106.5 | 0.0% | 0.530 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   10.8 | 0.0% | 0.788 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  109.7 | 0.0% | 0.555 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  106.5 | 0.0% | 0.563 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available