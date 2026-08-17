# English Grade 8 — Tutoring Dashboard

A static HTML dashboard for planning and running twice-weekly (Tuesday &
Friday, 30 minutes, online) English tutoring sessions, built around the
**Cambridge Lower Secondary English 8** curriculum (Learner's Book 8 &
Workbook 8) and mapped onto **Selong Bay School's Academic Calendar 26/27**.

No build step — just open `index.html` in a browser, or serve the folder
with any static host (GitHub Pages works out of the box).

## What's here

```
index.html                     Main dashboard: full 9-unit curriculum outline,
                                term calendar, and an auto-generated Tue/Fri
                                session schedule for the whole school year.
assets/styles.css               Shared stylesheet for every page.
lessons/
  lesson-01-2026-08-18/         Tue 18 Aug — Unit 1: Verb tenses for effect
  lesson-02-2026-08-21/         Fri 21 Aug — Unit 1: Poetic form (enjambment & caesura)
  lesson-03-2026-08-25/         Tue 25 Aug — Unit 2: Punctuation for effect in dialogue
  lesson-04-2026-08-28/         Fri 28 Aug — Unit 2: Combining descriptive techniques
```

Each lesson folder has four pages, cross-linked by tabs:

- **`index.html`** — the lesson plan: objective, timing, why it matters for
  the exam, and notes on likely points of confusion.
- **`worksheet.html`** — the homework worksheet the student completes
  independently. Printable (`window.print()` strips the nav/buttons).
- **`slides.html`** — the slide deck to screen-share during the live
  30-minute session.
- **`script.html`** — a full, minute-by-minute teaching script: exact things
  to say, model answers, and how to handle likely confusion — written for
  someone teaching this content for the first time.

## Source documents

- **Unit Overview & Year Planner** — the school's mapping of all 9
  Learner's Book 8 units onto its term dates. Texts, writing tasks,
  language focus and 21st-century skills are all taken directly from this
  document.
- **Academic Calendar 26/27** — term dates, breaks, and public holidays.

Both are reproduced in full inside `index.html`'s curriculum outline and
its `UNITS` / `TERMS` / `BREAKS` / `PUBLIC_HOLIDAYS` data arrays (top of the
`<script>` block), which drive the auto-generated session schedule table.

## A note on the four lessons already built

The **Workbook 8** (the actual student-facing text and exercises) wasn't
available yet when these four lessons were planned. Each of the four lesson
folders uses a short **original passage or poem**, written specifically to
demonstrate that session's language-focus skill on the same theme as the
real Learner's Book unit (e.g. a nature-disaster narrative for Unit 1's
"verb tenses for effect", standing in for 'When the Mountains Roared').

Every lesson plan flags this explicitly under **"A note on the text
used."** Once the Workbook 8 is available, the authentic Cambridge
text can be swapped directly into the worksheet/slides/script for that
lesson — the surrounding activities, questions and script structure don't
need to change, since they were built to work on any passage demonstrating
the same technique.

## Extending the dashboard

To plan the next batch of lessons:

1. Pick the next Tuesday/Friday from the schedule table in `index.html`
   (rows are auto-generated — just find the next one still marked
   *Not yet planned*).
2. Duplicate a `lessons/lesson-0N-YYYY-MM-DD/` folder as a template.
3. Add the new date to the `READY_LESSONS` object near the bottom of
   `index.html`'s `<script>` block so it shows up as **Ready** with links
   in both the schedule table and the "Up next" cards.
