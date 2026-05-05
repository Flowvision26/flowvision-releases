# flowvision-releases
FlowVision desktop app — Windows binary releases
## Critical fixes & v1.1 candidate

### Compensation correctness
- Workspace save/load now applies the same compensation as the live session (worker path now matches sync path)
- FCS export preserves $SPILL / $SPILLOVER / $THRESHOLD / $TIMESTEP keywords so downstream tools (FlowJo, Kaluza, FCS Express) display compensated correctly
- Compensation Web Worker has 60s timeout protection (prevents stuck UI on edge-case failures)
- 25 unit tests added for compensation math (regression guard)

### Stats Table
- Default to -A (Area) channels only — fits A4 page even with large panels
- Compact column headers (e.g. "CD3" instead of "CD3 FITC-A" truncated)
- New Properties toggles: "Include H/W channels" + "MFI metric" (Median / GeoMean / Mean)
- Geometric Mean MFI added (industry standard for log-distributed fluorescence)

### UI / UX
- Compensation modal now shows channel aliases (e.g. "CD3 FITC-A · FL1-A")
- Help → Contact Support menu (mailto info@flowvision.io)
- About dialog shows live version + What's New section
- Update notifier banner — checks flowvision.io/version.json on startup
- Trial state IPC failures fail-secure (no longer accidentally unlock the app)

### Build pipeline
- Main process JS (trial.js, main.js, preload.js) is now obfuscated in protected builds — license secret no longer visible in plain text in the asar archive

For Research Use Only (RUO) · Windows 10/11
