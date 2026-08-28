# Krita configuration — backed up, because it lives outside the repo

Krita is a Flatpak here, so its settings live in
`~/.var/app/org.kde.krita/config/` — **outside version control**. Reinstall Krita or move
machines and these are gone with no record of what they were. Hence this copy.

## `kritashortcutsrc` — animation timing shortcuts

Assigned 2026-08-27. Krita ships with **none** of these bound; the file did not exist at all
until they were set, which is how we knew nothing had ever been customised.

| Shortcut | Action | What it does |
|---|---|---|
| `Alt` + `←` `→` | previous / next **keyframe** | hop drawing to drawing |
| `Ctrl`+`Alt` + `←` `→` | previous / next **frame** | step one frame at a time |
| `Ctrl` + `←` `→` | remove / insert **hold frame** | shorten / lengthen the current drawing's exposure |

**The scheme is deliberate:** modifier tiers mean something consistent — `Alt` coarse, `Ctrl+Alt`
fine, `Ctrl` edits — and left is always backward-or-less, right always forward-or-more. Arbitrary
assignments get forgotten; patterned ones don't.

### Why the hold-frame pair matters most

**Dragging a keyframe couples two durations**: the gap before it shrinks while the gap after grows.
Total length is unchanged, and you must work left-to-right or keyframes land on each other. Every
re-time before this date was done that way.

**Insert / remove hold frame changes one duration** and ripples everything downstream. It is a
*direct duration dial* — the operation actually wanted when adjusting timing, rather than a
side-effect of moving something.

**Gotcha:** `Insert Hold Frame` pushes the keyframes *after* the playhead. Standing past the last
keyframe there is nothing to push, so it appears to do nothing. Not a broken binding — an empty
downstream.

## Restoring

```
cp kritashortcutsrc ~/.var/app/org.kde.krita/config/kritashortcutsrc
```

With Krita closed — it rewrites the file on exit.

## Hardware note

These shortcuts are also the target for the **Razer Stream Controller** (running under LoupixDeck).
Its command list includes a **Shell** action, so `xdotool key ctrl+Right` works; it also has a
**User Macros** system which may send keystrokes natively. Each rotary has three slots — rotate
left, rotate right, press — so one knob covers a full lengthen/shorten/duplicate set. Not yet
bound; see `SYLLABUS.md` in `nima-cmd-work` for the wider plan.
