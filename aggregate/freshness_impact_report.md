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

🟢 **M+**: FRESH precision (70.8%) is 31.9% HIGHER than DEGRADED (38.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.6%) is 3.0× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.4%) is 2.7× the overall rate (3.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 31.2% | 0.623 | 0.6 |       77 | 70.8% |  48.6% | 1.6× | 16.7% |   0.4545 |
|       OK |   42 |   36.7 | 7.1% | 0.507 | 0.1 |       42 | 0.0% |   0.0% |    - | 8.1% |   0.1190 |
| DEGRADED |  111 |  117.1 | 16.2% | 0.482 | 0.2 |      111 | 38.9% |  30.4% | 1.9× | 12.5% |   0.2072 |
|      ALL |  230 |   67.4 | 19.6% | 0.534 | 0.3 |      230 | 53.3% |  38.1% | 1.9× | 12.6% |   0.2739 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 2.6% | 0.557 | 0.0 |       77 | 100.0% |  15.4% | 5.9× | 0.0% |   0.1688 |
|       OK |   42 |   36.7 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  111 |  117.1 | 0.0% | 0.392 | 0.0 |      111 |    - |   0.0% |    - | 0.0% |   0.0450 |
|      ALL |  230 |   67.4 | 0.9% | 0.446 | 0.0 |      230 | 100.0% |  11.1% | 12.8× | 0.0% |   0.0783 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   77 |   12.3 | 10.4% | 0.609 | 0.1 |       77 | 12.5% |  20.0% | 1.9× | 9.7% |   0.0649 |
|       OK |   42 |   36.7 | 2.4% | 0.533 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  111 |  117.1 | 0.0% | 0.502 | 0.0 |      111 |    - |   0.0% |    - | 0.0% |   0.0090 |
|      ALL |  230 |   67.4 | 3.9% | 0.543 | 0.0 |      230 | 11.1% |  16.7% | 4.3× | 3.6% |   0.0261 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   26 |  101.4 | 42.3% | 0.576 | 0.4 |       26 | 45.5% |  71.4% | 1.7× | 31.6% |   0.2692 |
|      ALL |   26 |  101.4 | 42.3% | 0.576 | 0.4 |       26 | 45.5% |  71.4% | 1.7× | 31.6% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   26 |  101.4 | 0.0% | 0.543 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   26 |  101.4 | 0.0% | 0.543 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   26 |  101.4 | 0.0% | 0.566 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |  101.4 | 0.0% | 0.566 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available