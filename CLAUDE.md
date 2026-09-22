# SLOWBOT_LEAGUE

Scoping-only repo, no code yet. Read [`NORTHSTAR.md`](NORTHSTAR.md) before doing any work here —
it names what's real to reuse from SHANKPIT/DEADWEIGHT/IDUNA, what's genuinely new, and a phased
plan. Three open questions are named at its end; do not guess past them (especially the
lives-assignment direction in item 3 of "Real, genuinely new work") without checking with the
founder first.

Follow the root `/home/fatbaby/CLAUDE.md`'s "The Emily Way" protocol (backlog-first, Apple before
mark-done, changelog, commit format) same as every other repo in the monorepo.

## Related repos

- `SHANKPIT` — the engine and live queue server this spins off from; `scripts/rl_league.py` is
  the real PFSP+Elo library this repo should reuse, not reinvent.
- `IDUNA` — `internal/games/games.go`'s `Registry` is the real per-game tenant mechanism this
  repo's own IDUNA integration should add a row to, not a new subsystem.
- `DEADWEIGHT` — the real precedent for guest auth / Claim Account / daily-cap ticket economy,
  all already generic over `game` server-side; this repo's own client integration should mirror
  it, not fork it.
- `WOTAN` — where this league's stats/leaderboard need to land (Phase 3 of NORTHSTAR.md);
  no leaderboard-section pattern exists there yet for any game, including DEADWEIGHT.
