<p align="center">
  <img src="mewscope-icon.svg" width="128" height="128" alt="Mewscope"/>
</p>

<h1 align="center">Mewscope</h1>

<p align="center">A browser-based save file viewer for <a href="https://store.steampowered.com/app/2294060/Mewgenics/">Mewgenics</a> — inspect your cat roster, track stats, and explore bloodlines without leaving the browser.</p>

<p align="center">
  <em>All parsing happens client-side. Your save file never leaves your machine.</em>
</p>

---

## Features

- **Dashboard** — current day, gold, food, completion %, unlocked zones, and inventory at a glance
- **Cat Browser** — searchable, sortable table of every cat with class, HP, XP, gender, abilities, and stat focus
- **Pedigree Tree** — interactive family tree visualizing parent → child relationships across generations

## Usage

1. Open the app in your browser
2. Drop your `.sav` file onto the upload zone, or click it to browse

Save files are located at:

```
%APPDATA%\Glaiel Games\Mewgenics\<steamid>\saves\
```

Files are named `steamcampaign01.sav`, `steamcampaign02.sav`, etc.

## Tech Stack

| Tool | Purpose |
|------|---------|
| [sql.js](https://sql.js.org) | In-browser SQLite (WebAssembly) |
| `DataView` | Little-endian binary blob parsing |
| [D3.js](https://d3js.org) | Pedigree hierarchical tree layout |
| Vanilla JS | UI |

## Privacy

**Never commit save files to this repository.** Save files (`.sav`) contain your personal Steam ID and playtime data.

The following are excluded from version control via `.gitignore`:

- `*.sav` — Mewgenics save files (contain Steam ID, personal game state)
- `.claude/` — local project notes (not for distribution)
- `.env` — any local environment config

If you fork this project, review `.gitignore` before pushing to ensure no personal data is included.
