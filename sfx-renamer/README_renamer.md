# SFX Renamer — Naming Convention Tool

A lightweight, browser-based tool for game audio sound designers to batch-rename audio files according to a custom naming convention defined by the lead.

No installation. No backend. One HTML file.

---

## What it does

SFX Renamer lets you define a naming convention from scratch, load a batch of audio files, fill in the naming fields for each file, and apply the rename — all inside the browser.

The workflow is split into four steps:

1. **Define Convention** — Set a project name, separator character, and build your label structure. Each label is a "slot" in the final filename. Labels can be free text, a fixed enum list (rendered as a dropdown), or a padded number.
2. **Load Files** — Drag and drop or browse to select your audio files. Supports `.wav`, `.ogg`, `.mp3`, `.flac`, `.aif`, `.aiff`.
3. **Rename** — Fill in the label fields for each file in a table. Select multiple files and use **Apply to Selected** to batch-assign a value to a label across all selected rows. The final filename preview updates live.
4. **Apply** — Review the rename log and apply. On supported browsers (see below), files are written directly to a folder you select on disk. On Firefox, a ZIP archive is downloaded instead.

Conventions can be **exported and imported as JSON**, so lead sound designers can share a convention file with the whole team and everyone works from the same structure.

---

## Browser compatibility

| Browser | File output method |
|---|---|
| Chrome | ✅ Direct write to folder (File System Access API) |
| Edge | ✅ Direct write to folder (File System Access API) |
| Opera GX | ✅ Direct write to folder (File System Access API) |
| Brave | ✅ Direct write to folder (File System Access API) |
| Arc | ✅ Direct write to folder (File System Access API) |
| Firefox | ⬇ ZIP download |

> **Note:** The File System Access API does not rename files in-place. When you apply the rename, the browser writes the renamed files to a destination folder you choose. You can select the same folder as your source files. Original files are not deleted automatically.

---

## Features

- Custom label builder — free text, enum list, padded number
- Drag-to-reorder labels
- Live filename preview while filling in fields
- Batch apply a value to multiple files at once
- Export / import convention as `.json`
- Force or keep original file extension
- Rename log with old → new filename mapping
- Summary card showing ready vs. incomplete files
- Single `.html` file — no dependencies, no install, works offline

---

## Usage

Download `SoundRenamer_Tool.html` and open it in your browser. That's it.

Or use it directly via GitHub Pages:
```
https://<your-username>.github.io/sfx-renamer/SoundRenamer_Tool.html
```

---

## Naming convention example

A typical game audio convention might look like this:

```
SFX_ENV_Wind_Soft_01.wav
│   │   │     │    │
│   │   │     │    └── Version (number, padded)
│   │   │     └─────── Variant (free text)
│   │   └───────────── Object (free text)
│   └───────────────── Category (enum: ENV, CHAR, UI, VEH, WEAPON)
└───────────────────── Prefix (free text)
```

Separator, label names, label types, and value lists are all configurable.

---

## Tech stack

- Vanilla HTML + CSS + JavaScript
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (Google Fonts)
- [JSZip](https://stuk.github.io/jszip/) (loaded from CDN on Firefox fallback only)
- File System Access API (Chrome / Edge / Opera GX / Brave / Arc)

---

## License

MIT — free to use, modify, and distribute.
