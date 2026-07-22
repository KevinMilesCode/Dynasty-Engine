# About Dynasty Engine

> Reading this on GitHub's Code tab instead of a Wiki tab? That's expected —
> see the note on [Home](Home.md) for why.

## What it is

Dynasty Engine is an external front-office / GM tool for a CFB27 dynasty. It
runs alongside the game as its own app, and takes over recruiting, the
transfer portal, coaching moves, and NIL — the front-office side of running a
program — while CFB27 itself keeps doing what it does best: playing and
simulating games.

A small companion mod turns the in-game recruiting/portal systems **off**
(zeroes recruiting hours, blocks player-initiated transfers), so those
decisions only happen through the app. The app reads your real dynasty save
directly and, when you commit a decision, writes the result back into it —
there's no separate universe to keep in sync, no manual re-entry of your
roster or class.

## Why it exists

CFB27's on-field game is deep, but the front-office layer around it — who you
recruit, how the portal shakes out, what NIL actually buys, how a coaching
career plays out over a decade — is thin and mostly invisible. There's no
real memory across seasons (where did this player actually come from? what
has this coach actually built?), and the recruiting/portal systems the game
does have don't hold up to sustained, GM-level attention.

Dynasty Engine exists to be that missing layer: a persistent, detailed,
honest read on your program, and the actual mechanism for making
recruiting/portal/NIL/coaching decisions — not a spreadsheet on the side, the
thing that's actually driving those parts of the save.

## How it works

- **The mod** installs through MMC like any other CFB27 mod, and disables the
  in-game systems this tool replaces (recruiting hours, player-initiated
  transfers). Everything else about the game — games, on-field sim, prospect
  generation — is untouched, vanilla CFB27.
- **The app** opens your real save file, parses it, and layers a persistent
  memory on top (a small local database per dynasty) for everything the save
  itself doesn't track — where a player actually came from, a coach's career
  history, your program's ledgers. Your save stays the canonical source for
  game data; the app never invents a parallel copy of it.
- **Writing back**: nothing changes in your save silently. Every action that
  touches the save (signing a recruit, moving a transfer, a coach hire) is
  explicit, previewable before it happens, and automatically checkpointed —
  both the save and the app's own memory — so any decision can be undone by
  restoring the checkpoint.

## Features today

**Recruiting**
- Full high school / JUCO / transfer-portal prospect pool, read straight off
  your save — stars, per-stat scouting grades, recruitment interest, and an
  estimated NIL range for every player.
- A tiered board (Priority / Target / Watch) for managing staff attention,
  with a "warmth" read on how a relationship is actually trending.
- A scouting network for spending staff effort narrowing reads and turning up
  sleepers other programs haven't found.
- A weekly decision inbox (rival offers, visit windows, commit pressure) so
  nothing important gets buried.

**Transfer Portal**
- A fully simulated portal window — entrants, competing bids from CPU
  programs, day-by-day decisions on realistic personality-driven timers — that
  writes the resulting roster moves back into your save when it closes.

**NIL & Budget**
- A program NIL pool weighed against roster contracts, committed recruit
  deals, and at-risk offers, with a per-position spending plan.

**Coaching**
- A career scoreboard (Coach Legacy) benchmarking your coach against a set of
  real historic greats — trajectory, all-time leaderboard, peak vs. longevity.

**Data safety**
- Automatic checkpoints of both your save and the app's own memory before
  anything writes, with one-click restore — the app treats your dynasty as
  something that should never be at risk from using it.

See [Status](Status.md) for exactly what's built vs. still in progress right
now — this page describes the whole picture; that one tracks the current
build.

## Design principles

- **You see what a GM would actually know.** Recruits are graded in bands and
  qualitative reads, never a raw hidden number pretending to be certainty —
  the fog is part of being honest about what scouting actually gives you.
  Rostered and portal players, who you'd genuinely know the truth about,
  show real numbers.
- **Your save is never at risk.** Every write is backed up first, previewable
  before it happens, and reversible after.
- **The tool has memory the game doesn't.** Player origin, coach career
  history, program ledgers — things a real front office would track and the
  base game simply forgets.

## The vision — where this is going

Dynasty Engine is being built in phases, roughly by system:

1. **Recruiting core (current focus)** — scouting, the board, offers,
   commitments, the transfer portal, NIL, and the read-only data (awards,
   stats, prior-season results) the portal's own logic depends on.
2. **Coaches** — the full coaching carousel (a personality-driven,
   league-wide job market with realistic hires and firings), a career ledger,
   staff management, and reworking the in-game coach talent trees so their
   perks actually do something meaningful through the tool.
3. **Program intelligence** — an Almanac (champions, awards, draft history),
   Insights (recruiting hit-rate and development analytics), and
   simulated-world events (injuries, suspensions, booster swings, alumni
   donations after a big season) that give a dynasty more texture over time.
4. **Program systems** — further out: facilities and equipment/identity, the
   longer-horizon program-building layer.

Each phase builds on the last; recruiting has to be solid before coaching
carousel realism matters, and both need to exist before program-wide
intelligence is worth building on top of them.
