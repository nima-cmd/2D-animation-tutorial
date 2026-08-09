# T3-05 — Parallax Background & Camera Pan

**Tool:** Krita
**Goal:** Learn the layered-background parallax technique that's a hallmark of Ghibli's visual style — simplified for a first attempt.

Ghibli films are known for atmospheric, deep backgrounds where foreground, midground, and sky move at different rates as the "camera" pans — a digital analogue of traditional multiplane camera work. This lesson teaches a simple version of that, independent of character animation.

A note on what "camera" means here: Krita doesn't have a real camera object, so we fake the effect by moving the *layers themselves* in the opposite direction. That's a legitimate, standard way to fake parallax digitally — but know it's a fake; OpenToonz (Track 1's T1-03 onward) has an actual camera/column system, which is the "real" version of this technique.

## Steps

1. **Design a simple 3-layer scene**: pick something evocative but simple — a hillside with a tree in front, rolling fields behind it, and a sky/clouds furthest back. (Think of any wide Ghibli establishing shot — you don't need anywhere near that detail, just the same *layer logic*.) **Flat colored shapes or silhouettes are completely fine here** — this exercise is grading the *motion/depth illusion*, not the painting. Don't let background-painting skill (which nothing so far has taught you) become the bottleneck; a simple silhouetted hill and a plain gradient sky will demonstrate parallax just as well as a detailed painting.
2. **Paint each layer separately** on its own Krita layer, each layer wider than your canvas (e.g. canvas is 1280px wide, each background layer is painted at ~2000px wide) so there's room to pan across it.
3. **Set up the pan**: on the timeline, keyframe each layer's horizontal position moving left (or right) over time — but move the foreground layer *faster* than the midground, and the midground *faster* than the sky. This speed difference is the entire trick behind parallax; it's what creates the illusion of depth from flat 2D layers.
4. **Render a 3-4 second pan** with no characters yet — just the background moving. This is the asset you'll drop your T3-04 walk cycle in front of, in the capstone.

## Rough starting ratios (adjust by eye)

If your foreground moves 100px over the shot, midground might move ~40px, and sky ~10px, in the same amount of time. The exact numbers matter less than "each layer is clearly moving at a different rate than its neighbors" — if it's subtle enough to not be sure it's working, push the difference further.

## Check-in

Render the pan and take a look yourself first — does it read as "depth" or does it look like flat layers sliding independently? If the latter, the fix is almost always to widen the speed gap between layers, not to add more detail. Bring it back if you want a second opinion or run into Krita layer-transform quirks (moving a layer without a mask affecting the wrong region is the most common snag).

Check this off, then take the Track 1 detour: [T1-03 — Transition to OpenToonz](../track-1-tools/03-opentoonz-transition.md). Return here for [T3-06 — the capstone](06-capstone-short.md) after.
