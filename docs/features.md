# Features

← Back to [README](../README.md) · [Install](install.md) ·
[Screens](screens.md) · [Roadmap](roadmap.md)

This is the depth page: what each system does and why it works that way. Status
notes are inline, in italics, next to the system they apply to, so they cannot
quietly go stale in a separate list.

> **Barely alpha. Do not start a real dynasty in this tool yet.** Read the
> warning at the top of the
> [README](../README.md#read-this-before-you-download-anything). Descriptions
> below cover intent and mechanics; almost none of the numbers behind them are
> balance-tuned.

Everything here assumes [the weekly
loop](../README.md#how-you-actually-use-it-the-weekly-loop): you open the tool
at the start of each week, and it owns the front office while the game owns the
football.

## Contents

- [Recruiting: Prospects, Board, and reading a recruit honestly](#recruiting-prospects-board-and-reading-a-recruit-honestly)
- [Scouting: finding value the rankings don't show](#scouting-finding-value-the-rankings-dont-show)
- [Commitments: how a recruit actually decides](#commitments-how-a-recruit-actually-decides)
- [An invisible hand keeps the CPU honest](#an-invisible-hand-keeps-the-cpu-honest)
- [Promises, grievances, and a coach's credibility](#promises-grievances-and-a-coachs-credibility)
- [Transfer Portal](#transfer-portal)
- [NIL & Budget](#nil--budget)
- [Coaching](#coaching)
- [Player development: how a roster actually grows](#player-development-how-a-roster-actually-grows)
- [Data Safety: the Vault](#data-safety-the-vault)

### Recruiting: Prospects, Board, and reading a recruit honestly

**Prospects** is the full high school / JUCO / portal pool pulled straight
from your save: stars, per-stat scouting grades, recruitment interest, an
estimated NIL range, and a detail view for every player. Recruits are read
through **letter-grade bands** (like "B-/B") instead of a hard number, and
that's deliberate: the uncertainty represents projection, not incomplete
scouting. Even the tightest band is still an evaluation, never "the truth."
Only actual rostered or portal players ever show a real overall rating.

**Board** is where you sort recruits into Priority / Target / Interest tiers,
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

The **Departures Desk** is the end-of-season screen where everyone leaving your
program gets handled in one place: graduating seniors, who declares early for
the NFL draft, and who enters the portal. The design behind it moves portal and
draft entry out of the tool's own bookkeeping and into the game's own Players
Leaving phase, so an entrant becomes a real, in-game-visible portal player
rather than a record only Dynasty Engine knows about, while the tool keeps full
control over who leaves and where they land. *(The screen is live and computes
a full preview, but the "File the departures" button is deliberately disabled:
the feasibility test proving that write is safe has not passed yet, so nothing
on that screen touches your save. Treat it as a preview of where the portal is
going.)*

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

The **Coaching Carousel** is the league-wide market for coaching jobs: who
moves where across all ~134 programs, with your own climb up the ladder as the
centerpiece. It reads the game's real carousel out of your save (every opening,
every candidate, each with his prestige grade, tenure, last-year record, and a
**Fired** tag if he's out of a job), and then replaces the game's own judgment
about who lands where with a model of its own.

**That model exists because the game's version was measured and found
wanting.** The game's real coach-hiring math was decoded and regressed across
865 actual offers from 15 saves. Two findings drove the rebuild. First, the
game **rigs the market in the user's favor**: a user coach's interest score
gets inflated to levels no CPU coach ever reaches, so a D-grade user coach
ranks ahead of an A+ coach for the same job. Dynasty Engine removes that bonus
outright. You get ranked on the same scale as everyone else, and if you aren't
good enough for a job yet, the board says so. Second, the game rates coaches on
**absolute wins**, which quietly punishes anyone building at a hard program;
the tool rates you on wins against what your program should have done, with
scheme fit as the tiebreak.

**Who moves, and who doesn't:**

- **Good coaches are genuinely sticky.** Tenure puts down roots (far more for a
  head coach than a coordinator), and a successful coach at an elite program is
  effectively locked in place. An A+ coach at a powerhouse won't read as
  willing to take a lateral move. Let that same elite coach start losing and
  the lock breaks, so hot seats still cascade the way they should.
- **Fired elites take a year off and come back on top.** A big-name coach who
  loses his job anchors on his career stature, not on the smoking hole he just
  left, so he turns down work beneath him. The unhired year is the year in
  broadcasting, and he then gets injected back into the running for a job at
  his actual level rather than quietly disappearing from the league.
- **The hot coach leaps.** Multi-year overperformance at a modest program (the
  Bowling Green to Utah arc) builds real momentum and can produce a fast jump
  up several rungs.

**Your own climb** is the live part. **Your Standing** shows where your coach
ranks for every opening in the country, by the same model that ranks everyone
else, with a read on whether you'd even be wanted and whether the fit works.
You can **express interest** in jobs, including your own school's head-coaching
job when you're a coordinator, which the game itself blocks a human from being
considered for even though it lets CPU coordinators get promoted. The **Chain**
view projects the cascade: each team's leading candidate takes the job he most
prefers among those where he leads, which frees the rest, which reshuffles
everything downstream. It re-runs live as you edit, and it's labelled as a
model of the resolution, never a guarantee.

You can also edit the board directly: adjust a candidate's interest, reorder
him, or replace him outright from a searchable pool of every coach in the save.

*(Built and verified against real saves. Two honest caveats. **Vacancy
generation is the missing piece**: openings currently come from the game's own
carousel, so who gets fired, who retires, and who leaves for the NFL is still
the game's call, not yours, and surfacing and letting you intervene in that is
the next piece of work. And the write path has **not been validated in-game
yet**: the tool writes a carousel result your save reads back correctly, but
"reads back correctly" is not the same as "the game accepts it," so treat
running it as experimental and lean on the Vault.)*

You also hold a **blacklist** the carousel enforces every time it recomputes:
pick a coach/team pairing and decide whether the team will never make the
offer, the coach will never take it, or neither happens at all, and whether
that holds permanently or only while the coach keeps his current job (a
rivalry grudge that lifts the moment he's actually fired, versus a burned
bridge that never does). It ships with 18 real-world contentious pairings,
every one of them verified to be a coach who actually exists in the game;
delete any you disagree with and they stay gone. The league enforces its own
natural no-go pairings on top of whatever you add.

**Taking a new job** is its own handled event rather than a save edit that
teleports you. When you accept, the ledger at your old school closes out: your
promises there get settled, and the players you walked away from remember it.
You arrive with a board built from your new program's situation, not your old
one's. A one-time **Transition Window** opens, during which the roster you
inherited and the recruits you left behind both get to react: recruits who
committed to *you* can be reaffirmed or walk, and a Stay Promise you made and
then broke by leaving grades itself immediately against your credibility. Your
old school's colors and crest stay on the app through that window, because a
staff doesn't change its jersey the day the contract is signed.

**Coach perks** had to be rebuilt to mean anything under this mod, because the
game's own talent trees are built around in-game recruiting and scouting actions
the tool turns off. You still spend coach XP in the game's own talent trees,
exactly as you always did. What changed is what those nodes buy.

Every node worth anything now feeds **one of the six staff axes below**, across
all eleven of the game's remaining trees, roughly 240 graded slots in total.
Three trees are renamed in-game by the mod so what you are buying reads
correctly under this tool. Two others, the pure on-field scheme trees, keep their
native game effects untouched and quietly contribute points on top. Capstone
nodes are gone, and the free opener node in each tree is worth nothing but coach
XP. Kicker and punter specialist perks, draft-stock perks, "players are just more
likely to stay" perks, and dealbreaker perks are all cut on principle: if a node
is not a lever one of this tool's real systems reads, it does not get points.

Every CPU staff in the league is read the same way under the same rules, so rival
staffs get real, felt advantages too. This is not a bonus that only your program
gets.

**Staff Grades** turns all of that into one readable report card. Every FBS
staff in your save, yours and every rival's, is scored on **six axes**, each one
a plain statement of what that staff is actually good at:

| Axis | What a good grade means |
|---|---|
| **Evaluation** | Sharper scouting reads: tighter rating bands and more trustworthy gem calls |
| **Salesmanship** | Recruits and portal targets warm to your program faster |
| **Closing** | Stronger pitches in the moments that decide a commitment, and fewer late flips on recruits leaning your way |
| **Retention** | Your own players are less tempted by the transfer portal |
| **Market** | Sharper reads on what it actually takes in NIL money to sign or keep a player |
| **Development** | Your players grow faster and more reliably |

Each axis score is built from the coach talent nodes that staff actually owns,
pooled across all three coaches and weighted by role: a head coach counts
program-wide, a coordinator counts fully on his own side of the ball and half
off it. That score is then **ranked against every other staff in the league**
and turned into a letter on the same 13-step F to A+ ladder the game already
uses for coach prestige, in equal percentile bands. The league table is public
and sortable, so you can see exactly which programs out-recruit, out-develop, or
out-negotiate you. Raw point totals stay internal; only the letter and its tier
are ever shown.

Grading on the curve instead of against a fixed scale has two deliberate
consequences. **A C is exactly neutral**, and the full span from F to A+ is a
narrow real effect, so a great staff is a genuine edge and never a cheat code.
And **league-wide inflation moves nobody**: if every staff in the country buys
the same perks, every grade stays where it was. There is no power creep to
out-run over a twenty-season dynasty.

The grades are not cosmetic. Each axis is wired into the system it names, so a
better Closing grade genuinely closes more recruits, and a better Development
grade genuinely feeds the progression pass below.

*(Built and wired, for your staff and every CPU staff alike. Not yet calibrated:
how hard each axis pushes its system is a first-pass number, and two axes may
still merge if they prove to move together too closely.)*

The standout mechanic is the **hunch**: the one sanctioned piece of
development-trait information anywhere in the tool. A hunch is a staff
suspicion, never a fact, that a player might (or might notably might not)
turn into more than his ratings suggest. It's probabilistic, deliberately
capped to stay rare, and can simply be wrong with no warning. Perk
investment makes hunches fire more often and trust them more, but never
turns one into certainty. It's meant to feel like a scout's gut, not a
hidden stat revealed early. A better Evaluation grade is what makes hunches fire
more often and read more reliably.

### Player development: how a roster actually grows

*(Built and shipping in 0.098: the engine, the save write, and the Training
Results desk are all live and unit-tested. Two honest caveats. It is **not
calibrated**, so the constants below are first-pass shape decisions and the
long-run simulation meant to fit them has not been run. And it has **not been
verified across a real in-game season yet**, only in tests. Expect the numbers
to move, and take a Vault checkpoint before you run the pass.)*

Player growth is Dynasty Engine's, not the game's. The mod suppresses in-game
player XP so development isn't being decided in two places at once, and the
tool runs one **annual progression pass** at the Training Results stage of the
offseason. There is no in-season progression: you run it once a year, it shows
you what happened, and it writes the new attributes into your save.

**Every player is measured against a real, measured baseline.** Before any of
this was built, the entire base CFB27 roster was measured: every position, at
every class year, attribute by attribute. That measurement is the anchor. When
a player grows, the tool isn't applying a made-up curve to him. It's deciding
where he now sits among every player at his position and class year nationally,
then reading his actual attributes off the real measured distribution for that
spot.

**Growth is relative, and that is a deliberate choice.** Because everyone is
ranked against everyone else, the league's overall talent shape holds exactly,
every season, forever. It cannot quietly deflate (the base game's own failure
mode) or inflate after 20 seasons. The tradeoff is real and worth stating
plainly: **coaching does not mint new talent, it captures a bigger share of a
fixed pool.** A program that genuinely out-develops the league climbs at other
programs' expense. "Everyone develops great players at once" is impossible by
design. That is arguably the honest version of how relative rating scales
actually work, but it is a choice, and it is the kind of thing worth arguing
about.

**What moves a player**, in order of how much it matters:

1. **His development trait**, by a wide margin. It is the dominant force, and
   it's calibrated so the gap between a Normal and an Elite player at his
   senior year reproduces the gap actually measured on real rosters.
2. **His environment**, worth roughly half a development tier over a career.
   This is his staff and his program, scored league-wide and ranked, so it's
   relative too: if every staff in the country buys the same perks, nobody
   moves. Coaching sharpens talent. It never comes close to substituting for
   it.
3. **Luck**, a real but bounded amount of year-to-year noise.

On top of that sit rare **shock events**: a genuine breakout that jumps a
player several rungs at once, and a much rarer, much milder stall. Normal-trait
players keep a real chance at a breakout, and high-trait players occasionally
have a flat year, so a development read is always odds and never a solved
equation.

**Playing time is deliberately a minor input.** Meaningful snaps add a small
edge to the mental side of the game only, and **sitting never costs you
anything**. A backup buried behind a star at a great program develops at full
strength, and a bad team's starter gets no credit merely for playing. Playing
time keeps its full weight where it belongs, as a reason a player enters the
transfer portal. The well-developed backup who wants out is the story that
split is meant to produce.

**Nobody ever gets worse.** Attribute regression does not exist in college
here: seniors graduate, so aging is out of scope. The worst season a player can
have is a season where he grows *less* than he should have, and Training
Results says so honestly rather than hiding it.

**Physical tools move slowly, not never.** The measurement is unambiguous that
awareness, recognition, and technique carry almost all of a player's FR to SR
climb, while speed and strength are close to flat. But close to flat is not
frozen: every attribute moves at its own measured pace, so a freshman can still
get physically better, just slowly, and mostly early.

**Position decides how good you are; archetype decides what good looks like on
you.** Two equally-developed players at the same position are equally good and
can look completely different, because the archetype governs which attributes
carry his rating.

**Development traits are observed, never authored.** The game awards trait
changes. Dynasty Engine never writes one. It records what each player's trait
was on the last pass, compares it to the save, and reports any difference as a
promotion or demotion on Training Results. Whatever the game did is what you
see.

**The ladder itself is invisible on purpose.** You will never see a percentile,
a rung, or a velocity number anywhere in the app. Training Results reports
outcomes and stories: who broke out, who stalled, what each position group did,
and a plain-language check that this year's ratings still look like a real
football roster. Every season's results are archived and browsable by year.

**Year-One Breakouts** is an optional, one-time pass on the first preseason
checklist of a new dynasty. It picks roughly a hundred players league-wide to
become preseason breakout stars, weighted toward younger players and better
development traits but with small schools at identical odds to blue-bloods, so
a fresh dynasty starts diverging from the known base roster on day one instead
of being a world everyone has already memorized. It's off by default and runs
once.

*(Not built yet: the deliberate headroom at the very top of the ratings scale
for players who would in reality have already left early for the NFL, and
players whose archetype naturally shifts as they develop.)*

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
