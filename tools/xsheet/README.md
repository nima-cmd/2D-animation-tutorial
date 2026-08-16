# X-Sheet — a timesheet tool, and the seed of a web tutorial

A small browser tool for planning animation timing, built by hand as a first HTML project.

**This file has two jobs:** document the tool, and accumulate the HTML/CSS/JS being learned while
building it — so that when a proper web-development course gets its own repo, this is its starting
material rather than a blank page.

---

## Why it exists

Not "wouldn't a tool be nice." Stated 2026-08-14, during T3-01:

> *"We've been doing a lot of work in these time sheets and writing them by hand in the chat has
> become tedious and if I'm honest has been keeping me from progressing, since the act of formatting
> and writing it here takes more time."*

**The friction was blocking the animation work.** That is the requirement the tool has to meet, and
it implies something easy to miss: the tool's job is not only to help *think* about timing, but to
get a sheet **out of the user's head and into a form Claude can read** without hand-formatting a
table in chat. Design toward that from version one — a copy-to-clipboard string, or better, a file
written into the repo.

## The design target

Not a generic table of frame numbers. A **timesheet**, following the conventions of Japanese
animation (タイムシート) — chosen deliberately so that using it doubles as preparation for
**OpenToonz's Xsheet**, which is where Track 1 ends (T1-03). Conventions verified 2026-08-14; full
citations in the repo's `references.md`.

- **Vertical.** Time runs *down*, not across. This is the biggest departure from Krita's horizontal
  timeline, and it is how both real timesheets and OpenToonz read.
- **Frame numbers in the far-left column** — exactly OpenToonz's layout.
- **A heavy rule every 24 rows**, marking each second at 24fps.
- **Columns are cel layers**, lettered `A`, `B`, `C`… with **A nearest the background**.
- **A hold is a vertical line ruled down the column.** The most important one: it makes it visually
  impossible to mistake a hold for a movement. A digital timeline hides holds in empty space, which
  is exactly how the drowsy blink's `6/8/10` error slipped through — gaps intended as an
  increasingly heavy droop instead read as the eye sitting open longer.
- **Later:** circled numbers for key drawings (*genga*), dashes for in-betweens (*douga*).
- Japanese sheets run **144 rows = exactly 6 seconds**.

## The core mechanic

**You think in durations; frame numbers are a running total.**

```
drawing A lasts 4  →  starts at frame 0
drawing B lasts 2  →  starts at frame 4      (0 + 4)
drawing C lasts 5  →  starts at frame 6      (4 + 2)
```

Each frame number is the previous number plus the previous duration. The creative work is entirely
in the duration column; converting to frame numbers is bookkeeping — which is precisely the part
worth automating.

## A correction, recorded 2026-08-15

The friction that motivated this tool had a **zero-build fix that was never offered**: a shorter
notation for chat.

```
open 6 / half 3 / open 4
```

Drawing name, hold duration, slash-separated. **No frame numbers are ever typed** — Claude does the
addition and renders the sheet back, formatted, with hold lines. The formatting burden existed only
because Claude kept asking for *frame numbers* rather than *durations*; the asymmetry was Claude's to
remove and could have been removed in one sentence.

Instead the proposal was "build an app," and across two sessions the app became the blocker while the
animation lesson it was meant to unblock went untouched.

**Two rules carried forward** (also in `~/.claude/CLAUDE.md`):
1. **When friction is reported, find the zero-build fix first.** Build afterwards, on its own merits,
   as a parallel thread — never as a gate on the work it was meant to serve.
2. **"Type this block" is still being handed the answer.** Anything containing logic: state the
   problem, let the user write it, then review. Boilerplate should be named as boilerplate. The loop
   in this tool is the clearest miss — the user had already described the record-then-advance rule in
   his own words and could have written it unaided.

## Status

