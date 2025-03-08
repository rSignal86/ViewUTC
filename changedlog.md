## Changelog: V(U)iew(TC) GHv2.5.1 to GHv2.6
# Added
D-Layer Absorption Impact: Introduced a new factor in the propagation model based on A Index (Low = 0.5 for A ≤ 10, Moderate = 1.0 for A ≤ 25, High = 1.5 for A > 25). Negatively affects daytime conditions for lower bands     (80m-40m, 30m-20m).
Speech Synthesis Buttons: Added five buttons under the SFI/A/SN box to read aloud SFI, A Index, SSN, Kp, and D-Layer Absorption using the browser's speech API.
Solar Image Toggle: The solar image can now be clicked to toggle between normal (200px) and enlarged (400px) sizes with a smooth transition effect.
Enhanced Propagation Logic: Updated thresholds and logic for all bands (80m-40m, 30m-20m, 17m-15m, 12m-10m) with specific day/night variations and D-layer adjustments (see documentation for details).
Timestamp in Console Logs: Added getTimestamp() to include date and time in all console messages, improving debugging and transparency.

# Updated
Band Grouping: Adjusted from individual bands to groups (80m-40m, 30m-20m, 17m-15m, 12m-10m) to reflect shared propagation behavior, with fine-tuned thresholds.
Kp Speedometer Styling: Improved visual design with a wider needle (8px black + 12px white) and gradient color (green-yellow-red) for better contrast and readability.
Data Fetch Reliability: Added ?${new Date().getTime()} to NOAA and SDO URLs to prevent caching and ensure fresh data.
Version Check Message: The GitHub version check now displays a more informative message, including a link to the update if a new version is available.

# Removed
Redundant Code: Removed unused variables and styling rules from previous versions to streamline the code.
Static Band Conditions: Replaced static band statuses with dynamic calculations based on the updated model, removing older thresholds from 2.5.1.

# Fixed
Clock/Date Format: Ensured consistent UTC display with zero-padding (e.g., "01" instead of "1") for hours, minutes, seconds, and date.
Error Handling: Improved error handling in fetchKpData, fetchAIndex, and fetchSFIandSSN with clear console messages and fallback display (e.g., Kp speedometer shows "Error" on failure).

# Notes
This update focuses on a more realistic propagation model, user-friendliness (speech and image interaction), and code efficiency.
Full propagation documentation is available in HFPropagationModel-GHv2.6.md on the GitHub repository.

# Version GHv2.5.1
Bug fix:
- HF propagation model dident wanted to update every hour like the rest. even though it had the data every hour.
- JPG file got a strange timestamp on load, that is removed now.
- Did not got timestamp om some console Message.
