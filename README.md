# SKPSM

**PC mods on your PS4, file by file.**

SKPSM installs PC mods on a PS4 with GoldHEN: it checks every mod, converts
what the console needs (textures to GNF, meshes, BodySlide, load order) and
uploads it over FTP, all from a desktop app or the command line.

- **Skyrim Special Edition** (version 1.32) — supported
- RE4 / RE3 — in development · RE2 and Cyberpunk 2077 — planned

<p align="center"><img src="docs/screenshots/skpsm-1.png" width="80%" alt="SKPSM screenshot 1"></p>
<p align="center"><img src="docs/screenshots/skpsm-1b.png" width="80%" alt="SKPSM screenshot 2"></p>
<p align="center"><img src="docs/screenshots/skpsm-2.png" width="80%" alt="SKPSM screenshot 3"></p>

## Downloads

| Platform | File | Notes |
|----------|------|-------|
| Linux (x86_64) | [SkPSM-0.1.0-x86_64.AppImage](https://github.com/Betest/skpsm-rust/releases/latest) | Runs without installing |
| Windows | coming soon | — |

### AppImage

```
chmod +x SkPSM-0.1.0-x86_64.AppImage
./SkPSM-0.1.0-x86_64.AppImage
```

The desktop app has tabs for Mods, Build & Deploy, BodySlide, PS4 / Game and
Settings. The `skpsm` CLI is bundled too.

SHA-256 (v0.1.0):

`041f57a0dcaf548b8864413b2f8864fbbba2f9e651dca6cb75762172cc8fe395`

## OSE plugin

Mods that need SKSE work through **OSE** (Orbis Script Extender), our GoldHEN
plugin for the PS4. Download `ose.prx` from the [latest
release](https://github.com/Betest/skpsm-rust/releases/latest), put it in
`/data/GoldHEN/plugins/` on the console and enable it in
`/data/GoldHEN/plugins.ini` — or let `skpsm deploy` do both when `[goldhen]
ose_local` in `config.ini` points to your local copy. Built with the OpenOrbis
toolchain and the GoldHEN Plugins SDK. GPL-3.0; the source is attached to the
release.

## How PC dependencies work on PS4

Three pieces stand in for the PC tools mods depend on:

| PS4 piece | PC counterpart | What it does |
|-----------|----------------|--------------|
| **OSE** — Orbis Script Extender | SKSE | Runs the Papyrus scripts of mods that need SKSE, plus the hair and body physics. Ships as `ose.prx` (see above). |
| **OSB** — Orbis Scaleform Bridge | SKSE's Scaleform/UI layer | Part of OSE: the Flash bridge that UI mods like SkyUI rely on. |
| **OUP** — Orbis Unofficial Patch | USSEP | A progressive, generated patch. When a mod needs records from a master that cannot be installed whole (USSEP, NoFloatingFog, …), the build generates a plugin named after that master with only the records your mods use — for example a minimal `Unofficial Skyrim Special Edition Patch.esp` with the 16 records Northbourne NPCs needs out of USSEP's ~59,000. It grows as you add mods. |

## Website

Documentation and email updates: <https://skpsm.it-bridge.workers.dev>

## Disclaimer

Read [DISCLAIMER.md](DISCLAIMER.md). You need a legal copy of Skyrim Special
Edition. We do not support piracy.

## License and credits

- License: [Apache-2.0](LICENSE) — see also [NOTICE](NOTICE)
- Credits: [CREDITS.md](CREDITS.md)
- The source code is not published for now.
