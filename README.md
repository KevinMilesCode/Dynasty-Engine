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

## How it works

- **The mod** installs through MMC like any other CFB27 mod and disables the
  in-game systems this tool replaces (recruiting hours, player-initiated
  transfers). Everything else about the game (games, on-field sim, prospect
  generation) is untouched, vanilla CFB27.
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

### Recruiting: Prospects, Board, and reading a recruit honestly

**Prospects** is the full high school / JUCO / portal pool pulled straight
from your save: stars, per-stat scouting grades, recruitment interest, an
estimated NIL range, and a detail view for every player. Recruits are read
through **letter-grade bands** (like "B-/B") instead of a hard number, and
that's deliberate: the uncertainty represents projection, not incomplete
scouting. Even the tightest band is still an evaluation, never "the truth."
Only actual rostered or portal players ever show a real overall rating.

**Board** is where you sort recruits into Priority / Target / Watch tiers,
which controls how your staff's attention gets spent and how much
relationship-building influence a recruit accrues. Rival interest is shown
only as a qualitative "warmth" read, never a number or a progress bar,
because a fill-bar would just redraw a hidden number as a shape. The goal is
for recruiting to feel like reading a scouting report, not watching a
win-probability gauge.

**Pulse** is the weekly decision inbox: rival offers, visit windows, and
commit pressure surfaced as they happen, plus a running feed narrating the
week's recruiting movement, so nothing important gets buried between
windows.

### Scouting: finding value the rankings don't show

