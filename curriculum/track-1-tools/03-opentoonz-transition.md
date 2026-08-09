# T1-03 — Transition to OpenToonz

**Tool:** OpenToonz
**Goal:** Get comfortable in OpenToonz's very different interface, by re-doing something you already know how to do (the bouncing prop from [T3-02](../track-3-animation/02-bouncing-prop.md)) instead of learning new software and new animation concepts at the same time.

**Gate:** start this after Track 3's parallax lesson (T3-05) — you want timing, spacing, squash/stretch, and arcs already comfortable before adding a new interface on top.

Fun fact worth knowing here: OpenToonz is the open-sourced descendant of Toonz, which Studio Ghibli used internally for years (as a customized "Toonz Ghibli Edition") for digital ink-and-paint and compositing. You're moving to genuinely Ghibli-adjacent tooling.

## Why the switch, and why now

Krita is drawing-software-that-can-animate. OpenToonz is animation-software-first, built around the **Xsheet** (exposure sheet) — a spreadsheet-like grid that's much closer to how traditional animation studios actually track timing across many drawings and levels. It's less immediately friendly, which is exactly why we waited until core animation concepts (timing, spacing, squash/stretch, arcs) were already comfortable — now you're just learning a new interface for concepts you already understand, not both at once.

## Install & orient

1. Install OpenToonz: [opentoonz.github.io](https://opentoonz.github.io/e/) (or via your OS package manager if available).
2. Create a new **Scene**, and find:
   - The **Xsheet** (usually left side) — each column is a "level" (a drawing/character), each row is a frame.
   - The **Viewer** (main canvas).
   - The **Level Strip** — shows all drawings in the currently selected level.
   - Toggle **Onion Skin** in the viewer toolbar.
3. Set project frame rate to 12fps to match what you've been doing (Xsheet menu → Scene Settings).

## The exercise: re-do the bouncing prop

Re-animate your T3-02 bouncing prop from scratch in OpenToonz (don't import the Krita file — the point is learning the new workflow, not the drawing itself):

1. Create a new **Vector level** (Toonz Vector, `.pli`) and use the **Geometric** or **Brush** tool to draw your prop.
2. Draw your key poses directly into the Level Strip as separate drawings (each new drawing = new frame in that level).
3. Use the **Xsheet** to place those drawings on specific frame numbers and to hold/repeat frames (this replaces "duplicating frames" the way you did in Krita's timeline — in OpenToonz you type a drawing number into a cell and it holds there).
4. Reproduce the same spacing/timing choices you already validated in T3-02. While you're in here, also spend ten minutes in `File → Configure Shortcuts` mirroring your Krita bindings from [T4-02](../track-4-pen-tablet/02-shortcuts-and-flow.md) (frame step, play, onion skin) so your left hand doesn't relearn.

Because you already solved the *animation* problem once, this pass is really about: does the drawing feel comparable in a vector-based tool vs. Krita's raster brushes? Vector lines in OpenToonz are editable after the fact (you can nudge points) in a way raster strokes aren't — worth deliberately trying "adjust a line after drawing it" at least once here.

## Rendering out (different from Krita)

OpenToonz's export flow is genuinely one of the least discoverable parts of the tool, so budget some patience here: set your output format and frame range under **Xsheet → Output Settings**, then render via **File → Render Output** (or the render icon in the toolbar). Unlike Krita, there's no one-click "Render Animation to gif" — for a gif or shareable video you may need to render an image sequence or a video file and then convert it with an external tool (a simple video editor, or `ffmpeg`). Do this render test now on your bouncing prop, before the capstone, so it doesn't stall on export mechanics.

## Check-in

This one's worth a check-in specifically on friction points — OpenToonz has a real learning curve and a reputation for being less polished than commercial tools, so if something feels broken or confusing, it's worth asking rather than assuming it's user error. Bring specific stuck points (screenshots help a lot here).

Check this off, then return to Track 3 for the capstone: [T3-06](../track-3-animation/06-capstone-short.md). This completes Track 1.
