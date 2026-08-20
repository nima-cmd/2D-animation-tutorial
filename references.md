# References & Sources

What each track draws from, adapts, or points to. Nothing here is paywalled unless noted.

## Track 2 — Drawing

- **[Drawabox](https://drawabox.com/)** — free, structured beginner drawing course built entirely around lines, ellipses, and boxes. This is the single best free resource for "my drawing skills are crude" — it's designed for people with zero prior training and is deliberately boring/mechanical in a way that builds real control fast. T2-01's drills come straight from Drawabox Lesson 1; T2-02's form work parallels its Lesson 2.
- **Loomis method** (Andrew Loomis, *Fun With A Pencil* / *Figure Drawing for All It's Worth*) — classic construction approach for heads and figures using simple forms (spheres, boxes). Public-domain-adjacent and widely mirrored online. The backbone of T2-03.
- **Preston Blair, *Animation*** (a.k.a. *Cartoon Animation*) — the classic how-to-draw-for-animation book: line of action, construction for motion, walk cycles. Long the standard first book handed to trainee animators; widely available. T2-04 (and Track 3's structure) lean on it.
- **Gesture drawing tradition** — the 30-second-pose practice T2-04 uses is standard art-school/animation training; Proko's free gesture-drawing videos on YouTube are the best modern free treatment if you want a deeper guide. Ghibli/Frieren paused frames work fine as pose sources for our purposes.
- **David Revoy** ([davidrevoy.com/tag/tuto](https://www.davidrevoy.com/tag/tuto)) — creator of *Pepper&Carrot*, an open-source (CC-BY), anime-influenced comic made entirely in Krita. His tutorials are the best real-world example of Krita being pushed to a genuinely anime-adjacent illustration style, and his brush kits are free.

## Track 3 — Animation fundamentals

- **The 12 Principles of Animation** (Frank Thomas & Ollie Johnston, *The Illusion of Life*, Disney) — the foundational theory, codified by two of Disney's "Nine Old Men," the legendary animators who defined the craft's training tradition. T3-01 condenses these to the handful you need first; the rest surface one at a time through the exercises (anticipation and follow-through arrive in T3-03).
- **Richard Williams, *The Animator's Survival Kit*** — the industry-standard beginner textbook. The canonical exercise ladder — **bouncing ball → flour sack → walk cycle** — is exactly Track 3's spine (T3-02, T3-03, T3-04). We keep the timing/spacing structure Williams teaches, just reskin the subjects to be Ghibli/Frieren-flavored (soot sprites, mana orbs) instead of a plain ball and sack.
- **The flour sack** specifically is a Disney training-program classic — the simplest possible "character" (weight + attitude, no anatomy) and the traditional bridge from physics exercises to character animation.
- Free video treatments: search "bouncing ball animation principles", "flour sack animation exercise", and "12 frame walk cycle tutorial" — AlanBecker, Bloop Animation, AnimatorIsland, and various animation-school channels have solid free walkthroughs of all three.

### Timing & spacing — primary sources (checked 2026-08-11)

Gathered when the question came up of *why* a particular set of keyframes is correct, rather than
taking an instructor's numbers on trust. Each is marked with what it actually establishes.

- **Richard Williams, *The Animator's Survival Kit*** — the source for the timing/spacing
  distinction itself. Williams' worked example: a coin moved across a page in one second (24
  frames); **timing** is the one second, **spacing** is how the drawings are distributed across it.
  Identical timing with different spacing — easing out of one pose and into the next — produces
  visibly different movement though both start and finish together. Also the source of the
  **spacing chart** method (place the middle inbetween first, then halve each side). A
  [full text is readable on archive.org](https://archive.org/stream/TheAnimatorsSurvivalKitRichardWilliams/The%20Animator's%20Survival%20Kit%20-%20Richard%20Williams_djvu.txt),
  though this is the one book in the field worth owning on paper — the flipbook margins don't
  survive digitisation.
- **VanderWerf, Brassinga, Reits, Aramideh & Ongerboer de Visser (2003), "Eyelid movements:
  behavioral studies of blinking in humans under different stimulus conditions," *J Neurophysiol*
  89(5):2784–2796** — [PubMed](https://pubmed.ncbi.nlm.nih.gov/12612018/) ·
  [free PDF](http://wexler.free.fr/library/files/vanderwerf%20(2003)%20behavioral%20studies%20of%20blinking%20in%20humans%20under%20different%20conditions.pdf).
  Measured with a magnetic search coil on the lid plus EMG of the orbicularis oculi. **Spontaneous
  blink: total 334 ± 67 ms; closing (down) phase 92 ± 17 ms; opening (up) phase 242 ± 55 ms** — the
  reopening is nearly *three* times the close, not twice. This is the measurement the T1-02 blink
  re-time is derived from; it corrected an instructor claim of a 1:2 ratio down to 1:2.6, which
  moved the keyframes from 0/2/3/5/8 to **0/1/2/4/8**. Use it as the worked example of deriving
  frame counts from a real measurement rather than from feel.
- **Miyazaki on *ma*** — Roger Ebert, ["Drawing on 'Spirited' world"](https://www.rogerebert.com/interviews/drawing-on-spirited-world)
  (Toronto, 2002). Ebert praised the "gratuitous motion" in the films — characters sitting, sighing,
  gazing at a stream, doing something *extra* that doesn't advance the plot. Miyazaki: *"We have a
  word for that in Japanese. It's called 'ma.' Emptiness. It's there intentionally."* He clapped
  three or four times: *"The time in between my clapping is 'ma.' If you just have non-stop action
  with no breathing space at all, it's just busyness."* And: *"The people who make the movies are
  scared of silence."* Primary-source confirmation that Ghibli's pacing is a deliberate doctrine.
- **"On twos" / limited animation** — widely documented: on twos = 12 drawings/second (each drawing
  held 2 frames of 24); on threes = 8 drawings/second. Anime characteristically works at 8–12
  drawings/second and *modulates* the rate within a scene rather than holding one cadence. Good
  free treatments: [Wave Motion Cannon, "An Introduction to Framerate Modulation"](https://wavemotioncannon.com/2016/12/31/an-introduction-to-framerate-modulation/)
  and [Animétudes, "Animation and subjectivity: towards a theory of framerate modulation"](https://animetudes.com/2020/05/17/animation-and-subjectivity-towards-a-theory-of-framerate-modulation/) —
  both treat cadence as an expressive choice, which is exactly the Grimoire's Chapter III argument.

### Saccades and blink-saccade coupling (checked 2026-08-20)

Looked up because the nervous-blink exercise rests on both: gaze aversion is the behaviour being
animated, and the frame counts depend on how fast a dart actually is.

- **Saccade duration and speed** — saccades last **20–200 ms**, typically **30–100 ms**, with the
  *smallest* movements the fastest (~20 ms); peak angular speed reaches **1000°/s**, making the
  saccade **the fastest movement of any external part of the human body**.
  [Scholarpedia, "Human saccadic eye movements"](http://www.scholarpedia.org/article/Human_saccadic_eye_movements)
  · [ScienceDirect overview](https://www.sciencedirect.com/topics/neuroscience/saccade).
  **Consequence for animation:** at 24fps one frame is 41.67 ms, so a small dart is *shorter than a
  single frame*. A saccade cannot be animated as movement — **it is a cut**, no in-betweens exist and
  drawing them would be wrong. Only the end positions are needed. Because nothing intermediate helps
  the eye track it, the positional change must be large enough to read instantly.
- **Blinks are a component of gaze shifts, not separate from them** — lid-closing muscle activity
  accompanies **97% of gaze shifts larger than 33°**; blink probability rises with gaze amplitude
  (~20% for large shifts in humans); and the blink **begins simultaneously with the eye movement**
  rather than preceding it. Saccades accompanied by blinks are measurably slower.
  [Exp Brain Res, "Not looking while leaping"](https://link.springer.com/article/10.1007/BF00227203)
  · [Gaze-evoked blinks and gaze shifts](https://pmc.ncbi.nlm.nih.gov/articles/PMC3262917/)
  · [Properties of horizontal saccades accompanied by blinks](https://journals.physiology.org/doi/full/10.1152/jn.1998.79.6.2895).
  **Consequence:** put the blink *on* the dart, not before it, and reserve blinks for the larger
  direction changes.
- **Not sourced — Claude's inference**, flagged as such: since the saccade is sub-frame and therefore
  a cut, a blink on the same frame would *mask* that cut. Worth testing against a version without it.
- **Not checked:** typical *fixation* durations. Deliberately left unverified so the user derives
  fixation lengths from observation rather than from a handed number.

### The moving hold (checked 2026-08-15)

Looked up after the user diagnosed the effect unprompted — *"once we hit 24 all tension kind of
stops, cause we just hold on the one image"* — to find out whether the tradition names it. It does.

- **The moving hold**, developed by Frank Thomas and Ollie Johnston alongside the twelve principles.
  A character held perfectly still from the instant the main pose is reached **reads as dead**; the
  remedy is a pose held *without being static* — small, controlled secondary movement rather than a
  total freeze. Even a character doing nothing breathes or shifts slightly.
  Overviews: [Arlington Museum of Art on Thomas & Johnston](https://arlingtonmuseum.org/explore-more/the-twelve-principles-of-animation)
  · [Pluralsight, "Understanding the 12 Principles of Animation"](https://www.pluralsight.com/resources/blog/software-development/understanding-12-principles-animation)
  · [Simon Whatley's summary](https://www.simonwhatley.co.uk/writing/disney-12-basic-principles-of-animation/)
- **Not sourced — Claude's formalisation** of what the user found next, and it should be treated as
  one instructor's framing rather than doctrine: *stillness reads as dead only when the pose implies
  effort.* A tense pose held motionless contradicts itself; a released pose held motionless is doing
  what it should. This is why relocating a hold's static stretch — rather than shortening it —
  fixed the shot.

### The exposure sheet / X-sheet / time sheet (checked 2026-08-14)

Looked up after the question "is this actually used, and what does one look like?" — having twice
been asserted as standard practice without checking.

- **[How to Read a Timing Sheet — Animation Art Wiki](https://animationart.wiki/books/faqs/page/how-to-read-a-timing-sheet)**
  — the best starting point: **photographs of real anime time sheets** shown beside the *genga* and
  *douga* they produced. Establishes the notation — rows are frames at 24fps, a heavy rule every 24
  rows marks a second, columns `A`/`B`/`C` are cel layers with A nearest the background, **circled
  numbers are key drawings, dashes are in-betweens, and a vertical line ruled down the column is a
  hold.**
- **[Timesheet — Sakuga Wiki](https://sakuga.fandom.com/wiki/Timesheet)** and
  **[Anime GO — Timesheet](https://animego.erosakuga.com/benkyou/timesheet/)** — the Japanese
  convention (タイムシート): 144 rows to a sheet, i.e. exactly **6 seconds**. Key animators fill the
  action column; in-between staff translate it into the cel columns.
- **[Toon Boom — Exposure Sheet, Timeline and Timing](https://learn.toonboom.com/modules/basic-concepts2/topic/exposure-sheet-timeline-and-timing2)**
  — the modern digital treatment; confirms X-sheets persist in current software rather than being
  historical.
- **[D'source — basic X-sheet template](https://www.dsource.in/course/exposure-sheet/basic-x-sheet-template)**
  — a printable blank, if working on paper appeals.
- **[OpenToonz — Working in Xsheet](https://opentoonz.readthedocs.io/en/latest/working_in_xsheet.html)**
  — the Xsheet is one of OpenToonz's **main rooms**, not a legacy view. The notation learned now is
  literally the interface at the end of Track 1 (T1-03).
- **[Wikipedia — Exposure sheet](https://en.wikipedia.org/wiki/Exposure_sheet)** — general overview,
  column structure (action, dialogue, cel levels, background, camera).

Worth noting *why* this matters beyond trivia: the hold-as-a-ruled-line convention makes it
visually impossible to mistake a hold for a movement — the exact error committed in the drowsy
blink, where lengthening gaps were intended as a heavier droop and instead read as the eye sitting
open longer. A digital timeline hides holds behind empty space; paper made them a line you could
see.

**Not sourced — flagged honestly.** The Grimoire's *"seven dials of timing"* and its feeling→timing
table (nervous / drowsy / excited / sad / confident) are **Claude's own synthesis**, not established
doctrine, and appear under that name in no text. The claim that *"a typical anime blink is 4–6
frames"* was asserted from memory and has **not** been verified. Treat all of these as working
scaffolds to be tested against the exercises, not as citations.

## Ghibli & Frieren specific

- **Ghibli's multiplane/parallax background technique** — Miyazaki films are famous for layered backgrounds with independent camera movement per layer (foreground/midground/sky), inherited from traditional multiplane camera work. T3-05 teaches a simplified digital version in Krita.
- **Toonz → OpenToonz lineage** — Studio Ghibli used a customized version of Toonz (Toonz Ghibli Edition) as their in-house digital ink-and-paint and compositing tool for years. OpenToonz is the open-sourced descendant of that same codebase. The motivation behind Track 1's endpoint (T1-03).
- **"On twos" and anime timing** — hand-drawn animation, including Ghibli's films and TV anime like Frieren, is mostly animated at 12 drawings/second (each drawing held 2 frames at 24fps), with held frames used deliberately for stillness. Covered in T1-02; worth knowing so limited drawing counts read as a stylistic tradition, not a compromise.
- **Frieren's character design** — simple, clean linework, muted natural palettes, understated expressions. Reference frames from the anime (screenshot studies, not tracing for redistribution) are useful throughout Track 2's gesture work and Track 3's character exercises — personal study only.

## Track 4 — Pen & tablet

- No single canonical text — T4-01/T4-02 are built from standard digital-art practice (pencil grip, ghosting from the shoulder, pressure-curve tuning, minimal-shortcut-set habit building). [OpenTabletDriver](https://opentabletdriver.net/) is the open-source vendor-driver replacement referenced as the last-resort fix for the XP-Pen dialog bug documented in the ledger.

## Software docs

- [Krita Manual — Animation](https://docs.krita.org/en/user_manual/animation.html)
- [OpenToonz User Guide](https://opentoonz.readthedocs.io/)
