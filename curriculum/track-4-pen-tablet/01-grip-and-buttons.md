# T4-01 — Grip, Buttons & the Misfire Problem

**Tool:** Krita + your tablet's driver
**Goal:** Get genuinely comfortable holding and controlling the pen before drawing fundamentals — specifically, stop the pen's side button from firing commands you didn't mean to trigger, and get at least a few real shortcuts working so your off-hand isn't constantly diving for the keyboard.

This is Track 4's first milestone, and it sits ahead of all drawing drills on purpose: an unreliable pen is a worse problem than unpracticed lines — a line that's slightly wobbly just needs more mileage, but a stray button-press that undoes your last three strokes or switches tools mid-line is actively sabotaging every drill after this one. Track 4 then runs as a parallel thread through the whole project (grip gets checked during Track 2 check-ins, shortcuts build up in [T4-02](02-shortcuts-and-flow.md)) rather than ending here.

One standing Track 4 rule for every check-in from now on: **if you notice hand/wrist strain, or a drill feels physically awkward, say so in the check-in** — grip and posture corrections are much easier to give against a specific reported symptom, and photos of how you hold the pen are genuinely useful for this.

## Your specific situation (confirmed on this machine)

You're on an **XP-Pen Deco Pro MW**, and this same tablet already caused a documented, real problem in the Jessica Henwick character-study project: the XP-Pen driver's **Shortcut Keys assignment dialog visibly clips** under this system's desktop (COSMIC, running the driver's window through XWayland) — the title, the key-capture panel, and the Save/OK button all get cut off no matter how the window is moved or how display scaling is adjusted. That project tabled the issue as an unresolved driver/compositor bug, not a "you're doing it wrong" problem. It's worth ruling out this same wall here before assuming the fix is something you're missing.

Also confirmed on this machine: `xsetwacom` (the classic Linux tablet CLI) is installed but is flatly incompatible with a Wayland session — it can't be used as a workaround here either. So the fix has to come from one of the paths below, not a quick command-line remap.

## Step 1 — Diagnose the actual button (before touching any settings)

Before assuming it's a "shortcut setup" problem, confirm what's actually firing:

1. Open Krita, open a blank canvas, and do slow, deliberate strokes while *deliberately* trying to trigger the accidental press (grip the pen the way you normally do). Watch Krita's status bar / undo history / active tool indicator as you draw.
2. Note exactly what happens when it fires — does it undo? Switch tools? Open a menu? Toggle eraser? This tells you whether it's the barrel/side button (most common culprit — sits right where a thumb rests during a natural grip) or something else (e.g. an express key on the tablet body getting bumped, not the pen itself).
3. Note *when* it fires — constant grip pressure, or only during fast strokes / repositioning? This distinguishes "bad grip" (fixable with technique, see Step 3) from "button is just too easy to press" (fixable with remapping or physically avoiding it, see Step 2).

## Step 2 — Try to actually fix the shortcut/remap setup

Try these in order, stopping as soon as one works — don't feel obligated to attempt all of them:

1. **Try the driver's Shortcut Keys dialog again anyway.** Software gets updated; it's possible this has been patched since it was last tried. If it still clips, don't fight it further — move to option 2.
2. **Set the pen button's action inside Krita itself, not the OS driver.** Krita has its own input configuration (`Settings → Configure Krita → Canvas Input Settings`), which can bind actions directly to a "stylus button" input, independent of the XP-Pen driver entirely. This sidesteps the broken dialog completely for anything you do inside Krita — which, for this curriculum, is most of what matters. Good first assignment to try: bind the button to **Eraser toggle** or **Undo**, whichever matches what Step 1 revealed it's already closest to doing by accident (if it's already acting like an eraser toggle, keep it as one deliberately rather than fighting it).
3. **Try resizing the clipped dialog via the window manager, not the app.** Some tiling/compositing window managers let you force-resize or force-move a window with a keyboard shortcut even if its own UI is unusable (COSMIC's window management shortcuts, or a generic "interactive move/resize" binding). If you can drag the clipped edge into view this way, the underlying dialog logic likely still works fine — it's just been visually cut off.
4. **Consider OpenTabletDriver as a replacement driver**, if the above don't pan out. It's an actively-maintained, open-source, Linux-first alternative to vendor tablet drivers, with its own (non-Qt5) configuration UI that's unlikely to share this exact clipping bug. This is a bigger step (replacing your tablet driver, not just a setting), so treat it as a "last resort, and only outside of a session where you need the tablet working reliably" option — don't attempt it right before you need to get drawing done.

Whichever of these works, note it down for the ledger check-in — the Henwick project will want the same fix once it's found.

## Step 3 — Grip and technique drills (do these regardless of Step 2's outcome)

Even with perfect shortcuts, an unstable grip will keep bumping buttons by accident. A few minutes of deliberate practice fixes this permanently:

1. **Grip check**: hold the pen like a pencil, resting on the web between thumb and index finger, with your ring/pinky fingers grounded on the tablet surface for stability — not gripped tightly in a fist. A tight fist grip is the single most common cause of accidental barrel-button presses, since it presses your thumb straight into the button under normal drawing pressure.
2. **Hover drill**: move the pen tip just above the tablet surface (hovering, cursor moving, nothing drawn) for a full minute, getting used to the hover-vs-contact distinction — most accidental clicks happen while repositioning without meaning to touch down at all.
3. **Lift-cleanly drill**: draw a short line, then lift the pen fully off the surface (not just stop moving) before starting the next one. Dragging the pen tip between strokes while still in light contact is a common source of stray marks and accidental drags.
4. **Pressure curve check**: in Krita's tablet settings (`Settings → Configure Krita → Tablet Settings`), look at the pressure curve — if full black requires pressing much harder than feels natural, or a light touch is already near-black, adjust the curve rather than fighting your own grip to compensate.

## What "done" looks like

Not necessarily a fully-solved shortcut situation (Step 2 might genuinely stay blocked, same as the Henwick project) — but you should be able to answer: what specifically causes the accidental press, and do you have at least one working button/shortcut assignment (even just one, e.g. eraser toggle via Krita's own input settings). Perfect express-key mapping across the whole tablet is a nice-to-have, not a requirement to move on.

## Check-in

Describe what Step 1 revealed (what the button was actually doing, and when), which Step 2 option worked (if any), and how the Step 3 drills felt. This is a good one to loop back to later if a driver update or a different fix surfaces — it doesn't need to be perfect before moving on to drawing fundamentals.

Check this off, then continue with Track 1 ([T1-02](../track-1-tools/02-animation-tool-concepts.md)) or jump into drawing (Track 2's [T2-01](../track-2-drawing/01-line-control.md)). [T4-02 — Shortcuts & Flow](02-shortcuts-and-flow.md) picks up once you're drawing regularly.
