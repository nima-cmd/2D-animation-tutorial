# T4-02 — Shortcuts & Two-Handed Flow

**Tool:** Krita + (eventually) OpenToonz
**Goal:** Build the two-handed workflow every digital artist ends up with: pen hand draws and *never leaves the canvas*, keyboard hand lives on a small cluster of shortcuts. Getting this right roughly doubles working speed — not by drawing faster, but by deleting the constant pen-to-menu round trips.

Prerequisite: T4-01 (grip is stable, the pen's side button is either usefully bound or deliberately neutralized).

## The principle

You only need a *tiny* number of shortcuts — the ones you hit hundreds of times per session. Everything else can stay in menus. Trying to memorize twenty bindings at once fails; adding one or two per week sticks. Here's the priority order, by actual frequency in animation work:

## Tier 1 — learn these first (this week)

Keyboard hand rests near these; all Krita defaults:

| Action | Krita default | Why it's tier 1 |
|---|---|---|
| Undo | `Ctrl+Z` | The most-pressed key in digital art, no contest |
| Brush size down / up | `[` / `]` | Constant resizing beats opening any slider |
| Eraser toggle | `E` | Faster than any button once it's reflex |
| Color picker (hold) | `Ctrl` (hold + click) | Sample colors mid-stroke without switching tools |
| Pan canvas (hold) | `Space` (hold + drag) | You should be repositioning the canvas constantly |
| Zoom | `+` / `-` (or `Ctrl+Space` drag) | Work zoomed out for gesture, in for detail |

**Drill:** one full T2 drawing session where your pen hand does not touch the keyboard and every action above comes from the left hand. It'll feel clumsy for ~20 minutes, then permanently better.

## Tier 2 — animation-specific (add when Track 3 starts)

| Action | Krita default | Notes |
|---|---|---|
| Play/pause | `Space`* | *In the timeline context; check `Settings → Configure Krita → Keyboard Shortcuts` |
| Next / previous frame | `.` / `,` | Stepping frames one at a time is half of animation work |
| Add blank frame | (bind it) | Unbound by default — worth assigning, e.g. `Ctrl+.` |
| Add duplicate frame | (bind it) | Ditto |
| Toggle onion skin | (bind it) | You'll flip it constantly while in-betweening |

The unbound ones: `Settings → Configure Krita → Keyboard Shortcuts`, search "frame". Choose keys near your left hand's resting cluster and **write your choices in the ledger's quick reference** so future sessions (and OpenToonz setup later) can mirror them.

## Rotating and mirroring the canvas — the sleeper feature

Two shortcuts most beginners never find, both huge:
- **Canvas rotation** (`4` / `6` to rotate, `5` to reset): traditional animators constantly rotated their paper on the peg disc to put each stroke at a comfortable wrist angle. Digital rotation is the same trick — if a curve keeps coming out wrong, rotate the canvas until it's a *natural* stroke direction instead of fighting your wrist.
- **Mirror view** (`M`): flips the canvas horizontally without touching the artwork. Errors in proportion/tilt that your eye has adapted to become instantly obvious mirrored. Animators flip constantly; it's the digital version of holding a drawing up to a light from the back.

Both go in your left hand's vocabulary once Tier 1 is comfortable.

## The pen's own controls

- **Pressure = size and/or opacity** per brush preset. Now that you're using pressure deliberately (T2-02's line-weight work), audit your two main brushes: sketching brush → pressure controls *opacity* (light construction lines when light-handed); inking brush → pressure controls *size* (line weight from T2-02).
- **The side button, revisited**: with T4-01's fix in place, the highest-value binding for it is **pan** (matching `Space`) or **color pick** (matching `Ctrl`) — an action you need *mid-stroke-flow* where even the left hand is a detour. If it's still misfiring despite the grip drills, keeping it unbound remains a legitimate choice — plenty of professionals disable it and lose nothing.
- **Tablet express keys**: still gated by the driver-dialog bug documented in T4-01 / the ledger quick-reference. If a workaround lands, mirror Tier 1 onto them (Undo and brush-size on physical keys are the classic assignments — see the proposed mapping already written up in the Henwick project's ledger). Until then, the keyboard cluster does the same job.

## OpenToonz note (for later, at the T1-03 gate)

OpenToonz has its own shortcut editor (`File → Configure Shortcuts`). When you get there, spend ten minutes mirroring your Krita bindings (frame step, play, onion skin) so your left hand doesn't have to relearn. This lesson's ledger notes are the checklist for that.

## What "done" looks like

Tier 1 is reflex (you notice when it *breaks* rather than when it works), you've bound the animation frame-stepping keys, and you've used canvas rotation + mirror at least once each on real work. Express keys remain optional/blocked — that's fine.

## Check-in

Report which bindings stuck, which you overrode, and your left hand's resting cluster — these get written into the ledger quick-reference as this machine's canonical setup.
