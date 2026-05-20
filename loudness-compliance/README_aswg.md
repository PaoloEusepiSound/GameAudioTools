# ASWG-R001 Loudness Compliance Tool

A standalone browser tool for verifying average loudness compliance against the PlayStation Studios ASWG-R001 v1.2 recommendation across multiple gameplay sessions.

No installation. No server. One HTML file.

---

## What it does

Aggregates loudness data from multiple gameplay sessions and produces a single binary compliance verdict against the ASWG-R001 standard:

| Platform | Integrated Loudness Target | True Peak Max |
|---|---|---|
| Home (TV) | −24 ±2 LKFS | −1 dBTP |
| Portable | −18 ±2 LKFS | −1 dBTP |

Three input modes are supported, selectable via the mode bar:

### Wwise Profiler
Upload one or more `.txt` exports from the Audiokinetic Wwise Profiler (one file per gameplay session).
- Integrated loudness estimated via Short-term average with −70 LUFS gate
- Output peak extracted as sample peak
- Session duration parsed from the Profiler timestamp data

### Youlean CSV
Upload one or more `.csv` exports from Youlean Loudness Meter.
- Reads certified ITU-R BS.1770 integrated loudness and True Peak Max directly from the file header
- Session duration parsed from timecodes
- Most accurate input mode for compliance purposes

### Manual Input
Enter integrated LUFS and True Peak values by hand for any number of sessions. Useful when you already have measured values from another metering tool.

---

## Output

All three modes produce:

- **Arithmetic mean** and **duration-weighted mean** of integrated loudness across all sessions
- **Loudness range** — max and min session values with session attribution
- **Peak stats** — peak max, average, and min across sessions
- **Session duration statistics** — individual and total
- **Binary ASWG-R001 compliance verdict** — PASS or FAIL

Wwise Profiler and Youlean CSV modes also include a **Full Report CSV export** with all key data and a per-session breakdown.

---

## How to export from Wwise Profiler

1. Open the Wwise Profiler and connect to your game session
2. Enable **Save Performance Counters** in Profiler Settings
3. Activate the **Loudness Meter** via `Alt+G`
4. Run a complete gameplay session
5. Export via **File → Save Performance Counters** as `.txt`
6. Repeat for each session you want to include in the aggregate

## How to export from Youlean Loudness Meter

1. Run your gameplay session with Youlean Loudness Meter active
2. At the end of the session, export via **File → Export to CSV**
3. Repeat for each session

---

## Usage

Download `ASWG_LoudnessComplianceTool.html` and open it in your browser. That's it.

Or access it directly via GitHub Pages:
```
https://<your-username>.github.io/audio-tools/loudness-compliance/ASWG_LoudnessComplianceTool.html
```

---

## Important notes

- **Wwise Profiler mode:** integrated loudness is an *estimate* based on Short-term data. For certified compliance measurement, use Youlean CSV or Manual Input with data from a certified meter.
- **True Peak:** Wwise Profiler mode reports sample peak, not inter-sample True Peak (dBTP). Only Youlean CSV mode provides certified True Peak values.
- **Session coverage:** for a meaningful compliance result, each session should represent a complete, representative gameplay segment (main menu, in-game, cutscenes, etc.).

---

## Reference

- [ASWG-R001 Recommendation (Audio Standards Working Group)](https://www.audiostandards.org)
- [ITU-R BS.1770 — Algorithms to measure audio programme loudness](https://www.itu.int/rec/R-REC-BS.1770/en)
- [EBU R 128 — Loudness normalisation and permitted maximum level](https://tech.ebu.ch/publications/r128)

---

## Tech stack

- Vanilla HTML + CSS + JavaScript
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (Google Fonts)
- [Tabler Icons](https://tabler.io/icons)

---

## License

MIT — free to use, modify, and distribute.
