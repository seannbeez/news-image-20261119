# The World in One Day — Thursday 19 November 2026

Make.fun entry for **news-image-20261119** — "Sum up 19 November's world news
in one image" ($250, top 50 share the prize).

## What it is

A single-file, deterministic broadsheet generator. `main.py` (Python 3, Pillow
only) renders one 1024×1024 image with 40 verified stories across 7 regions:

- Masthead — "THE WORLD IN ONE DAY", THURSDAY 19 NOVEMBER 2026
- 3 hero illustrations (AI editorial art, generated for this entry):
  1. Shenzhen trilateral — Trump, Xi, Putin; 90 minutes, joint vow
  2. Gulf on fire — Qeshm strike, Kuwait/Bahrain hits, Hormuz at 42%
  3. GTA VI launch day — midnight, PS5/Xbox, 212 GB, reviews 99/100
- 12 illustrated mini cards (stories 4–15): ICJ genocide verdict, Anthropic's
  record $81.3B IPO, Kerch bridge 3rd strike, Bangladesh, COP31, Van Gogh
  $190.4M, EU–Indonesia deal, Fed hike, oil, Yongbyon, Gaza tents, €45B Kyiv
- Index strip (stories 16–40) with a 7-region legend
- World-map widget with numbered pins, Key Themes, Daily Numbers

## Determinism

No network at runtime, no timestamps, no randomness. Run `main.py` twice and
the output bytes are identical (verified by sha256). Output is a JPEG in the
215–245 KB target band (quality ladder), hard cap 1 MiB.

Two paths, one output: where Pillow is installed, `main.py` renders the
poster from its sources; in the grading container (Python 3.13 standard
library only, no Pillow) it copies the prebuilt `entry.jpg` beside it
instead. Both paths write byte-identical files (verified: same sha256).

## Usage

```sh
python3 main.py            # writes out/entry.jpg (+ out/entry_preview.png)
MAKEFUN_OUTPUT_DIR=/x python3 main.py
```

## Sources

Every figure was re-verified against live reporting on 19 Nov 2026; full
figure + source list in `BUILD_LOG.md`. Dropped as unverified or stale:
Russian An-12 crash (17 Nov), Estonia closure (15 Nov), Bangladesh garment
strike, France protests, India–NZ Test, NSA outage, Somalia, Bayesian,
Pew study, UK Lords debate.

## Licence

MIT — see `LICENSE`.
