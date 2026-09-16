# StudySprint

StudySprint is a private, browser-based learning workspace for turning raw study material into structured revision and active recall.

## Product

StudySprint is designed as a lightweight learning OS rather than a notes page. It processes material locally and turns it into:

- Key-point summaries
- Definitions
- Recurring concepts
- Study priorities
- Flashcards
- Recall questions
- Timed focus sessions
- Session analytics

## Core capabilities

- PDF, TXT and Markdown import
- Browser-side PDF text extraction
- Local study intelligence engine
- Active-recall flashcards
- Multiple-choice recall lab
- 10, 20, 30 and 60 minute focus sprints
- Session history and recall accuracy
- Search within the current study set
- Offline-first application shell
- Responsive desktop and mobile interface
- No account, backend or paid API required

## Architecture

The project is intentionally framework-free so it stays easy to deploy on GitHub Pages and easy to inspect as a portfolio project.

- `index.html` provides the application shell and semantic views
- `styles.css` contains the product UI system and responsive layout
- `app.js` manages application state, interactions, timers and rendering
- `engine.js` contains the local text-analysis and question-generation engine
- `sw.js` provides the offline application shell
- `manifest.webmanifest` defines the installable web app metadata

## Privacy model

Study material is processed in the browser. The project does not require an account or application server for its core workflow. Study data and session history are stored locally in the browser.

PDF extraction uses PDF.js loaded from a public CDN when available. The core study workflow does not require a paid API.

## Deploy

The repository includes a GitHub Pages workflow under `.github/workflows/pages.yml`.

For local development, serve the repository with a local HTTP server because ES modules and service workers are restricted when opening files directly from `file://`.

Example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Product direction

The project is structured for future additions such as IndexedDB document libraries, richer mastery analytics, spaced review scheduling, keyboard-first navigation and additional local document processing.