The **Scouting Network** replaces a slot-machine "click for a random
sleeper" mechanic with something closer to actually scouting: you assign
staff **beats** (a position group in a region, like "Georgia defensive
backs") that run for about a month of game-time and dig into the deep,
unranked pool where real value hides (the top of the class is already public
knowledge; everyone knows who the best players are). A beat doesn't hand you
a verdict outright. It files scouting reports over time that tighten a
covered prospect's per-stat grade bands and add a written, opinionated read
("plays faster than his rank," "worth a second look"), and you decide who's
worth chasing. There's no guaranteed hit: reports carry real uncertainty,
like an actual scout's opinion.

The payoff loops back into NIL: because a recruit's price follows his public
ranking (see below), a hidden gem you found is cheap relative to his real
ability. And blue-blood programs don't hoover up every sleeper for free.
Contested top recruitments eat the same staff attention that funds scouting
beats, so a leaner program running several beats at once can find value the
powerhouses never had the bandwidth to chase.

### Commitments: how a recruit actually decides

Every recruit's decision comes down to one running score per school, built
from six factors: relationship strength, how competitive your money offer
is, whether he'd actually play early, how the program's overall
trajectory/strength fits his ambitions, whether your promises match his
priorities, and geography/home ties. Those factors are weighted differently
for every recruit based on his personality, so a kid who cares mostly about
playing time genuinely decides on playing time, not a one-size-fits-all
formula.

Recruits move through visible stages (shortlisted → soft-committed →
hard-committed/signed), and a soft commit isn't a lock: it carries a
stability score, so a commitment bought purely with money is deliberately
flighty and can be poached, while one built on real relationship and fit is
nearly unbreakable. Decommits are never random. They're always triggered by
a visible cause, like a coaching change or a broken promise, so every twist
in a recruiting battle has a story behind it. As with rival interest
generally, you never see the literal lean number, only qualitative signals
(who's rising, who's fading, what's moving him), because seeing the exact
number would turn recruiting into spreadsheet-gaming instead of a read on a
relationship.

### Promises, grievances, and a coach's credibility

Recruiting isn't only money. Every promise you make (to a recruit, to a
portal entrant, to a player you talked into staying) goes onto a **promise
ledger** the moment it's filed, and it stays there for the rest of the
dynasty. Playing time, a starting role, an NIL commitment, "I'm not going
anywhere": all of it is on the record, yours and the CPU's alike.

Promises get **graded** at season end as kept, partial, or broken, and the
cost of breaking one deliberately does *not* land on the recruit who was
promised. It lands on **your coach's credibility**, a single figure that
starts clean and only moves when a promise is actually graded. Tell a kid
he'll start, bury him on the depth chart, and the damage isn't one angry
player; it's that your word is worth less to the *next* kid. Taking a new
job while you've told your roster you're staying is the same trade in a
bigger form.

On the player's side, a broken or voided promise leaves a **grievance**.
Grievances feed the transfer portal's read on who's likely to leave and who
follows a coach out the door, and they fade after a while rather than
haunting a player forever.

The tool will tell you when a promise isn't backed by the actual outlook
(you're promising early playing time the depth chart doesn't support, for
instance), and then it will let you make it anyway. That's the point:
over-promising is a real recruiting tactic with a real, delayed bill, and
the tool's job is to make the bill visible, not to stop you.

*(Automatic grading is only partly built so far: the "I'm not going
anywhere" promise verifies itself the moment you take another job, while
playing-time and NIL promises currently sit open on the ledger rather than
being auto-graded.)*

### Transfer Portal

A fully simulated portal window (entrants, competing bids from CPU
programs, day-by-day decisions on realistic personality-driven timers) that
writes the resulting roster moves back into your save when it closes.
Displaced starters cascade back into the portal on later days as their spots
fill elsewhere, and every day gets a wire report narrating your program's
departures and offers.

### NIL & Budget

The **Budget** screen is your program's real financial dashboard: one annual
NIL pool (bigger for blue-bloods, leaner for Group-of-5 programs) that has to
cover your current roster's pay, new recruiting deals, and retention raises
all at once. It tracks your committed spend, what's "at risk" in open
offers, true remaining headroom, and a multi-year outlook for next year's
roster cost rolling in. You're allowed to over-offer past your real capacity
(that's how recruiting actually works: more offers than open spots), but the
moment a recruit tries to commit on a deal that no longer fits your money,
that offer auto-collapses and he almost certainly walks. The cost of
over-promising lands visibly, at the worst moment.

NIL money is priced the way real recruiting markets actually work:
**perception** prices recruits (a kid's ask follows his public ranking,
since that's what agents and the market actually see, not his hidden true
talent), while production and performance price veterans and portal players.
Every player has a hidden personality (how money-motivated he is, how much
he inflates his opening ask, some natural noise), so no two equally-ranked
players negotiate identically. Programs bid according to a tiered budget
system: elite programs open near market value expecting a bidding war;
smaller programs open lower and have to sell playing time and fit instead,
with a real budget ceiling, not just taste. A rare "generational talent"
whose perception and substance both agree gets an anchored mega-deal instead
of a formula-derived number. All of it is real dollars, not an abstract
points system, because a real budget is a real-world fact the game engine
doesn't model on its own.

Before the portal opens each year there's a dedicated **Retention phase**:
every rostered player is flagged as a flight risk, underpaid (his market
value has outgrown his contract), or safely settled, and you can offer a
raise to keep him, or let him walk, which is a one-way move once you do it.
A decline is final: no re-asking with a sweeter number.

### Coaching

**Coach Legacy** gives your coaching career a single lifetime score, a
season-by-season trajectory chart, and plots it directly against the
greatest college coaches of all time: real historical legends (sourced and
verified, from Bear Bryant to Nick Saban) and every other coach in your
current save. The score is built entirely from things you can verify and
compare fairly across eras (championships, wins, win percentage, bowl/
playoff runs, awards, longevity), deliberately leaving out any
"overachieved for your program's resources" bonus, since that can't be
fairly sourced for coaches from the 1950s. The point is a concrete,
non-vibes answer to "am I actually good at this": seeing exactly where your
career-year-8 stacks up against Saban's career-year-8, on the same chart.

**Coaching Carousel** *(most of this is built; understanding and surfacing
CPU firings/retirements is the piece still being finished)* is the
league-wide market for coaching jobs: who gets fired, who retires, who gets
poached by the NFL, and who moves where across the whole league, with your
own climb up the coaching ladder as the centerpiece. Every CPU coach has a
stable personality (ambitious vs. content, loyal vs. mercenary, risk-taking
vs. safe, program-builder vs. maintainer), so the carousel is predictable in
character but surprising in outcome. An Alabama coach almost never leaves,
a hot young Group-of-5 coach bolts the moment a Power job calls, and you can
generally read who's a flight risk without it feeling scripted. You can
maintain your own blacklist of jobs/coaches you'd never accept or hire, and
the league enforces its own natural no-go pairings too. Your own coach is
the one truly live agent in the simulation: a great season at a mediocre
program spikes your market value and can trigger real offers, but a bad one
can put you on the hot seat and get you fired for real.

### Data Safety: the Vault

Your dynasty is really two linked files: the game save itself, and Dynasty
Engine's own side-database, which holds everything the game doesn't track
(relationship/influence numbers, contracts, promises, scouting reports,
portal history). Because that tool-side memory can't be rebuilt from the
save alone, the app automatically takes a paired checkpoint (a snapshot of
both files together) before any risky moment: before it writes anything
back to your save, at the start of each new season, and before every manual
restore. The **Vault** screen is where you roll back to one of these
checkpoints if something goes wrong, and restoring always puts both halves
back together as a matched pair, so the tool's memory and the game world
never fall out of sync.

This is deliberately coarse, on purpose: Dynasty Engine won't let you undo a
single decision (a declined retention offer or a broken promise stays real;
consequences are what make the choices matter). The Vault only ever rewinds
the *entire world* to a specific saved moment, never cherry-picks history.

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

Dynasty Engine is being built in phases, roughly by system:

1. **Recruiting core (current focus):** scouting, the board, offers,
   commitments, the transfer portal, NIL, and the read-only data (awards,
   stats, prior-season results) the portal's own logic depends on.
2. **Coaches:** the full coaching carousel described above, a career
   ledger, staff management, and reworking the in-game coach talent trees so
   their perks actually do something meaningful through the tool.
3. **Program intelligence:** an Almanac (champions, awards, draft history),
   Insights (recruiting hit-rate and development analytics), and
   simulated-world events (injuries, suspensions, booster swings, alumni
   donations after a big season) that give a dynasty more texture over time.
4. **Program systems:** further out, facilities and equipment/identity, the
   longer-horizon program-building layer.

Each phase builds on the last; recruiting has to be solid before coaching
carousel realism matters, and both need to exist before program-wide
intelligence is worth building on top of them.

### Possible direction: real-world roster economics

College football's actual rules are moving toward something the game doesn't
model at all. Schools now pay players directly out of a capped pool,
third-party NIL is a separate number that gets scrutinized on its own, and
the pressure on transfer rules is toward tightening them rather than
loosening them further. There's a real chance Dynasty Engine ends up modeling
that shape instead of the current one.

What that would mean concretely:

- **A school-paid salary cap as the primary constraint.** A hard, league-wide
  per-program limit on direct player compensation, the same number for
  everyone, replacing today's prestige-scaled NIL pool where blue-bloods
  simply have more money to spend.
- **NIL as a separate number on top.** True third-party endorsement money
  would sit outside the cap and be tracked independently, so a program's
  total appeal becomes cap space plus market. A big-brand school in a big
  city can offer outside earnings a directional school can't, without that
  collapsing into "they just have a bigger budget."
- **Transfer limits.** Restrictions on how often and when a player can move,
  instead of today's effectively unlimited movement. Roster construction
  becomes a multi-year commitment rather than an annual reset.
- **Contracts as real objects.** Every player carries a term and a status, so
  retention turns into renegotiation: extending early, eating a bad year,
  deciding who to re-sign before the market re-prices him.
- **Recruiting priced against all of it.** What you can offer a recruit would
  be bounded by your cap space, your existing commitments, and the contract
  years already on your books, not by a standalone recruiting budget.

This is **not decided and not scheduled**. It's a direction under serious
consideration, and it would touch nearly every system described above.
Whether it makes a dynasty more interesting or just adds paperwork is exactly
the kind of thing worth arguing about now, before any of it is built.

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