| | |
|---|---|
| Started | 2026-08-14 |
| Built so far | 39 lines. A `<table>` whose rows are generated from a list of `{drawing, hold}`; frame numbers computed as a running total and **appearing nowhere in the file**. Change a duration, the column recalculates. |
| Not yet | one row per *frame* (currently one per keyframe), hold lines, second markers, cel-layer columns, looping. Durations still live in the source rather than an input. |

### Why it is still worth building (reassessed 2026-08-15)

**Not to remove tedium — that is already solved** by the durations-only chat notation. The two
reasons that survive:

1. **Learning HTML**, which is wanted independently, with `nima-cmd-work` waiting as project 2.
2. **Seeing the sheet while designing it.** Holds drawn as ruled lines would have made the
   `6/8/10` error obvious on sight. A *thinking* aid, not a communication one — and precisely what
   Krita's timeline hides.

**The curriculum keeps demanding sheets**, so this is not a one-exercise tool: T3-02 (keys at arc
peaks and impacts, squash held 1–2 frames), **T3-03 (explicitly compares a 2-frame crouch against a
6+ frame one — two sheets side by side)**, **T3-04 (8 key poses over 12–16 frames, and it *loops*)**,
T3-06 (a timing pass over the whole short), T3-07 (re-timing). The walk cycle's loop is a real
feature nothing here handles yet.

### Next session

1. **The animation goes first.** This advances alongside the lessons, never as a gate on them — see
   the correction above.
2. Then: **a text box** to paste `open 6 / half 3 / …` into, and **one row per frame with holds as
   ruled lines.** That is the point at which it becomes genuinely useful; roughly two short sessions.
3. **The user writes the code.** The problem to hand over is *"one row per frame instead of one per
   keyframe"* — he already knows the record-then-advance algorithm and can derive the inner loop.
   Everything after this is optional polish, added when a lesson actually demands it.

## HTML/CSS/JS learned here

Filled in as we go. Each entry: the concept, and *why* it is the way it is — not just the syntax.

### A tag declares what content **is**, not how it looks
`<h1>X-Sheet</h1>` says "this is a top-level heading." Appearance is specified separately, later.
That separation of *structure* from *presentation* is the central design idea of HTML and the reason
the language looks the way it does.

### HTML produces a *document tree*, not text on a page
The browser does not read HTML as instructions for drawing. It builds a **tree of nodes** from it.
The first page produced:

```
RootWebArea: "X-Sheet"        <- from <title>: the browser-tab name
  heading: "X-Sheet"          <- from <h1>: the page heading
    StaticText: "X-Sheet"
```

That tree is the real output. It is what screen readers announce, what search engines index, and —
most relevant here — **what JavaScript reaches into to change the page**. Visual appearance is
downstream of the tree, not the other way round. `<title>` and `<h1>` held identical words but did
different jobs: one named the tab, the other titled the document.

### The boilerplate, and why each line is there
- `<!doctype html>` — use modern rendering rules rather than 1990s compatibility mode.
- `<head>` — information *about* the page that is not displayed (title, encoding).
- `<body>` — everything actually shown.
- `<meta charset="utf-8">` — how to decode bytes into characters. Omit it and `タイムシート` renders
  as mojibake.

---

### A script changes only what you point it at
Confused twice, so worth stating plainly: JavaScript has no general awareness of the page. It
modifies exactly the element named in the code and nothing else.

- Writing to `#out` left the hand-typed `<table>` untouched — the table did not know the script
  existed.
- Later, pointing the script at `#sheet` instead left `<p id="out">` reading its original
  `"nothing yet"`, which *looked* like a failure and was in fact correct: nothing overwrote it.

**When output seems wrong, check whether you are looking at the element the code actually names.**

### `let` vs `const`
Both bind a name to a value. `const` means the name will never be pointed at something else; `let`
means it will. Hold durations are set once (`const`); a running counter changes every pass (`let`).
Preferring `const` is a message to a future reader: *nothing here is what changed.*

