# STS2 Regent — OpenPeon Sound Pack

<p align="center">
  <img src="assets/char_select_regent.png" alt="Regent" width="180" />
</p>

<p align="center">
  <i>"Come on, out with it. I haven't got all day."</i><br/>
  An <a href="https://openpeon.com">OpenPeon</a> (CESP v1.0) sound pack of
  Regent voice lines from
  <i>Slay the Spire 2</i> (2026, Mega Crit).
</p>

<p align="center">
  <a href="#installation">Install</a> ·
  <a href="#categories">Categories</a> ·
  <a href="#source">Source</a> ·
  <a href="#copyright--fair-use-notice">License</a>
</p>

---

Every impatient sigh, smug chuckle, triumphant bark, and wounded gasp the
Regent can muster, wired into your Claude Code / Codex / IDE events.

## Installation

```sh
git clone https://github.com/flavono123/sts2-regent-peon.git
peon packs install-local sts2-regent-peon
peon packs use sts2_regent
```

Preview any category:

```sh
peon preview session.start       # "Greetings."
peon preview input.required      # impatient foot-tapping
peon preview task.complete       # triumphant
peon preview resource.limit      # wounded gasps
peon preview user.spam           # dramatic collapse
```

## Categories

Mapped from the game's internal `sts2_sfx_VO_regent_*` events in
`sfx.bank`. Regent ships with eight distinct emotions across 70 clips —
more voice variety than any other character in the bank — so each CESP
slot gets healthy rotation.

| CESP event         | Game emotion                          | Clips |
|--------------------|---------------------------------------|------:|
| `session.start`    | `regent_greeting`                     |    12 |
| `task.acknowledge` | `regent_superior`                     |     5 |
| `task.complete`    | `regent_triumphant`                   |    10 |
| `task.error`       | `regent_hurt_low`                     |    10 |
| `input.required`   | `regent_impatient`                    |    13 |
| `resource.limit`   | `regent_hurt_mid` + `regent_hurt_high`|    15 |
| `user.spam`        | `regent_die`                          |     5 |

> The Regent holds court through the normal flow — regal greetings,
> smug acknowledgments, triumphant completions. Push too hard and the
> pain ramps: a light wince when something errors, deeper hurt when
> you're hitting rate limits, and an outright collapse when you spam
> the poor man.

<p align="center">
  <img src="assets/regent_win.png" alt="Regent victorious" width="160" />
  &nbsp;
  <img src="assets/regent_hand_point.png" alt="Regent pointing" width="120" />
</p>

**70 clips total · ~32 MB · 48 kHz stereo WAV**

## Source

Regent is one of STS2's five playable characters, voiced by **Mark Ota**.
Audio is extracted from the game's FMOD Studio sound banks:

1. Extract `Slay the Spire 2.pck` with
   [GDRE Tools](https://github.com/GDRETools/gdsdecomp):
   ```sh
   "Godot RE Tools.app" --headless \
       --recover="/path/to/Slay the Spire 2.pck" \
       --output-dir=extraction
   ```
2. Decode the regent subsongs from `extraction/banks/desktop/sfx.bank`
   with [vgmstream](https://github.com/vgmstream/vgmstream):
   ```sh
   vgmstream-cli -s <subsong_n> -i -o "?n.wav" \
       extraction/banks/desktop/sfx.bank
   ```

All 70 regent VO streams were extracted, renamed from their
`sts2_sfx_VO_regent_<emotion>_v<N>_rr<N>` event names to
`regent_<emotion>_<n>.wav` (using the `rr` round-robin number as the
variant), and mapped to CESP categories by emotional context.

## Copyright & Fair Use Notice

The audio clips in this pack are short excerpts of voice lines from
*Slay the Spire 2*, copyright © 2026 Mega Crit, LLC. All rights reserved
by the original owners. Character artwork in `assets/` is likewise
Mega Crit property.

**This pack is:**
- **Non-commercial** — not sold, not monetized
- **Fan-made** — created out of appreciation for the game
- **Minimal in scope** — only short Regent VO grunts and a couple of
  illustrative asset thumbnails are included; no music, no full scenes,
  nothing that could substitute for the original game

This project makes no claim of ownership over any Slay the Spire 2
assets. If Mega Crit or any rights holder objects to this use, the repo
will be taken down promptly upon request.

The pack manifest, scripts, and documentation in this repository are
licensed under [CC-BY-NC-4.0](https://creativecommons.org/licenses/by-nc/4.0/).
Audio and image assets themselves remain the property of their
respective copyright holders.

## Disclaimer

This is an unofficial fan project and is not affiliated with, endorsed
by, or sponsored by Mega Crit, LLC.
