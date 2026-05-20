# Wwise Session Analysis Tool

A lightweight, standalone browser tool for game audio QA. Load a `.txt` file exported from the Audiokinetic Wwise Profiler and get instant aggregated metrics across the full session.

No installation. No server. One HTML file.

---

## What it does

Parses a Wwise Profiler performance counter export (`.txt`) and aggregates all metrics across the full recording session, giving you a single clear picture of your game's audio performance.

Three analysis modes are accessible via the tab bar:

### Fast Analysis
Full session overview at a glance:
- **CPU** — total and plugin usage (average, peak, P95)
- **Voices** — physical, virtual, and total voice counts
- **Memory** — Wwise RAM usage
- **Media** — loaded media and SoundBanks
- **Streaming** — streaming bandwidth

### QA Audit
Set your own project hard limits and get a colour-coded compliance verdict:
- Configurable thresholds for CPU average, CPU peak, physical voices, and total media size
- Configurable WARN threshold (% of hard limit)
- Results displayed as green / amber / red blocks for instant readability

### Loudness Check
Estimated integrated loudness based on Profiler data:
- Estimated integrated loudness (ITU-R BS.1770 gate-based approximation on Short-term/Instance A)
- Momentary max, short-term max, and output peak
- Configurable target with ±2 LUFS tolerance

> **Note:** Loudness data requires explicit activation of the Loudness Meter in Wwise Profiler Settings (`Alt+G`) before capture. Output Peak is a sample peak, not an inter-sample True Peak.

---

## How to export from Wwise Profiler

1. Open the Wwise Profiler and connect to your game session
2. Enable **Save Performance Counters** in the Profiler Settings
3. Activate the **Loudness Meter** via `Alt+G` if you need loudness data
4. Run your game session
5. In the Profiler, go to **File → Save Performance Counters** and export as `.txt`
6. Load the `.txt` file into this tool

---

## Usage

Download `WwiseSessionAnalysisTool.html` and open it in your browser. That's it.

Or access it directly via GitHub Pages:
```
https://<your-username>.github.io/audio-tools/wwise-session-analysis/WwiseSessionAnalysisTool.html
```

---

## Features

- Zero dependencies — runs fully offline after first load (Google Fonts optional)
- Three analysis modes in a single file
- Configurable QA hard limits and warn thresholds
- P95 percentile CPU reporting alongside average and peak
- Colour-coded results for fast readability
- Works on any modern browser

---

## Tech stack

- Vanilla HTML + CSS + JavaScript
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (Google Fonts)
- [Tabler Icons](https://tabler.io/icons)

---

## License

MIT — free to use, modify, and distribute.
