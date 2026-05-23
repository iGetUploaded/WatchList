# 📋 My Anime Watchlist

A fully offline, single-file anime tracking app that runs directly in your browser — no account, no server, no install required. Just open the HTML file and start tracking.

---

## Getting Started

Download `main.html` and open it in any modern browser. That's it.

Your list starts empty. Add anime manually using the **+ Add** button, or load an existing list with **↑ Import**.

---

## Features

### Adding Anime
Click **+ Add** to add a new entry. You can provide:
- **Title** — the anime's name
- **Episodes** — total episode count (use `18+` to flag adult content)
- **Status** — Watching, Completed, Plan to Watch, or Dropped
- **Category** — a custom tag to group anime (e.g. "Action", "Romance", "Ongoing")
- **Note** — any personal notes

### Tracking Progress
Each card has an episode counter. Type in the number of episodes you've watched and the progress bar updates automatically. When you hit 100%, the bar turns green.

### Statuses
Every anime can be assigned one of four statuses, shown as a colored left border on each card:

| Status | Color |
|---|---|
| Watching | Blue |
| Completed | Green |
| Plan to Watch | Amber |
| Dropped | Red |

Click the **stat tabs** at the top to filter by status.

### Notes
Click any anime's title or the note preview text to open a note editor. Notes support multi-line text and are searchable.

### Search & Filter
- **Search bar** — filters by title or note content in real time
- **Sort** — order by Original, A→Z, Z→A, Status, Most/Fewest Episodes, or Recently Added
- **Category filter** — filter to a specific category
- **Letter bar** — jump to anime starting with a specific letter

### Bulk Actions
Click **☑ Bulk** to enter bulk mode. Check multiple cards, then:
- Set the same status on all selected anime at once
- Remove all selected anime at once

### Random Picker
Click **🎲 Random** to have the app pick a random anime from your list. You can narrow the pool to only Plan to Watch, Currently Watching, or Not Set entries — useful for deciding what to watch next.

### Duplicate Detector
Click **🔍 Dupes** to scan your list for entries with identical or very similar titles.

### Import
Click **↑ Import** and either:
- **Drag & drop** a `.json` file onto the drop zone
- **Browse** for a file
- **Paste** raw JSON directly into the text box

Importing merges with your existing list — existing titles are updated, new ones are added.

The expected JSON format is an array of objects:
```json
[
  {
    "title": "Fullmetal Alchemist: Brotherhood",
    "episodes": "64",
    "status": "completed",
    "progress": 64,
    "category": "Action",
    "note": "One of the best."
  }
]
```
All fields except `title` are optional.

### Export
Click **↓ Export** to download your list in three formats:
- **JSON** — full data, can be re-imported later
- **CSV** — opens in Excel or Google Sheets
- **TXT** — plain text list

Exports respect your active search/filter — so you can export just your "Plan to Watch" list, or just anime in a specific category.

### Light / Dark Mode
Click **☀ Light** / **🌙 Dark** to toggle the theme.

### Print
Click **🖨 Print** to open the browser print dialog. The UI chrome is hidden and the grid prints cleanly.

---

## Data & Privacy

Everything stays in your browser. There is no backend, no account, and no data is ever sent anywhere. Your list exists only in the HTML file's session — to keep it permanently, **export to JSON** and re-import it next time.

> 💡 **Tip:** Keep your exported JSON file as your "save file." Each time you finish a session, export JSON. Next time, open the HTML and import it back.

---

## File Format Reference

| Field | Type | Description |
|---|---|---|
| `title` | string | Anime title (required) |
| `episodes` | string | Episode count, or `"18+"` for adult content |
| `status` | string | `watching`, `completed`, `plan`, or `dropped` |
| `progress` | number | Episodes watched so far |
| `category` | string | Custom grouping tag |
| `note` | string | Personal notes |
