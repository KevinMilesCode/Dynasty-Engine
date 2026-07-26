# Roadmap

← Back to [README](../README.md) · [Features](features.md) ·
[Install](install.md)

Nothing on this page is a delivery date. The current build (0.098) is barely
alpha, and the whole point of releasing it is to get feedback before the tuning
and refinement work starts. The "possible direction" section at the bottom is
exactly the kind of thing worth arguing about now: use **Request Feature** in
the app, or [Discussions](../../../discussions).

Dynasty Engine is being built in phases, roughly by system:

1. **Recruiting core (current focus):** scouting, the board, offers,
   commitments, the transfer portal, NIL, and the read-only data (awards,
   stats, prior-season results) the portal's own logic depends on.
2. **Coaches:** most of this has moved ahead of schedule. The
   [coaching carousel](features.md#coaching) is built, including the hiring
   model, your own standing in the market, the cascade projection, and the
   career ledger; what's left there is generating vacancies ourselves (who
   gets fired and who retires is still the game's call) and validating the
   write in-game. The rework of the in-game coach talent trees, so their
   perks actually do something meaningful through the tool, is built too: it
   became the six-axis Staff Grades system, and what remains there is
   calibration. Staff management beyond the head coach is still ahead.
3. **Program intelligence:** an Almanac (champions, awards, draft history),
   Insights (recruiting hit-rate and development analytics), and
   simulated-world events (injuries, suspensions, booster swings, alumni
   donations after a big season) that give a dynasty more texture over time.
4. **Program systems:** further out, facilities and equipment/identity, the
   longer-horizon program-building layer.

Each phase builds on the last; recruiting has to be solid before coaching
carousel realism matters, and both need to exist before program-wide
intelligence is worth building on top of them.

## Built since this page last said otherwise: player progression

Player progression used to be listed here as a possible direction. It is
now decided, built, and shipping in 0.098, so it has moved to
[Features](features.md#player-development-how-a-roster-actually-grows).
Short version: growth is relative to a measured baseline of the real base
roster, position by position and class year by class year, driven mostly by
development trait, then by the quality of the staff and program, then by
luck. It is not calibrated yet, which is exactly the sort of thing feedback
helps with.

Two pieces of it are still open: deliberate headroom at the very top of the
ratings scale for players who would in reality have left early for the NFL,
and players whose archetype naturally shifts as they develop.

## Possible direction: real-world roster economics

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
