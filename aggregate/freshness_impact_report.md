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

🟢 **M+**: FRESH precision (70.8%) is 25.4% HIGHER than DEGRADED (45.5%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 2.8× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.5× the overall rate (4.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |   96 |  120.5 | 11.5% | 0.451 | 0.1 |       96 | 45.5% |  23.8% | 2.1× | 8.0% |   0.2188 |
|      ALL |  215 |   65.4 | 17.7% | 0.524 | 0.3 |      215 | 57.9% |  36.1% | 2.0× | 10.4% |   0.2837 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   96 |  120.5 | 0.0% | 0.355 | 0.0 |       96 |    - |   0.0% |    - | 0.0% |   0.0521 |
|      ALL |  215 |   65.4 | 0.9% | 0.433 | 0.0 |      215 | 100.0% |  11.1% | 11.9× | 0.0% |   0.0837 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   96 |  120.5 | 0.0% | 0.485 | 0.0 |       96 |    - |   0.0% |    - | 0.0% |   0.0104 |
|      ALL |  215 |   65.4 | 4.2% | 0.538 | 0.0 |      215 | 11.1% |  16.7% | 4.0× | 3.8% |   0.0279 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |  109.5 | 36.4% | 0.438 | 0.4 |       11 | 75.0% |  60.0% | 1.6× | 16.7% |   0.4545 |
|      ALL |   11 |  109.5 | 36.4% | 0.438 | 0.4 |       11 | 75.0% |  60.0% | 1.6× | 16.7% |   0.4545 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |  109.5 | 0.0% | 0.424 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|      ALL |   11 |  109.5 | 0.0% | 0.424 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   11 |  109.5 | 0.0% | 0.499 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   11 |  109.5 | 0.0% | 0.499 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available