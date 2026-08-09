# 2D Animation Tutorial

A self-paced, ledger-tracked curriculum for learning 2D animation from scratch — total beginner to computer animation, crude-but-willing drawing skills, big love for Studio Ghibli and *Frieren: Beyond Journey's End*.

**Tools:** [Krita](https://krita.org) (free) to start, moving up to [OpenToonz](https://opentoonz.github.io/e/) (free) once the basics click. Both are open source.

## The four tracks

1. **[Tools & workflow](curriculum/track-1-tools/)** — the universal machinery of digital 2D animation (onion skinning, timelines vs. exposure sheets, holds, layers/cels), ending in the graduation to OpenToonz — the open-sourced descendant of Ghibli's own in-house software.
2. **[Drawing](curriculum/track-2-drawing/)** — line control, then the fix for flat/dead-looking drawings (form, overlap, line weight), construction, and finally drawing *specifically for animation*: gesture, line of action, silhouette, model sheets.
3. **[Animation fundamentals](curriculum/track-3-animation/)** — the classic milestone sequence every animator trains through, from the Disney tradition (the 12 principles, *The Animator's Survival Kit*): bouncing ball → flour sack → walk cycle → a full scene, each reskinned to Ghibli/Frieren subjects.
4. **[Pen & tablet](curriculum/track-4-pen-tablet/)** — a thread running through the whole project rather than a phase: fixing the pen-button misfires, grip correction, pressure curves, shortcuts, and two-handed flow. Grip/strain feedback belongs in every check-in.

The recommended path through the tracks is written at the top of the ledger.

## How this works

- [`ledger.html`](ledger.html) is the single source of truth for progress — open it in a browser (double-click the file, or `python3 -m http.server` from the repo root and visit it). Only the **active** milestones get an interactive panel: checkable steps (autosaves to your browser, no tokens spent) and a "Copy check-in message" button. Past milestones show as done with a written checkpoint/notes; future ones are locked until reached — matching the same pattern used in the `first-game-frieren-rpg` and `jessica-henwick-character-study` projects.
- [`curriculum/`](curriculum/) holds the full written lesson for each milestone, one folder per track. `ledger.html` stays lean and links out to these rather than duplicating them.
- [`references.md`](references.md) lists the real tutorials and resources each lesson adapts or draws from.

## Using Claude as your instructor

Work through lessons in order. When you reach the current milestone's panel in `ledger.html`, tick its steps off yourself as you go — free, no session needed. When you're actually done with the milestone:
1. Click "Copy check-in message" in the ledger and paste it into a Claude Code session here, filled in with what happened (attach exported work, screenshots, or files as needed — saving work under the matching track folder, e.g. `curriculum/track-3-animation/my-bouncing-prop.mp4`, keeps everything findable).
2. Claude reviews it, helps troubleshoot anything stuck, and writes the milestone up as done directly in `ledger.html` — checkpoint, any gotchas worth remembering, and unlocks the next milestone's panel.

No pressure to go fast — the point of the ledger is to make slow, real progress visible, and to keep permanent notes on what actually happened rather than just a checkbox.

## Current status

Open [`ledger.html`](ledger.html) for live status. Start at [`curriculum/track-1-tools/01-setup-krita.md`](curriculum/track-1-tools/01-setup-krita.md).
