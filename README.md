Game Audio Tools
A suite of lightweight, standalone browser tools for game audio professionals — sound designers, audio leads, and QA engineers.
No installation. No backend. No dependencies. Each tool is a single .html file that runs entirely in the browser.

Tools
🟡 SFX Renamer
Naming Convention Tool
Define a custom naming convention, load a batch of audio files, fill in the label fields, and apply the rename — directly on disk or as a ZIP archive. Designed for sound designers working under a lead-defined naming structure across different projects.
→ Open tool

🟢 Wwise Session Analysis Tool
Profiler Performance & Loudness Analysis
Load a .txt export from the Audiokinetic Wwise Profiler and get instant aggregated metrics across the full session. Three analysis modes: Fast Analysis (CPU, voices, RAM, streaming), QA Audit (configurable hard limits with colour-coded verdict), and Loudness Check (ITU-R BS.1770 approximation).
→ Open tool

🟣 ASWG-R001 Loudness Compliance Tool
PlayStation Studios ASWG-R001 Compliance Checker
Verify average loudness compliance against the ASWG-R001 v1.2 recommendation across multiple gameplay sessions. Supports three input modes: Wwise Profiler .txt exports, Youlean Loudness Meter .csv exports, and manual entry. Produces a binary compliance verdict with full session statistics.
→ Open tool

Usage
Each tool is self-contained. Download the .html file for the tool you need and open it in your browser, or access it directly via GitHub Pages:
https://<your-username>.github.io/audio-tools/sfx-renamer/SoundRenamer_Tool.html
https://<your-username>.github.io/audio-tools/wwise-session-analysis/WwiseSessionAnalysisTool.html
https://<your-username>.github.io/audio-tools/loudness-compliance/ASWG_LoudnessComplianceTool.html
Browser compatibility
All tools run in any modern browser. The SFX Renamer uses the File System Access API for direct file writing — supported on Chrome, Edge, Opera GX, Brave, and Arc. Firefox falls back to ZIP download.

Tech stack

Vanilla HTML + CSS + JavaScript
JetBrains Mono (Google Fonts)
Tabler Icons (Wwise and ASWG tools)
JSZip (SFX Renamer — Firefox fallback only)


License
MIT — free to use, modify, and distribute.
