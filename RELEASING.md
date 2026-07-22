# Releasing

Source code lives in a separate private repo
(`CFB27-Dynasty-Engine-Dev`) — nothing here is built by CI from source. A
release is a manual step: build the artifact(s) in the dev repo, then attach
them to a GitHub Release here.

## What ships today (2026-07-22)

**Both the app installer and the mod file**, in one release. From the dev
repo's `app/`:

```
node scripts/release.mjs            # dry run — builds + shows what would ship
node scripts/release.mjs --publish  # actually creates the GitHub Release
```

This runs `npm run dist:win` (full build, then `electron-builder` → a Windows
NSIS installer, `electron-builder.yml`), finds the newest `.fbmod` under
`mods/releases/` (built by `mods/src/build-dynasty-engine-v*.mjs`, see that
repo's `mods/README.md`), and — with `--publish` — runs `gh release create`
here with both files attached. Verified end to end (2026-07-22): the packaged
installer's unpacked app opens a real save with every native module
(better-sqlite3, madden-franchise, node-zstd) working, no errors.

**No code signing.** Windows will show a SmartScreen "unrecognized publisher"
warning on first run (click "More info → Run anyway") until a real
code-signing certificate is set up — a separate, paid, not-yet-decided step.

**Updating is just re-running the installer.** No auto-updater — the NSIS
installer targets the same install directory/registry key every version, so
running a newer installer over an existing install upgrades in place. This
was a deliberate choice over building `electron-updater` infrastructure.

## Why manual, not a CI-triggered release

Mod builds require judgment (which FTC edits are ready, growth-rule checks,
in-game verification per the dev repo's `TEST_PLAN.md`) — there's no
"push to main → ship" signal that would be safe to automate. Same reasoning
applies to whatever eventually packages the app: a human decides a build is
release-worthy, then runs the command above.
