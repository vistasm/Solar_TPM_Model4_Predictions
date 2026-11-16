# Solar_TPM_Model4_Predictions
Solar flare prediction blind test — Model 4 ("Ranger"). Daily forecasts for M+, M5+, X+ flares using NeuralNet (M+/X+) and LogReg (M5+) with Combined+Persist and Combined features. Predictions committed before the [06:00 UTC D+1, 06:00 UTC D+2) forecast window opens. Signed commits, append-only.

---

## Service Note: DONKI API Migration — October–November 2026

### What happened

On **2026-09-30**, NASA's Community Coordinated Modeling Center (CCMC) moved the public DONKI API from `https://kauai.ccmc.gsfc.nasa.gov/DONKI/WS/get/` to `https://ccmc.gsfc.nasa.gov/DONKI-API/get/` ([CCMC announcement](https://ccmc.gsfc.nasa.gov/news/major-updates/)). Query parameters and the JSON response format did not change.

Every pipeline in this project (Models 1–4: Sniper, Catcher, Sweeper, Ranger) fetched the DONKI flare catalog from the old address. Once the move happened, the old host first returned an HTML announcement page instead of JSON (logged as `Expecting value: line 1 column 1 (char 0)`). Later it stopped responding altogether (`Network is unreachable`). The DONKI fetch had no error handling, so this one failure stopped the whole daily run before inference.

### Impact on daily predictions

- **Affected target dates:** 2026-10-01 through 2026-10-30, all four models.
- On each of these days the pipeline published a `FAILED` prediction JSON instead of a forecast. Those failure records are still in this repository's commit history.

### Fix and backfill: 2026-10-30

- All four daily inference scripts were moved to the new DONKI endpoint on **2026-10-30**.
- The same day, every failed target date was **backfilled** by re-running the pipeline with `--date <asof_date>`, oldest first. Each backfill commit replaced the `FAILED` JSON for that date.
- **Transparency note:** backfilled predictions were generated *after the fact* on 2026-10-30, not in real time on the original publication date. Each run used only data up to its as-of date. However, the DONKI catalog it read may include flare records that were not yet published at the original 05:20 UTC run time. These predictions are therefore not strictly blind forecasts, and they should be weighted accordingly when judging live performance. Model 3 (Sweeper) uses DONKI for output metadata only, not as a model input, so its backfilled forecasts don't depend on late-published DONKI data. The commit timestamps for every backfilled file record when it was actually produced.

### Impact on monthly retraining

- The monthly retrain scripts fetch the same DONKI catalog, and they abort before training if that fetch fails. Retraining is scheduled for the 1st of each month. **Two scheduled retrains were missed for all four models:**
  - **2026-10-01:** failed at the DONKI fetch (HTML response instead of JSON).
  - **2026-11-01:** failed at the DONKI fetch (old host unreachable).
- In both cases no new model was swapped in. All production predictions from 2026-10-01 until the next successful retrain, including the backfilled ones, therefore used the model artifacts trained on **2026-09-01**, the last successful retrain.
- The retrain scripts for all four models were moved to the new endpoint on **2026-11-16**. Each was checked with a dry run, in which all training checkpoints passed and no model was swapped.
- No retrain was swapped in mid-cycle. Solar activity in September and October 2026 was low, so a rolling-forward retrain would have changed little, and keeping monthly model boundaries keeps the evaluation record clean. The next scheduled retrain runs on **2026-12-01**.

### Hardening added

- The DONKI endpoint is now a configurable list (`DONKI_FLR_ENDPOINTS`), so a future move is a one-line change.
- Each DONKI request is retried 3 times with backoff, and non-JSON responses (such as an HTML page) are detected and reported explicitly.
- **Daily inference** no longer stops when DONKI is unreachable. It continues with the cached flare catalog, and the resulting data lag is reflected in the `lag_bucket`. Each prediction JSON now records `donki_fetch_status` and `donki_endpoint` under `persistence_status`, so any degraded day is visible in the published record.
- **Monthly retraining** still fails closed if DONKI cannot be reached. A model trained on incomplete flare labels is never swapped into production.

### Timeline

| Date (UTC) | Event |
|---|---|
| 2026-09-01 | Last successful monthly retrain (all four models) |
| 2026-09-30 | CCMC moves DONKI API to `ccmc.gsfc.nasa.gov/DONKI-API` |
| 2026-10-01 | Scheduled monthly retrain fails at DONKI fetch; 2026-09-01 models remain live |
| 2026-10-01 → 2026-10-30 | Daily runs fail at DONKI fetch; `FAILED` JSONs published |
| 2026-10-30 | Daily scripts fixed; all missed dates backfilled |
| 2026-11-01 | Scheduled monthly retrain fails at DONKI fetch; 2026-09-01 models remain live |
| 2026-11-16 | Retrain scripts fixed and verified by dry run |
| 2026-12-01 | Next scheduled retrain (first on the new endpoint) |

*DONKI data courtesy of NASA's Community Coordinated Modeling Center (CCMC) at Goddard Space Flight Center.*
