# Dynasty Engine

An external front-office / GM tool for a CFB27 dynasty. It runs alongside
the game as its own app and takes over recruiting, the transfer portal,
coaching moves, and NIL (the front-office side of running a program), while
CFB27 itself keeps doing what it does best: playing and simulating games.

A small companion mod turns the in-game recruiting/portal systems **off**
(zeroes recruiting hours, blocks player-initiated transfers), so those
decisions only happen through the app. The app reads your real dynasty save
directly and, when you commit a decision, writes the result back into it.
There's no separate universe to keep in sync, no manual re-entry of your
roster or class.

**Why it exists:** CFB27's on-field game is deep, but the front-office layer
around it (who you recruit, how the portal shakes out, what NIL actually
buys, how a coaching career plays out over a decade) is thin and mostly
invisible. There's no real memory across seasons (where did this player
actually come from? what has this coach actually built?), and the
recruiting/portal systems the game does have don't hold up to sustained,
GM-level attention. Dynasty Engine is that missing layer: a persistent,
detailed, honest read on your program, and the actual mechanism driving
recruiting/portal/NIL/coaching decisions, not a spreadsheet on the side.

This repo is the **public side** of the project: releases, bug reports,
feature requests, and questions. The app's source code lives in a separate
private repo. This one exists so anyone can get the tool, report a problem,
and find answers without needing access to the source.

## Get it

Latest release (app + mod): see [Releases](../../releases).

## Contents

