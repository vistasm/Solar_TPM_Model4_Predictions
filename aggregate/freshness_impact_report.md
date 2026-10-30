# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (70.8%) is 32.4% HIGHER than DEGRADED (38.5%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.8× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.5× the overall rate (4.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   99 |  119.8 | 13.1% | 0.464 | 0.1 |       99 | 38.5% |  23.8% | 1.8× | 10.3% |   0.2121 |
|      ALL |  218 |   65.8 | 18.4% | 0.528 | 0.3 |      218 | 55.0% |  36.1% | 2.0× | 11.5% |   0.2798 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   99 |  119.8 | 0.0% | 0.369 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0505 |
|      ALL |  218 |   65.8 | 0.9% | 0.438 | 0.0 |      218 | 100.0% |  11.1% | 12.1× | 0.0% |   0.0826 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   99 |  119.8 | 0.0% | 0.496 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0101 |
|      ALL |  218 |   65.8 | 4.1% | 0.543 | 0.0 |      218 | 11.1% |  16.7% | 4.0× | 3.8% |   0.0275 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |  106.5 | 42.9% | 0.528 | 0.4 |       14 | 50.0% |  60.0% | 1.4× | 33.3% |   0.3571 |
|      ALL |   14 |  106.5 | 42.9% | 0.528 | 0.4 |       14 | 50.0% |  60.0% | 1.4× | 33.3% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |  106.5 | 0.0% | 0.514 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   14 |  106.5 | 0.0% | 0.514 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |  106.5 | 0.0% | 0.575 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   14 |  106.5 | 0.0% | 0.575 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available