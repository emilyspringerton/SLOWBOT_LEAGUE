# SLOWBOT_LEAGUE

A SHANKPIT spin-off: an Elo-ranked, lives-based ("last player standing" per round, not
continuous-respawn) league mode where humans play against — and train — a persistent-forever
Player-vs-Fictitious-Self-Play (PFSP) bot pool, seeded from SHANKPIT's own live, currently-active
training checkpoint.

**Status: NORTHSTAR only, no code yet.** See [`NORTHSTAR.md`](NORTHSTAR.md) for the full scoping
pass — a real audit of what already exists to reuse (IDUNA's per-game tenant system, guest-auth/
Claim Account, the `rl_league.py` PFSP+Elo library, the live active-checkpoint anchor) versus
what's genuinely new (a lives-based SHANKPIT server game mode, a separate server process, a WOTAN
leaderboard pattern that doesn't exist for anyone yet, and this repo's own training script) — and
a phased build plan. Three open questions for the founder are named at the bottom of that doc,
including one real ambiguity in the lives-assignment rule as specified.

This repo is provisionally named and local-only (no GitHub upstream yet).
