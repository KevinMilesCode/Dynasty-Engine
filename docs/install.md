# Install and first run

← Back to [README](../README.md)

> **Barely alpha. Do not start a real dynasty in this tool yet.** Read the
> warning at the top of the [README](../README.md#read-this-before-you-download-anything)
> before you install anything. Back up any save you point the app at.

## Contents

- [What you need](#what-you-need)
- [1. Install the mod](#1-install-the-mod)
- [2. Install the app](#2-install-the-app)
- [3. First run](#3-first-run)
- [Try it without the game](#try-it-without-the-game)
- [The weekly loop](#the-weekly-loop)
- [Uninstalling](#uninstalling)

## What you need

- **Windows 64-bit.**
- **CFB27** and a **Frosty-based mod manager (MMC)**, if you want to use your
  own dynasty. Not needed for the demo save.
- **An existing dynasty save**, or the demo save from the release. The app reads
  your save; it does not generate a world of its own.
- Both halves of the release: the **app installer** and the
  **`Dynasty-Engine-v0.098.fbmod`**. They are versioned together. The app checks
  that the mod is actually in force in your save and refuses to open one where
  it is not.

Downloads are on the [Releases](../../../releases) page.

## 1. Install the mod

1. Put `Dynasty-Engine-v0.098.fbmod` in your mod manager's
   `Mods\CollegeFB27\` folder.
2. Enable it in the mod manager and launch the game through the mod manager as
   usual.
3. **Enable it alone.** Do not enable it alongside another Dynasty Engine build
   or any other mod that patches CFB27's dynasty tuning. Two mods touching the
   same tuning resource means the higher-priority one wins silently, and you
   will get a dynasty that looks modded but is not.
4. **Start a new dynasty with the mod already enabled** if you want its recruit
   generation changes. Generation happens once, when the class is created, so
   an existing dynasty keeps the classes it already generated.

What the mod changes: recruiting and scouting hours are zeroed, three coach
talent trees are renamed and repurposed, in-game player XP is suppressed, and
recruit generation is retuned by archetype. Games and on-field simulation are
untouched.

## 2. Install the app

Run the installer from the release. It is a standard Windows installer.

It is **not code signed yet**, so Windows SmartScreen will show an
"unrecognized publisher" warning the first time. More info → Run anyway.

## 3. First run

1. Save your dynasty in CFB27 and exit to the main menu (or close the game).
2. Open Dynasty Engine. The Open screen lists the saves it found in your
   `Documents\EA SPORTS College Football ##\saves` folder, most recently used
   first.
3. Pick your save. The app checks that the mod is in force before it opens
   anything. If it refuses, the panel tells you which check failed and what to
   do about it.
4. Work through the **Getting Started** checklist. It has a short list of
   one-time setup actions plus five things you have to acknowledge, because they
   change how you play: all recruiting happens in the tool, in-game NIL numbers
   mean nothing, the tool decides who enters the portal, the mod has to stay
   enabled, and the loop is work-here then play-in-game.
5. You land on **Pulse**, the week brief.

## Try it without the game

The release includes a **demo save**: a real dynasty save, already generated
under the Dynasty Engine mod, so you can open the tool and look at every screen
with real data without installing the mod or launching CFB27 at all.

1. Install the app (step 2 above). You do not need the mod or the game for this.
2. Put the demo save file in your
   `Documents\EA SPORTS College Football ##\saves` folder. If you do not have
   that folder because CFB27 is not installed, create it with that exact name.
3. Open the app and pick the demo save from the list.

The demo save is for looking around, not for playing. It is a snapshot of
somebody else's dynasty at one moment, and anything you commit into it is only
meaningful inside that copy.

## The weekly loop

The tool is meant to be opened at the **start of every week** of your dynasty,
and it replaces a large part of what you would otherwise do inside the game.
The full explanation is in the
[README](../README.md#how-you-actually-use-it-the-weekly-loop). The short
version:

**Open the tool → do the front-office work → commit and close → play and save
in CFB27 → come back next week.**

The app never writes to your save on its own. Every write is explicit,
previewable, and checkpointed first.

## Uninstalling

Uninstall the app from Windows Settings, and disable or delete the `.fbmod` in
your mod manager. Removing the mod restores the game's own recruiting hours,
NIL, and XP behavior for future weeks, but it does not undo changes the tool
already wrote into your save. Restore a Vault checkpoint or your own backup for
that.

## Something broken

Use the **Report Bug** button in the app's Community sidebar. It bundles
diagnostics, and optionally your save and dynasty database, into a folder and
opens the issue form so you can attach them. If the app will not open at all,
file it directly: [bug](../../../issues/new?template=bug_report.yml) ·
[question](../../../discussions/new?category=q-a) ·
[feature](../../../issues/new?template=feature_request.yml)
