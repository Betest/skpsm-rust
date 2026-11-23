# Changelog

All dates in UTC.

## v0.1.0 — 2026-11-23

First public release.

### Desktop app (Linux)

- Mods, Build & Deploy, BodySlide, PS4 / Game and Settings tabs.
- Progress bars for build and deploy.
- Load order export with each plugin's archive.

### CLI

- The original tool's commands: `init`, `check`, `conflicts`, `build`,
  `bodyslide`, `deploy`, `undeploy`, `restore`, `plugins`, `discover`, `logs`,
  `probe`, `sample`, `game-files`, `dump-eboot`, `ftp-check` and `status`.
- OSE Scripts generated during build (`[goldhen] ose_local`).
- FTP upload of only what changed, with a manifest and resume of an
  interrupted deploy.

### Other

- Apache-2.0 licensed. The source code is not published for now.
