# AniTrack

A personal anime tracking web app — built as a single HTML file, no install required.

---

## Getting Started

1. Download `main2.html`
2. Open it in any modern browser
3. Import your anime list via **⇅ Import / Export**

> **Note:** Data is memory-only — it clears on refresh. Export your list before closing the tab.

---

## Features

### Status Lists
Anime can be assigned to one of six statuses, each with its own sidebar tab:

| Status | Description |
|---|---|
| **All** | Combined view of every entry across all statuses |
| **Watching** | Currently airing/watching |
| **Completed** | Finished |
| **Dropped** | Abandoned |
| **Plan to Watch** | Queued for later |
| **Waiting** | Waiting for next season or a movie release |
| **NSFW / 18+** | Separate tab for adult content |

---

### Import / Export
Access via **⇅ Import / Export** in the nav bar.

**Export formats:**
- `.json` — full data export including all fields
- `.txt` — human-readable formatted list
- Copy to clipboard as JSON

**Import formats:**
- `.json` — AniTrack exports or compatible JSON
- `.txt` — AniTrack TXT exports
- `.xml` — MyAnimeList export files (exported from MAL profile → Export)

**Import options:**
- **Merge** — keeps existing entries, adds new ones (skips duplicates by ID)
- **Replace** — wipes current list and replaces with imported data

**After importing**, a green summary banner appears showing how many anime were added and how many duplicates were skipped.

**Status mapping from MAL XML:**

| MAL Status | AniTrack Status |
|---|---|
| Watching | Watching |
| Completed | Completed |
| On-Hold | Plan to Watch |
| Dropped | Dropped |
| Plan to Watch | Plan to Watch |

---

### Add / Edit Anime
Click **＋ Add Anime** or the **✎** icon on any row.

Fields available:
- Title, Sub-title / Info
- Status, Format (TV, TV Short, Movie, Special, OVA, ONA, Music)
- Score (0–10, decimals supported — 0 is treated as unscored)
- Episodes Watched / Total Episodes
- Rating (G, PG, PG13, R, R+, Rx)
- Genres (comma-separated)
- Cover Image URL

---

### Views
Toggle between two display modes using the **☰ / ▦** buttons in the toolbar:

**Table view** — default, shows score, progress bar, +/− episode controls, edit/delete actions

**Grid view** — poster wall with:
- Cover art thumbnails
- Score badge overlaid on cover
- Status color dot
- Progress bar along bottom edge
- Hover to reveal edit/delete buttons
- Hover preview panel showing format, status, genres, score, progress

> Grid view is not available on Duplicates or Broken Covers tabs.

---

### Filters & Sorting
Located in the sidebar under **Filters**:

- **Format** dropdown — filter by TV, TV Short, Movie, Special, OVA, ONA, Music
- **Rating** multi-select — check one or more: PG, PG13, G, R, R+, Rx
- **Sort** dropdown — Score, Title, Progress, Date Added

The toolbar search box filters by title or sub-title within the current tab.

---

### Tools (Sidebar)

#### 🎲 Random Picker
Picks a random anime from your **Plan to Watch** list with a slot-machine animation.
- **▶ Start Watching** — moves the picked anime to Watching
- **Skip** — removes it from this session's pool and spins again
- Resets automatically when all options are skipped

#### 📤 Share List
Encodes your entire list into a URL. Anyone with the link sees a read-only card grid of your list — no account needed.
- **Preview** button shows exactly what others will see
- Warning shown if URL is very long (large lists may hit browser limits)

#### ⚠ Duplicates *(auto-detected)*
Appears automatically when duplicate titles are found after import.
- Groups entries by title (case-insensitive)
- Shows status, score, and progress for each copy
- Delete the unwanted copies — tab disappears when list is clean

#### 🔗 Broken Covers *(auto-detected)*
Appears automatically after import when cover images fail to load or are missing.
- Shows the broken URL so you know what to fix
- Click ✎ to edit and paste a working image URL
- Tip shown at bottom of the list

---

### Currently Watching Banner
Appears automatically below the profile section when you have anime in the **Watching** tab.
- Shows cover art thumbnails, title chips, and episode progress summary
- Click any title or cover to jump to the Watching tab
- Hides when Watching list is empty

---

### Editable Profile Name
Click your name or avatar to set a custom display name. Updates the avatar initial automatically.

---

### Episode Controls
- **− button** disables when episode count is at 0
- **+ button** disables when episode count reaches the total
- Auto-moves anime from **Watching → Completed** when you hit the final episode

---

## Removed / Cleaned Up

| What | Why |
|---|---|
| Firebase / Google login | Too many browser compatibility issues with GitHub Pages; removed in favour of Import/Export |
| Nav bar search box | Redundant — three search boxes existed at once; only toolbar search kept |
| Sidebar search box | Same as above |
| Sidebar Sort By link list | Replaced with compact dropdown in Filters section |
| Sidebar Format filter link list | Replaced with compact dropdown in Filters section |
| Dead `.nav-search` CSS | Leftover after nav search was removed |
| AniList search (auto-fill) | Blocked by CORS on GitHub Pages; removed |
| localStorage persistence | Intentionally removed — data is memory-only, use Import/Export to save |

---

## File Info

- **Single HTML file** — no dependencies, no server, no install
- **Fonts** — Rajdhani, Inter, JetBrains Mono (loaded from Google Fonts)
- **Data** — lives in memory only; clears on page refresh
- **Compatible** — works in any modern browser (Chrome, Firefox, Edge, Safari)