| Page | What's there |
|---|---|
| [How it works](#how-it-works) | The mod + app, on this page |
| [docs/features.md](docs/features.md) | Recruiting, Scouting, Commitments, the Portal, NIL & Budget, Coaching, Data Safety |
| [Design principles](#design-principles) | What the tool will and won't do, on this page |
| [docs/roadmap.md](docs/roadmap.md) | The build order, and a possible future direction under consideration |
| [This is an early preview](#this-is-an-early-preview-and-its-honest-about-that) | Where the app actually stands right now, on this page |
| [Get help / get involved](#get-help--get-involved) | Report a bug, ask a question, on this page |
| [Screens](#screens) | Live screenshots of every screen, at the bottom of this page |

## How it works

- **The mod** installs through MMC like any other CFB27 mod and disables the
  in-game systems this tool replaces: it zeroes out the weekly hours coaches
  spend on in-game recruiting/scouting, so the AI's old click-to-recruit loop
  simply has nothing to spend, and it blocks player-initiated transfers, so
  the portal only moves players the way this tool decides.
- **It also retunes recruit generation itself, down to the archetype.** The
  game's own recruiting-class generator still produces every prospect, and
  this isn't a separate generator bolted on, but the mod reshapes the star
  ratings it hands out, and it doesn't just flatten that by position. A true
  deep-threat receiver or a shutdown corner gets a real shot at 4★/5★; an
  elite tackle prospect is restored to the 5★ prominence real recruiting
  gives offensive linemen; a pure run-blocking receiver or fullback
  essentially never is one, because that's how actual recruiting rankings
  work, not a flat blue-chip rate shared by every archetype at a position.
  Overall the class comes out with more realistic 4★/5★ counts, no more
  scrubby 1★ recruits (folded into a stronger 2★ tier instead), and a small
  floor so a handful of states the game almost never recruits from actually
  show up occasionally. Games and on-field sim are untouched, vanilla
  CFB27.
- **In-game NIL gets zeroed out, on purpose.** Every player's raw in-game
  NIL value and NIL-related flags get cleared to nothing, so there's no
  stray number on a player's in-game card that could make you think the
  game's own systems are handling NIL, or that you need to do anything
  with them yourself. Every NIL number you actually see, and every
  recruiting/retention/portal decision it drives, comes entirely from this
  tool's own dollar-based system, run independently of whatever the game
  itself still has on the books.
- **The app** opens your real save file, parses it, and layers a persistent
  memory on top (a small local database per dynasty) for everything the save
  itself doesn't track: where a player actually came from, a coach's career
  history, your program's ledgers. Your save stays the canonical source for
  game data; the app never invents a parallel copy of it.
- **Writing back**: nothing changes in your save silently. Every action that
  touches the save (signing a recruit, moving a transfer, a coach hire) is
  explicit, previewable before it happens, and automatically checkpointed
  (both the save and the app's own memory), so any decision can be undone by
  restoring the checkpoint.

## Features

Prospects and the recruiting board, a real scouting network, commitment
decisions that weigh six factors per recruit, a self-correcting CPU league,
a promise ledger tied to your coach's credibility, a fully simulated
transfer portal, a real-dollar NIL budget, the coaching carousel and career
legacy, and the Vault's paired checkpoints.

**→ Full writeup: [docs/features.md](docs/features.md)**

## Design principles

- **You see what a GM would actually know.** Recruits are graded in bands
  and qualitative reads, never a raw hidden number pretending to be
  certainty. Rostered and portal players, who you'd genuinely know the truth
  about, show real numbers.
- **Real dollars, not an invented currency.** NIL is priced in actual dollars
  against a real budget, because program wealth is a real-world fact the
  game itself doesn't model.
- **Consequences are real.** Declined offers, broken promises, and lost
  recruiting battles stay lost. The Vault protects against bugs and
  mistakes, not against the outcomes of your own decisions.
- **Your save is never at risk.** Every write is backed up first,
  previewable before it happens, and reversible after.
- **The tool has memory the game doesn't.** Player origin, coach career
  history, program ledgers, all things a real front office would track and
  the base game simply forgets.

## Where this is going

Built in phases: recruiting core (current focus), then coaches, then program
intelligence, then facilities/equipment. There's also a possible bigger
future direction under consideration, modeling real-world salary caps and
transfer limits instead of today's system.

**→ Full writeup: [docs/roadmap.md](docs/roadmap.md)**

## This is an early preview, and it's honest about that

**The app is not end-to-end functional yet.** Individual systems work against
a real save (opening a dynasty, reading the prospect pool, running a portal
window, scoring a coaching career), but you cannot yet play a full season
through the tool start to finish. Read everything above as a description of
what's being built and how it's meant to work, not as a feature list you can
go use today. Some of it is finished, some is half-wired, and some is design
that hasn't been built at all. If you want to know where a specific system
actually stands, ask; I'd rather answer straight than keep a status list here
that quietly goes stale.

I'm sharing it now, unfinished, on purpose. I've spent a long stretch
building this in the dark with nobody looking at it, and ideas from people
who actually play dynasty are worth far more early than late. If something
here sounds wrong, or there's an obvious thing missing, that's exactly what
I want to hear. Feedback is very welcome; just send it directly for now
rather than through Issues/Discussions.

## Get help / get involved

| I want to... | Go here |
|---|---|
| Report something broken | [New bug report](../../issues/new?template=bug_report.yml) |
| Suggest something | [New feature request](../../issues/new?template=feature_request.yml) |
| Ask a question | [Discussions → Q&A](../../discussions/categories/q-a) |

## Status

Private for now. Public release timing is still being decided. Everything
above already works the same whether the repo is private (for
collaborators) or public.

---

## Screens

Every screen in the app, captured from a real dynasty save mid-bowl-season.
These are live screenshots, not mockups: the numbers, names, and rosters are
what the tool actually produced from that save. Remember the honesty note
above, though. Some of what's pictured is finished, some is half-wired, and a
screen existing doesn't mean the system behind it is complete.

### Pulse — the weekly decision inbox

The landing screen: what needs a decision this week, and a running wire of
everything that moved.

![Pulse](docs/screenshots/pulse.png)

### Prospects — the recruit pool

The full pool from your save, read in letter-grade bands rather than raw
ratings.

![Prospects](docs/screenshots/prospects.png)

Opening any prospect gives you his card: projected playing time at your
program, an estimated NIL range (a range, never a quote), per-stat grade
bands graded against others at his position, and where his recruitment
actually stands.

![Prospect card](docs/screenshots/prospect-card.png)

### Board — Priority / Target / Watch

Where you sort the pool into tiers, which is what actually spends your
staff's attention.

![Board](docs/screenshots/board.png)

### Scouting — the beat network

Assign staff beats to a position group in a region and let them file reports
over time.

![Scouting](docs/screenshots/scouting.png)

### Offers — what the sheets you cut actually bought

![Offers](docs/screenshots/offers.png)

### Transfer Portal

![Portal](docs/screenshots/portal.png)

### Budget — the NIL ledger

One annual pool covering the roster book, recruit deals, and retention
raises, with your true headroom and what's at risk in open offers. The
forward view projects what next year's book looks like once graduating
seniors and likely early NFL declarations come off it.

![Budget](docs/screenshots/budget.png)

### Roster

![Roster](docs/screenshots/roster.png)

Rostered players are people you'd genuinely know the truth about, so their
cards show real ratings and real NIL, unlike a recruit's bands.

![Roster player card](docs/screenshots/roster-player-card.png)

### Training Results

*(Placeholder — the progression engine behind this screen is still being
designed.)*

![Training Results](docs/screenshots/training-results.png)

### Coach Legacy

Your career scored on one lifetime number and plotted directly against real
historical coaching legends and every coach in your save.

![Coach Legacy](docs/screenshots/coach-legacy.png)

### Coach Trust

![Coach Trust](docs/screenshots/coach-trust.png)

### Coaching Carousel

The league-wide job market. **Edit board** is where you set openings,
candidate ranks, and interest:

![Carousel — edit board](docs/screenshots/carousel-edit-board.png)

**Your standing** is where your own coach sits in the market:

![Carousel — your standing](docs/screenshots/carousel-your-standing.png)

**Chain / who takes what** projects the whole cascade: each team's leading
candidate takes the job he most prefers, which frees the others and lets the
next candidate step up.

![Carousel — chain](docs/screenshots/carousel-chain.png)

**Next week** simulates the following week's hiring round:

![Carousel — next week](docs/screenshots/carousel-next-week.png)

### Vault — paired checkpoints

Roll the entire world (save + the tool's own memory) back to a saved moment,
always as a matched pair.

![Vault](docs/screenshots/vault.png)

### Options

![Options](docs/screenshots/options.png)
