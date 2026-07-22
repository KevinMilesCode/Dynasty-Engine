# Current Status

_Snapshot as of 2026-07-22. This page is updated by hand, occasionally, while
the project is in early preview — it isn't tied to specific releases yet.
Once there's a first real v0.1, wiki updates will start tracking what
changed release by release._

## What Dynasty Engine is

An external front-office / GM tool for a CFB27 dynasty. It drives
recruiting, the transfer portal, and NIL **outside** the game — a companion
mod blocks in-game recruiting hours so this tool is the only way to scout,
offer, and sign. Everything else about CFB27 (playing games, prospect
generation, on-field simulation) stays exactly as the base game does it.

## What works today

The current build covers the recruiting core end to end:

- **Prospects** — browse the full high school / JUCO / portal pool from your
  real save: stars, letter-grade scouting reads, recruitment interest, an
  estimated NIL range, and a detail view for every player.
- **Board** — a tiered priority list (Priority / Target / Watch) over your
  staff's attention, with a visit-influence "warmth" read per prospect.
- **Scouting** — spend staff effort narrowing scouting reads and turning up
  sleepers.
- **Pulse** — a decision inbox surfacing rival offers, visit windows, and
  commit pressure as they happen, plus a running feed of the week's
  recruiting movement.
- **Budget** — the team's NIL pool weighed against roster contracts,
  committed recruit deals, and at-risk offers.
- **Portal** — a full simulated transfer-portal window: entrants, CPU
  bidding, day-by-day decisions, and writing the resulting roster moves back
  to your save.
- **Roster** — the projected depth chart, including incoming/outgoing portal
  moves and where each player originally came from (HS / JUCO / portal).
- **Coach Legacy** — a career scoreboard for your coach, benchmarked against
  historic greats.
- **Vault** — automatic checkpoints before anything writes to your save, with
  one-click restore.

## What's in progress

- **Coaching Carousel** — the coach hiring/firing job market. Most of it is
  built (expressing interest in openings, running the market, hot-coach
  career leaps); understanding and surfacing CPU firings/retirements is the
  one piece still being finished.
- **Recruit-class generation tuning** — a small mod-side adjustment to
  recruit star distribution, built and pending final in-game verification.
- **Visual redesign** — the app's look is being reworked screen by screen
  (a couple of screens are done, most aren't yet).
- **Coach perks** — wiring the coaching talent trees' effects into the
  systems above (currently the trees exist and rename correctly in-game, but
  most of their gameplay effects aren't hooked up yet).

## What's not built yet

- **An installer.** Right now there's no packaged download — if you're
  previewing the app, you got it set up directly.
- **Everything past recruiting/portal/coaches** — facilities, program
  intelligence/almanac, and later phases haven't been started.

## This is an early preview

If you're reading this, you're one of a small number of people trying the
app before any real release. Expect rough edges and missing polish outside
the areas above — feedback is very welcome, just send it directly for now
rather than through Issues/Discussions.
