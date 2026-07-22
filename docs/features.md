# Features

← Back to [README](../README.md)

## Contents

- [Recruiting: Prospects, Board, and reading a recruit honestly](#recruiting-prospects-board-and-reading-a-recruit-honestly)
- [Scouting: finding value the rankings don't show](#scouting-finding-value-the-rankings-dont-show)
- [Commitments: how a recruit actually decides](#commitments-how-a-recruit-actually-decides)
- [An invisible hand keeps the CPU honest](#an-invisible-hand-keeps-the-cpu-honest)
- [Promises, grievances, and a coach's credibility](#promises-grievances-and-a-coachs-credibility)
- [Transfer Portal](#transfer-portal)
- [NIL & Budget](#nil--budget)
- [Coaching](#coaching)
- [Data Safety: the Vault](#data-safety-the-vault)

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

### An invisible hand keeps the CPU honest

Rival interest runs its own quiet simulation underneath everything above:
offers land, interest surges, official visits happen, and recruits soft- and
hard-commit on their own schedule over the course of a season, the same way
a real recruiting cycle breathes rather than resolving in one shot at
Signing Day. That's most of what you're actually reading on the Pulse wire.

Sitting on top of that is a self-correcting layer that keeps a long dynasty's
CPU league from looking robotic. If a small program is inexplicably hoarding
blue-chip signees year after year, the market cools on them; if a genuine
blue blood is whiffing on recruits at its own level, interest heats back up
for it. It's the same corrector watching every program, not a thumb on the
scale for or against you specifically.

If your own class is stacking unusually far above what your program's
actual level would support, the tool doesn't take a recruit away from you or
block anything. It just makes the fight a little more honest: a rival's
interest in your best remaining target heats up, or your shakiest soft
commit starts fielding harder questions about why he picked you. Nothing
already locked in gets reversed, and no real lead you've built ever gets
erased by dice. It only ever adds pressure to a race that already exists,
never invents one out of nothing.

*(A quieter cleanup pass, the kind that force-places stragglers and
rebalances lopsided CPU classes at the end of a cycle, is designed but not
built yet.)*

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
generally read who's a flight risk without it feeling scripted. Your own
coach is the one truly live agent in the simulation: a great season at a
mediocre program spikes your market value and can trigger real offers, but
a bad one can put you on the hot seat and get you fired for real.

You also hold a **blacklist** the carousel enforces every time it recomputes:
pick a coach/team pairing and decide whether the team will never make the
offer, the coach will never take it, or neither happens at all, and whether
that holds permanently or only while the coach keeps his current job (a
rivalry grudge that lifts the moment he's actually fired, versus a burned
bridge that never does). It ships pre-loaded with a handful of real-world
contentious-exit pairings; delete any you disagree with and they stay gone.
The league enforces its own natural no-go pairings on top of whatever you
add.

**Coach perks**, rebuilt from scratch to matter under this mod, since the
game's own talent trees are built around in-game recruiting/scouting actions
this tool turns off. Three new trees ride the native talent-tree slots the
mod frees up (renamed in-game so what you're buying reads correctly), each
tied to a currency this tool actually spends: relationship influence,
staff attention, NIL negotiation leverage, and portal intel. Every CPU coach
in the league draws from the same trees under the same rules, so the AI's
staffs get real, felt advantages too, not a static number only your program
benefits from.

The standout mechanic is the **hunch**: the one sanctioned piece of
development-trait information anywhere in the tool. A hunch is a staff
suspicion, never a fact, that a player might (or might notably might not)
turn into more than his ratings suggest. It's probabilistic, deliberately
capped to stay rare, and can simply be wrong with no warning. Perk
investment makes hunches fire more often and trust them more, but never
turns one into certainty. It's meant to feel like a scout's gut, not a
hidden stat revealed early.

Kicker/punter perks, draft-stock perks, "players are just more likely to
stay" perks, and dealbreaker perks are all cut on principle. If it isn't a
lever one of this tool's real systems reads, it doesn't make the cut.

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