### The running total, which is the whole tool
```js
for (const step of sheet) {
  rows  = rows + "<tr><td>" + frame + "</td><td>" + step.drawing + "</td></tr>";
  frame = frame + step.hold;      // record first, THEN advance
}
```
Order is load-bearing: record the current frame, *then* add the duration. Reversed, the first drawing
would start at 6 rather than 0. **The frame numbers exist nowhere in the file** — they are derived on
every load, which is exactly the arithmetic worth removing from a human.

### Objects vs arrays
`[6, 3, 4]` is an ordered list and cannot say *which drawing*. `{ drawing: "open", hold: 6 }` bundles
related values under names, reached with a dot: `step.hold`. Once a thing has more than one property,
it wants to be an object.

### `innerHTML` vs `textContent`
- `textContent` — treat this as **plain text**. Given `<tr>`, it displays the literal characters.
- `innerHTML` — **parse this as HTML** and build real elements. This is how a built-up string becomes
  actual table rows.

Caveat worth carrying: `innerHTML` with text originating from anyone else is how code gets injected
into a page. Safe here because every character is authored locally — but this is why it is argued
about.

### Order matters: the browser reads top to bottom
A `<script>` can only find elements that already exist when it runs. Placed above `<body>`, a script
calling `document.getElementById("out")` gets `null`, and setting a property on `null` throws — the
script dies silently and the page simply looks unchanged. **Put scripts just before `</body>`**, after
everything they touch.

### HTML has no syntax errors — the browser repairs instead
Given `<p>` written *inside* `<table>` (only rows may live there), the browser did not complain. It
**moved the paragraph out** into `<body>`, and **invented a `<tbody>`** wrapper around the rows that
was never typed. Verified by inspecting the live tree: the paragraph's parent came back as `BODY`,
not `TABLE`.

This forgiveness is why the early web survived, and it is a double-edged gift: **a page can look
correct while the source is wrong**, and the discrepancy surfaces later when JavaScript goes looking
for a structure shaped differently from how it was written. Corollary: what is written is not
necessarily what exists — inspect the live tree, do not trust the source file.

### The console is where JavaScript reports failure
**F12 → Console.** Errors appear there and nowhere else; without it, a dead script is
indistinguishable from a page that simply did nothing. Keep it open while working.

## Working setup (and a gotcha that cost time)

Code in one VS Code pane, the live page in VS Code's **internal browser** in the pane beside it.
Save, then **refresh** — the page does not reload itself.

**Gotcha (hit 2026-08-14):** VS Code's internal browser **rejects `file://` URLs** with
`Forbidden. File does not reside within a trusted folder.` Nothing is wrong with the file. Serve the
repo over HTTP instead and use:

```
http://localhost:8123/tools/xsheet/index.html
```

Worth adopting as the habit regardless of this bug: later, when the tool reads and writes files,
browsers restrict `file://` pages from doing so, while pages served from `localhost` are treated as
a proper origin and are not restricted.

## Decisions on record

- **Lives in `2D-animation-tutorial`, not its own repo** (2026-08-14). It serves this course, its
  output belongs beside `progress/track-1/`, and one HTML file in one folder is cheap to move later.
  Compare `tablet-tool`, which earned its own repo by being a system utility unrelated to any course.
  **Split when there is evidence it is needed** — non-animation use, or the web course outgrowing
  this README — not on speculation.
- **When the web course does get a repo**, the user's workflow is: create it blank on GitHub first,
  clone it down, then work. Not `git init` locally and push.
- **The larger goal beyond this tool:** the user wants to own `nima-cmd-work` — an existing Work Hub
  page that aggregates the ledgers across all his repos, which he did not write and cannot yet
  modify. That is Project 2, deliberately *after* this one: it involves JSON, cross-repo fetching
  and a build script, and would be a punishing first project. Note also that its `repos.json` is
  **stale** — it points this repo at `ledger.html`, deleted in commit `3618b6a`, now
  `ledger/index.html` with a `LEDGER` block.
