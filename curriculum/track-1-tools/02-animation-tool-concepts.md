# T1-02 — The Universal Tools of Digital 2D Animation

**Tool:** Krita (but the concepts are the point, not the buttons)
**Goal:** Learn the tools and concepts that exist in *every* serious 2D animation program — Krita, OpenToonz, Toon Boom, Clip Studio, TVPaint — so that when you graduate to OpenToonz, you're relearning button locations, not ideas. Everything here was used at Ghibli in some form, most of it decades before computers.

Work through each concept in Krita as you read it — this is a guided tour, not a reading assignment.

## The core toolkit, app by app it's the same

### 1. Onion skinning
The digital version of a lightbox shining through stacked paper. Shows ghosted tints of the previous/next frames under your current one so you can judge spacing and keep drawings consistent. Every app has it; every app lets you adjust how many frames deep and how strong the tint. **In Krita:** the Onion Skins docker + the per-layer light-bulb toggle. **Try it:** draw a dot on three consecutive frames, watch the ghosts.

### 2. The timeline vs. the exposure sheet (Xsheet)
Two interfaces for the same underlying idea — *which drawing shows on which frame*:
- **Timeline** (Krita, most modern apps): horizontal strip, one row per layer, frames as columns. Intuitive, video-editor-like.
- **Exposure sheet / Xsheet** (OpenToonz, Toon Boom): vertical spreadsheet, one *column* per level, frames as rows. This is a direct digitization of the paper exposure sheets studios like Ghibli filled out by hand — the animator wrote which numbered drawing gets photographed on which frame. It looks intimidating and is actually simpler: it's just a table.

The key shared idea: **a drawing and a frame are different things.** One drawing can be *held* (exposed) for multiple frames. Animating "on twos" — each drawing held for 2 frames, i.e. 12 drawings per second at 24fps — is the standard look of hand-drawn animation, including nearly everything Ghibli has made. Constant "on ones" (24 drawings/sec) is reserved for fast action. Frieren, like most TV anime, is mostly on twos and threes with held frames for stillness — that *restraint* is a stylistic tool, not a shortcut.

### 3. Layers
Same as in any paint program, but in animation they map to production roles: character on one layer, background on another, effects (glow, rain) on a third. This is the digital descendant of painting on stacked transparent **cels** over a single background painting — the reason old anime backgrounds are lush paintings while characters are flat colors is that they literally lived on different physical layers. **Try it:** put a quick background scribble on one layer and animate a dot on a layer above it — notice you only redraw the dot, never the background.

### 4. Keys, breakdowns, and in-betweens
Not a software feature — a workflow the software supports. **Key poses** define the important moments of an action; **breakdowns** define how you get between keys (the arc, the favoring); **in-betweens** fill the remaining frames. At a studio these were different people's jobs (key animator vs. in-betweener — in anime production, *genga* vs. *dōga*). Digitally, you'll be all of them, and the discipline of drawing keys FIRST, then filling in, is what Track 3 drills. The software concept to know: most apps mark/color keys differently in the timeline so you can navigate between them.

### 5. Frame rate and playback
12fps vs 24fps vs "24fps on twos" (same result, different bookkeeping). Real-time playback with looping is your most important quality check — you'll play a 1-second loop fifty times while adjusting. Learn the shortcut for play/pause before anything else. **In Krita:** also note the *cache* — first playback may stutter while frames render, second loop plays true.

### 6. Brush stabilizers / smoothing
Digital-only, and a genuine gift for a beginner: the app averages your stroke to smooth out hand wobble. **In Krita:** the Tool Options for the freehand brush → Stabilizer. Use a light setting (too strong feels like drawing through syrup and kills the confident-stroke habit Track 2 is building — it's a seatbelt, not a chauffeur).

### 7. Color fill workflow ("ink and paint")
Line art on one layer, flat color filled underneath on another — the digital version of the ink-and-paint department, which is exactly what Toonz was originally built to do at Ghibli. Krita's fill tool + "use other layer as reference" setting is the miniature version. Just know it exists; you'll use it properly in the capstone.

### 8. Export / render
Animation isn't done until it's a video file someone can watch. Every app has a render step (Krita: `File → Render Animation`; OpenToonz: Output Settings → Render). Covered per-app in its own lesson — the shared concept is just: *the working file and the watchable file are different artifacts.*

## The exercise

Make a 2-3 second "tool sampler" scene — no quality bar at all, this is a scavenger hunt:
1. A background layer (scribbled hill, Ghibli spirit optional).
2. An animated layer on top: a soot sprite (blob + eyes) that blinks — hold the open-eye drawing for ~10 frames, closed for 2, open again. You've just used **exposure/holds** deliberately.
3. Onion skin ON while making the blink frames.
4. One stroke drawn with the stabilizer cranked to maximum and one at zero — feel the difference.
5. Play it back looping, then render it to a file and watch it outside Krita.

## Check-in

Copy the check-in from the ledger — the main thing to report is which concepts feel clear vs. fuzzy. Fuzzy is fine and normal for keys/breakdowns (Track 3 exists to make that one physical); onion skinning and holds should feel concrete before moving on.

Next: Track 2 and Track 3 run from here. Return for [03-opentoonz-transition.md](03-opentoonz-transition.md) when Track 3 reaches the OpenToonz gate.
