## Model Overview
This propagation model is designed to assess HF band conditions for amateur radio use, based on real-time solar and geomagnetic data from the NOAA Space Weather Prediction Center (SWPC). It integrates four primary parameters – Solar Flux Index (SFI), Sunspot Number (SSN), Kp Index, and A Index – with a day/night check based on UTC time and an additional D-layer absorption factor derived from the A Index. The model aims to balance the enhancing effects of solar activity (high SFI/SSN) against geomagnetic instability (high Kp/A), while accounting for diurnal variations and band-specific sensitivities. Results are categorized as "Good," "Fair," or "Poor", consistent with the visual design of the ViewUTC dashboard. Bands are grouped as 80m-40m, 30m-20m, 17m-15m, and 12m-10m to reflect their shared propagation characteristics under varying conditions.

# Values and Band-Specific Calculations
The model relies on the following parameters:

- SFI (Solar Flux Index): Solar radiation at 10.7 cm (higher values enhance ionization, benefiting higher bands).
- SSN (Sunspot Number): Number of sunspots, indicating ionospheric potential (higher is better).
- Kp Index: 3-hour geomagnetic activity (0–9, lower values indicate quieter conditions).
- A Index: Daily geomagnetic stability (0–400, lower values improve propagation).
- Day/Night Check: UTC time between 06:00–18:00 is daytime (D-layer absorption impacts lower bands, F-layer supports higher bands; reverses at night).
- D-Layer Impact: A multiplier based on A Index (Low = 0.5 for A ≤ 10, Moderate = 1.0 for A ≤ 25, High = 1.5 for A > 25), worsening daytime conditions on lower bands.

# Band Calculations
- 80m-40m (3.5-7 MHz)
-- Daytime (06:00-18:00 UTC):
--- Good: SFI > 80, SSN > 20, Kp ≤ 3, A ≤ 10, D-Layer Impact ≤ 1.0 (needs moderate solar activity and calm conditions despite D-layer).
--- Fair: SFI > 70, Kp ≤ 5, D-Layer Impact ≤ 1.5 (tolerates some disturbance and absorption).
--- Poor: Otherwise (high disturbance or strong D-layer absorption disrupts signals).
-- Nighttime:
--- Good: SFI > 80, SSN > 20, Kp ≤ 4, A ≤ 15 (benefits from no D-layer, tolerates slightly more disturbance).
--- Fair: SFI > 60, Kp ≤ 5, A ≤ 20 (works with lower activity, still usable).
--- Poor: Otherwise (insufficient activity or excessive disturbance).
- 30m-20m (10.1-14 MHz)
-- Daytime (06:00-18:00 UTC):
--- Good: SFI > 90, SSN > 30, Kp ≤ 3, A ≤ 10, D-Layer Impact ≤ 1.0 (requires stronger solar input, stable conditions).
--- Fair: SFI > 80, Kp ≤ 4, D-Layer Impact ≤ 1.5 (moderate activity and tolerable disturbance).
--- Poor: Otherwise (low activity or high disturbance weakens propagation).
-- Nighttime:
--- Good: SFI > 90, SSN > 30, Kp ≤ 4, A ≤ 15 (good with no D-layer, slightly relaxed stability).
--- Fair: SFI > 70, Kp ≤ 5, A ≤ 20 (still functional with lower activity).
--- Poor: Otherwise (insufficient solar support or geomagnetic interference).
- 17m-15m (18.1-21 MHz)
-- Daytime (06:00-18:00 UTC):
--- Good: SFI > 110, SSN > 50, Kp ≤ 2, A ≤ 7, D-Layer Impact ≤ 1.0 (needs high solar activity and very stable conditions).
--- Fair: SFI > 90, Kp ≤ 4, D-Layer Impact ≤ 1.5 (usable with moderate activity and some disturbance).
--- Poor: Otherwise (lacking solar strength or too unstable).
- Nighttime:
--- Good: Not achievable (higher bands typically close at night due to weaker F-layer).
--- Fair: SFI > 130, SSN > 70, Kp ≤ 3, A ≤ 10 (rare, requires exceptional solar activity).
--- Poor: Otherwise (nighttime typically shuts these bands).
- 12m-10m (24.9-28 MHz)
-- Daytime (06:00-18:00 UTC):
--- Good: SFI > 130, SSN > 70, Kp ≤ 2, A ≤ 7, D-Layer Impact ≤ 1.0 (demands peak solar activity and calm conditions).
--- Fair: SFI > 110, Kp ≤ 4, D-Layer Impact ≤ 1.5 (open with moderate activity, tolerates slight disturbance).
--- Poor: Otherwise (insufficient solar input or geomagnetic instability).
-- Nighttime:
--- Good: Not achievable (bands close at night due to ionospheric collapse).
--- Fair: Not achievable.
--- Poor: Always (nighttime propagation is negligible).

# Calculation Method
The model fetches Kp and A Index from wwv.txt for real-time accuracy, with SFI and SSN from daily-solar-cycle-indices.txt. 
The day/night check uses UTC time (06:00–18:00 for daytime), and D-layer impact is calculated as a multiplier based on A Index thresholds. 
Conditions are evaluated using nested conditional logic, prioritizing solar activity (SFI/SSN) for band openings and geomagnetic stability (Kp/A) for signal quality, adjusted by diurnal effects. 
Thresholds are tuned based on amateur radio observations, e.g., Kp ≤ 4 yields "Fair" on 12m-10m during daytime, aligning with practical HF experience.
