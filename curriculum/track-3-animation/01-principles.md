# T3-01 — Animation Principles Primer

**Tool:** Krita
**Goal:** Learn the small handful of the 12 Principles of Animation that actually matter for your first exercises, before you need them. Reading about squash & stretch *before* you draw a bouncing ball is much more useful than discovering it by accident.

Full background in [references.md](../../references.md) — the 12 Principles come from Frank Thomas and Ollie Johnston's *The Illusion of Life*, two of Disney's "Nine Old Men," the legendary animators who codified the craft. Track 3 exists to walk you through the same milestone exercises their tradition (and Richard Williams' *The Animator's Survival Kit* after them) has used to train every generation of animators since. Here's the condensed version, tool-agnostic:

## The principles you need right now

- **Timing** — how many frames (i.e. how much time) an action takes. Fewer frames between two poses = faster/snappier action. More frames = slower, heavier, or more graceful. At 12fps, 1 frame ≈ 83ms.
- **Spacing** — how far apart, in *position*, drawings are, even if the time between them (in frames) is constant. Objects speeding up have spacing that gets wider frame to frame; objects slowing down have spacing that gets narrower. This is the #1 thing that separates "mechanical, robotic" motion from motion that feels alive.
- **Squash & stretch** — a shape deforms along its motion to sell weight, flexibility, and impact, while (usually) preserving its volume — squash it flat, and it should look "wider" to compensate. A rigid object (a rock) barely squashes; a soft one (a soot sprite, a beanbag) squashes a lot.
- **Arcs** — almost nothing organic moves in a straight line. Limbs, falling objects, heads turning — nearly everything travels a curved path. Straight-line motion is one of the fastest tells of stiff, amateur animation.
- **Ease in / ease out (slow in / slow out)** — motion rarely starts or stops instantly; it accelerates out of a held pose and decelerates into the next one. This is really just "spacing" applied at the start/end of an action.
- **Anticipation** — a small counter-motion before the main action (crouching slightly before a jump) that telegraphs what's about to happen and makes the main action read more clearly.

## Deriving timing instead of guessing it

A number you can't re-derive is worthless. The chain, runnable on any action:

1. **What does the real thing take, in milliseconds?** Observe it, film yourself, or find a study.
2. **Divide by the frame duration** — at 24fps, one frame is **41.67 ms** — to get a frame count.
3. **Find the asymmetry.** Nearly every action has a fast phase and a slow phase. Split the frame budget by the *measured* ratio, not down the middle.
4. **Within each phase, accelerating or decelerating?** Accelerating → the time gaps *shrink*. Decelerating → the gaps *grow*.
5. **Then stylise** — usually compress for snap. **This is the only step where taste enters.** Steps 1–4 can be objectively wrong; step 5 cannot.

Worked example, the T1-02 blink. VanderWerf et al. (2003) measured the spontaneous blink at **334 ± 67 ms** total, **92 ± 17 ms** closing, **242 ± 55 ms** opening — the reopening is nearly *three* times the close. At 24fps that is 8 frames total, 2 closing, 6 opening, with the reopen's gaps widening (2, then 4):

```
open @0 · half @1 · shut @2 · half @4 · open @8
```

An instructor claim of a 1:2 ratio, made from memory, put this at 0/2/3/5/8 — plausible, and wrong. Only the measurement caught it. **A clean derivation from a half-remembered number feels exactly as convincing as a correct one.** That is the failure mode to watch for.

## The exercise — one blink, three feelings

Take the five drawings you already have and re-time them **three times**, changing nothing but keyframe positions. Save each as its own file:

- `t1-02-blink-drowsy.kra`
- `t1-02-blink-nervous.kra`
- `t1-02-blink-excited.kra`

**Derive first, animate second.** For each feeling, write down *before* you touch the timeline: the total duration you're aiming for and why, where the asymmetry goes, and whether each phase accelerates or decelerates. Then place the keyframes to match. If the result doesn't read, the interesting question is whether the derivation was wrong or the execution was.

The dials available to you: **speed**, **cadence** (ones/twos/threes), **hold length**, **easing** (how bunched the gaps are), and **regularity** (even rhythm vs. irregular).

**A constraint worth meeting head-on:** with five fixed drawings you have only the *time* lever — spacing is baked into the artwork. One of these three will fight you badly for exactly that reason. Working out **which one, and why**, is the real content of this exercise; it's the thing that motivates learning to draw new positions rather than only re-time old ones.

## The falling circle — the bridge to T3-02

Separately, animate a plain circle falling and landing on a flat line in about 8–10 frames, position only. Then duplicate it and add squash on impact, stretch while falling fast, and re-space so the gaps are widest mid-fall and tightest at the bounce. This one is about the **other** lever: timing stays constant while *position* does the work. That is precisely what the bouncing prop demands, so treat it as a warm-up for T3-02 rather than part of the timing drill above.

## Check-in

Show the three re-timed blinks — they get a review, because the derivations are the graded part, not the drawing. The falling circle needs no review unless you want one.

Move to [T3-02 — The Bouncing Prop](02-bouncing-prop.md).
