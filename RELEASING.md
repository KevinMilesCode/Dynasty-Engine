# Releasing

Source code lives in a separate private repo
(`CFB27-Dynasty-Engine-Dev`) — nothing here is built by CI from source. A
release is a manual step: build the artifact(s) in the dev repo, then attach
them to a GitHub Release here.

## What ships today

**The `.fbmod` mod file** (`mods/releases/*.fbmod` in the dev repo — built by
`mods/src/build-dynasty-engine-v*.mjs`, see that repo's `mods/README.md`).

```
gh release create v0.087 \
  "path/to/Dynasty-Engine-v0.087.fbmod" \
  --repo KevinMilesCode/Dynasty-Engine \
  --title "v0.087" \
  --notes "See mods/releases/CHANGELOG.md in the dev repo for detail."
```

## What's planned, not built yet

**The Electron app itself, as an installer.** The dev repo currently only
builds unpacked `dist/` + `dist-electron/` output (`npm run build`) — there's
no `electron-builder`/`electron-forge` packaging step, no installer target,
and no code-signing setup. Producing a real installer (`.exe`/`.dmg`/etc.) to
attach here is separate follow-on work, not something this release process
can do yet.

## Why manual, not a CI-triggered release

Mod builds require judgment (which FTC edits are ready, growth-rule checks,
in-game verification per the dev repo's `TEST_PLAN.md`) — there's no
"push to main → ship" signal that would be safe to automate. Same reasoning
applies to whatever eventually packages the app: a human decides a build is
release-worthy, then runs the command above.
