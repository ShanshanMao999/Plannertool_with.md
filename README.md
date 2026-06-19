# Annual Planner

A single-file task management app with Gantt charts, priority sorting, and AI-powered `.md` import.


## Features

- **All tasks view** — full task list, auto-sorted by priority (P0+ → P0 → P1 → P2), with completion tracking
- **Year overview** — annual Gantt chart showing all tasks grouped by category (Thesis, Academic, Career, Platform, Life, Side)
- **Month detail** — monthly Gantt chart + task list with per-day hour estimates
- **Chat / Import** — natural language task management powered by Claude API, or bulk-import from `.md` files
- **Dark mode** — automatic, follows system preference
- **Offline-first** — all data stored in localStorage, no server required
- **Mobile responsive** — sidebar collapses on small screens

## Quick Start

1. Download `planner-app.html`
2. Open in Chrome:
   ```bash
   open -a "Google Chrome" planner-app.html
   ```
3. Start adding tasks

### Install as Desktop App (macOS)

1. Open `planner-app.html` in Chrome
2. Click the install icon in the address bar (or Menu → Cast, save and share → Install page as app)
3. A purple "P" icon appears in your Dock

### Install as Mobile App (iOS)

1. Open `planner-app.html` in Safari
2. Tap Share → Add to Home Screen

## Import from Markdown

You can bulk-import tasks from a `.md` file. Use the included `planner-template.md` as a starting point.

### Format

```markdown
### Task Name
- name: Task Name
- priority: p0+
- category: thesis
- start: 2026-05-01
- end: 2026-05-31
- hours: 40
- desc: Description of the task
```

### How to import

**Option A — Drag & drop:** Drag your `.md` file onto the sidebar drop zone

**Option B — Click to upload:** Click the drop zone and select your file

**Option C — Paste:** Go to Chat, click "Paste / upload doc", paste your markdown, click "Parse and sync"

The AI will diff your document against existing tasks and add/update/delete accordingly.

## Chat Commands

The Chat view accepts natural language (requires Anthropic API key):

- `"Add task: literature review, P0, thesis, May 1-31, 20h"`
- `"Move conference submission to April 10"`
- `"Mark experiment batch A as done"`
- `"Delete the exercise task"`

Your API key is stored in localStorage only — never sent anywhere except the Anthropic API.

## Priority Levels

| Level | Meaning | Use for |
|-------|---------|---------|
| P0+ | Hard deadline | Submissions, visa deadlines |
| P0 | Must complete | Thesis chapters, experiments |
| P1 | Steady progress | Job prep, exercise, admin |
| P2 | Side project | Explorations, low priority |
| NEW | Newly added | Uncategorized tasks |

## Categories

| Category | Color | Examples |
|----------|-------|----------|
| Thesis | Orange | Chapters, experiments, writing |
| Academic | Purple | Conferences, reviews, reports |
| Career | Blue | Job search, visa, CV |
| Platform | Green | Open-source, research tools |
| Life | Gray | Health, admin, driving |
| Side | Violet | Side projects, explorations |

## Data

All data is stored in your browser's `localStorage`. To back up:

```javascript
// Export
copy(localStorage.getItem('planner_data'))

// Import
localStorage.setItem('planner_data', '...')
```

## Tech Stack

- Single HTML file, no build step
- React 18 (CDN)
- Babel standalone (in-browser JSX compilation)
- Claude API for chat features (optional)
- Zero dependencies to install

## License

MIT
