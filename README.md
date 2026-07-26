# Dynasty Engine

An external front-office / GM tool for a CFB27 dynasty. It runs alongside the
game as its own Windows app and takes over recruiting, the transfer portal,
coaching moves, and NIL, while CFB27 keeps doing what it does best: playing and
simulating games.

The app opens your real dynasty save, reads it directly, and writes decisions
back into it when you commit them. There is no separate universe to keep in
sync, and no re-entering your roster or your class by hand.

---

## Read this before you download anything

**This is barely alpha. Do not start a real dynasty in this tool yet.**

I would normally keep a build in this state private. I am sharing it because I
have spent a long stretch building it with nobody looking at it, and I do not
yet have enough people involved to get the feedback I need before committing to
serious tuning, refinement, and testing. That feedback is the entire reason
this release exists.

What that means concretely:

- **Systems work in isolation; the full season loop does not.** You cannot play
  a season start to finish through the tool.
- **Numbers are untuned.** NIL prices, commit odds, portal behavior, and
  generation targets are all first-pass values, not balanced ones.
- **Data can break between versions.** The tool keeps its own per-dynasty
  database alongside your save, and its shape is still changing. Migrations
  exist, but at this stage I will discard that data rather than carry a bad
  structure forward, which has already happened once.
- **Treat every dynasty you open with it as disposable.** Back up your save
  yourself before you point the app at it.

The right way to use version 0.098 is to look around, break things, and tell me
what is wrong. Not to invest 15 seasons in it.

---

## Quick links

