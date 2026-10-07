# TaskPilot — Intelligent Work OS

A from-scratch rebuild for the "Does the AI Assistant Actually Pay Off?"
challenge — one self-contained web app, no framework, no install step.

## Why this version instead of the Streamlit one

The earlier Streamlit build fought back at every turn: every click re-ran the
whole page, custom CSS clashed with Streamlit's own styling and its
"refreshing" dimming effect, and a couple of widget-key bugs slipped through.
This version is plain HTML/CSS/JavaScript in one file — no full-page reruns,
full control over the look, and far fewer moving parts to break.

## Run it

There's nothing to install. Just open `taskpilot.html` in any modern browser
(double-click it, or drag it into a browser window). That's the whole setup.

Your tasks and logged runs are saved in that browser's local storage, so they
persist between visits on the same device/browser.

## What's inside

- **Overview** — a live readout of overdue/due-today/open/high-priority
  counts, a natural-language command bar, a next-action recommendation, and
  an evidence snapshot pulled from the AI Impact Lab.
- **My Work** — add, search, filter and manage tasks (priority, due date,
  project, tags). Click "Break into steps" on any task to get an
  ordered checklist — from AI if you've added a key, from built-in
  deterministic logic if you haven't.
- **AI Impact Lab** — log AI-assisted vs. No-AI runs with a real live
  stopwatch, then get a computed scorecard and a plain-English verdict
  derived from the numbers (never scripted to favor AI), plus CSV export.

## Live AI (optional)

Open the "AI connection" panel in the sidebar and paste an OpenAI API key.
The Model field is plain text, so use whatever your account can reach —
gpt-4o-mini is the default. The key is stored only in your browser's local
storage and is sent straight to OpenAI's API from your machine — it never
passes through any other server.

Without a key, task creation, quick-add parsing, task decomposition and the
next-action insight all still work from deterministic local logic.

## Why this fits the brief

- Measures actual time, not a feeling — the built-in stopwatch logs real
  elapsed seconds per run.
- Reports a balanced scorecard — the verdict always cites both effective
  time (time + rework) and the defect delta, and calls out when speed
  improved at a quality cost instead of hiding it.
- Says where AI helped versus where it slowed things down — the verdict
  logic can and does report a manual win when the data shows one.

## About the earlier Python/Streamlit version

It's still in this project if you need it (app.py, requirements.txt),
but this HTML app is the current, recommended version.
