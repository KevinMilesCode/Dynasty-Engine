# Roadmap

← Back to [README](../README.md)

Dynasty Engine is being built in phases, roughly by system:

1. **Recruiting core (current focus):** scouting, the board, offers,
   commitments, the transfer portal, NIL, and the read-only data (awards,
   stats, prior-season results) the portal's own logic depends on.
2. **Coaches:** the full coaching carousel described in
   [Features](features.md#coaching), a career ledger, staff management, and
   reworking the in-game coach talent trees so their perks actually do
   something meaningful through the tool.
3. **Program intelligence:** an Almanac (champions, awards, draft history),
   Insights (recruiting hit-rate and development analytics), and
   simulated-world events (injuries, suspensions, booster swings, alumni
   donations after a big season) that give a dynasty more texture over time.
4. **Program systems:** further out, facilities and equipment/identity, the
   longer-horizon program-building layer.

Each phase builds on the last; recruiting has to be solid before coaching
carousel realism matters, and both need to exist before program-wide
intelligence is worth building on top of them.

## Possible direction: player progression

Right now the Training Results screen is an honest placeholder: a season's
worth of player growth isn't modeled yet. The system under active design
works something like this: instead of aging every player by a fixed
formula, each player at every position is measured against where real
recruits and rostered players from actual base-game rosters land, position
by position, class year by class year. A player's growth each season is
really a move up or down that real-world scale, driven by his development
trait, the strength of his coaching staff, and how much he's actually
played, with some year-to-year randomness on top.

The point of building it this way is that the league's overall talent shape
holds up over a long dynasty, the way a real conference does, instead of
quietly drifting flatter (or wildly overinflated) after 20 simulated
seasons. A program with genuinely good player development doesn't
manufacture new talent out of nowhere; it wins a bigger share of a talent
pool that stays the same size league-wide, closer to how real recruiting
and development plays out relative to rivals. Physical tools (speed,
strength) mostly stay put once a player arrives on campus; what actually
improves year to year is largely the mental/technical side of the game
(awareness, recognition, technique).

This is proposed, not decided or built. If it ships, it also has to hold
deliberate room open at the top of the ratings scale for players who would,
in reality, have already left early for the NFL, so the pool doesn't get
quietly capped by the players who are no longer in it.

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
