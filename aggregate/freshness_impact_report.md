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

🟢 **M+**: FRESH precision (70.8%) is 29.2% HIGHER than DEGRADED (41.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.8× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.5× the overall rate (4.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   97 |  120.3 | 12.4% | 0.456 | 0.1 |       97 | 41.7% |  23.8% | 1.9× | 9.2% |   0.2165 |
|      ALL |  216 |   65.5 | 18.1% | 0.525 | 0.3 |      216 | 56.4% |  36.1% | 2.0× | 11.0% |   0.2824 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   97 |  120.3 | 0.0% | 0.359 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0515 |
|      ALL |  216 |   65.5 | 0.9% | 0.434 | 0.0 |      216 | 100.0% |  11.1% | 12.0× | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   97 |  120.3 | 0.0% | 0.489 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0103 |
|      ALL |  216 |   65.5 | 4.2% | 0.540 | 0.0 |      216 | 11.1% |  16.7% | 4.0× | 3.8% |   0.0278 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |  108.4 | 41.7% | 0.478 | 0.4 |       12 | 60.0% |  60.0% | 1.4× | 28.6% |   0.4167 |
|      ALL |   12 |  108.4 | 41.7% | 0.478 | 0.4 |       12 | 60.0% |  60.0% | 1.4× | 28.6% |   0.4167 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |  108.4 | 0.0% | 0.458 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   12 |  108.4 | 0.0% | 0.458 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |  108.4 | 0.0% | 0.533 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   12 |  108.4 | 0.0% | 0.533 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available