| Go here | For |
|---|---|
| [Install and first run](docs/install.md) | Requirements, the app, the mod, the demo save, known limitations |
| [The weekly loop](#how-you-actually-use-it-the-weekly-loop) | How the tool is meant to be used, and what it replaces in-game |
| [Demo save](docs/install.md#try-it-without-the-game) | Open a real dynasty in the tool without launching CFB27 |
| [Walkthrough video](#walkthrough-video) | A guided tour of every screen |
| [Screens](docs/screens.md) | Screenshot of every screen in the app |
| [Features](docs/features.md) | What each system does, with what is built and what is not marked inline |
| [Roadmap](docs/roadmap.md) | Phase plan, plus two directions still under consideration |
| [Releases](../../releases) | Downloads: installer, `.fbmod`, demo save |
| [Report a bug](../../issues/new?template=bug_report.yml) | Prefer the in-app **Report Bug** button, it attaches diagnostics for you |
| [Ask a question](../../discussions/new?category=q-a) | Prefer the in-app **Ask Question** button |
| [Request a feature](../../issues/new?template=feature_request.yml) | Prefer the in-app **Request Feature** button |
| [Usage terms](LICENSE.md) | What you may and may not do with the build |

---

## Why it exists

CFB27's on-field game is deep, but the front-office layer around it (who you
recruit, how the portal shakes out, what NIL actually buys, how a coaching
career plays out over a decade) is thin and mostly invisible. There is no real
memory across seasons: where did this player actually come from, what has this
coach actually built? And the recruiting and portal systems the game does have
do not hold up to sustained, GM-level attention. Dynasty Engine is that missing
layer.

## How you actually use it: the weekly loop

Dynasty Engine is not a companion dashboard you glance at. **It is meant to be
opened at the start of every single week of your dynasty**, and it replaces a
large amount of what you would otherwise be doing inside CFB27.

The loop, in order, every week:

1. **Open Dynasty Engine and load your save.** Pulse, the landing screen, is
   the week brief: what needs a decision from you this week, plus a wire of
   everything that moved since last time.
2. **Do the front-office work here.** Scouting beats, sorting the board,
   cutting NIL offers, making and grading promises, working the portal during
   its window, retention, coaching moves. None of it happens in the game
   anymore.
3. **Commit, then close the app.** Every decision that touches the save is
   explicit and previewable, and the app checkpoints both halves (your save and
   its own database) before writing. The app never writes to your save on its
   own while you are away.
4. **Go back to CFB27, play or sim the week, and save in-game.**
5. **Come back to Dynasty Engine for the next week.**

Both directions of that loop matter. The app is the only place recruiting
happens, because the mod zeroes the game's recruiting and scouting hours. And
the game is the only place football happens, because Dynasty Engine does not
simulate games at all. If you skip weeks in the tool, offers expire, visit
windows close, and recruits commit elsewhere without you having had a say.

What the tool now owns instead of the game: all recruiting and scouting, all
scholarship offers, all NIL (in real dollars, the game's own NIL numbers are
zeroed on purpose), who enters the transfer portal and where they land, and
coaching-carousel moves. What the game still owns: everything on the field,
plus the roster and results the tool reads back out of your save.

## How it works, briefly

Dynasty Engine is two halves, and you need both.

**The mod** (`Dynasty-Engine-v0.098.fbmod`) is small, and everything it does is
about getting the game's own systems out of the way. It zeroes the weekly hours
coaches spend on in-game recruiting and scouting, so the game's click-to-recruit
loop has nothing left to spend and recruiting only happens through the app. It
retunes recruit generation down to the archetype: the game's own generator still
produces every prospect, but the mod reshapes the star ratings it hands out so
position value looks like real recruiting, with more realistic 4-star and 5-star
counts and no 1-star filler. It also renames and repurposes three coach talent
trees so what you are buying reads correctly, and suppresses in-game player XP
so progression is not being decided in two places at once. Games and on-field
simulation are untouched vanilla CFB27.

**The app** does everything else: it parses your save, layers a persistent
per-dynasty memory on top for what the save does not track, turns off
player-initiated transfers, clears in-game NIL so no stray number implies the
game is handling it, and writes every decision back explicitly, previewable
first and checkpointed automatically.

**→ [Full detail in Features](docs/features.md)**

## What is in it

Prospects and the recruiting board, a real scouting network, commitment
decisions that weigh six factors per recruit, a self-correcting CPU league, a
promise ledger tied to your coach's credibility, a fully simulated transfer
portal, a real-dollar NIL budget, the coaching carousel and career legacy, and
the Vault's paired checkpoints.

Each of those is marked in [Features](docs/features.md) with where it actually
stands. If something is not marked, ask.

## Design principles

- **You see what a GM would actually know.** Recruits are graded in bands and
  qualitative reads, never a raw hidden number pretending to be certainty.
  Rostered and portal players, who you would genuinely know the truth about,
  show real numbers.
- **Real dollars, not an invented currency.** NIL is priced in actual dollars
  against a real budget, because program wealth is a real-world fact the game
  itself does not model.
- **Consequences are real.** Declined offers, broken promises, and lost
  recruiting battles stay lost. The Vault protects against bugs and mistakes,
  not against the outcomes of your own decisions.
- **Your save is never at risk from the tool.** Every write is backed up first,
  previewable before it happens, and reversible after.
- **The tool has memory the game does not.** Player origin, coach career
  history, program ledgers: all things a real front office would track and the
  base game simply forgets.

## Walkthrough video

A guided tour of every screen, recorded against a real save.

<!-- PASTE THE YOUTUBE LINK HERE, then delete this comment line. -->
*Link coming shortly. Until it lands, [Screens](docs/screens.md) has a
screenshot and a description of every screen in the app.*

## Feedback

**Use the buttons in the app.** The left sidebar has a Community section with
**Ask Question**, **Report Bug**, and **Request Feature**. Report Bug is the
important one: it bundles diagnostics (and optionally your save and dynasty
database) into a folder, then opens the issue form so you can attach them. A
bug report with that bundle is worth several without it.

If you cannot get the app open at all, file it here directly:
[bug](../../issues/new?template=bug_report.yml) ·
[question](../../discussions/new?category=q-a) ·
[feature](../../issues/new?template=feature_request.yml)

## About this repo

This is the public side of the project: releases, docs, and the wiki. The app's
source lives in a separate private repo. This one exists so anyone can get the
tool and find answers without needing access to the source.

Usage terms are in [LICENSE.md](LICENSE.md). Not affiliated with, endorsed by,
or associated with Electronic Arts.
