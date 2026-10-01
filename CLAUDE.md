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

## Core Deps Are PARENA-First (standing, monorepo-wide)

Founder real-time, 2026-10-01: *"always implement core deps in PARENA — when core deps are missing
always implement the core deps in PARENA first."*

- **When a core dependency is missing** (a codec, a protocol client, an inference engine, a
  parser, a data structure — anything this repo's own functionality stands on), implement it in
  PARENA (`PARENA/stdlib/...`) **first**, before building the feature that needs it. Deps first,
  feature second.
- **If PARENA itself can't express the dep yet**, that gap is the real first task: fix or extend
  PARENA (compiler, emitter, or stdlib), with tests, then build the dep on top. Don't route around it.
- **Third-party tools/binaries are stopgaps, not the answer.** Shelling out to or FFI-binding an
  existing tool is allowed only to unblock a demo, and must be labeled as a stopgap in the code and
  in `EMILY/BACKLOG.md` with a PARENA replacement item. (Example: Piper via subprocess for
  MODE_TYLER TTS, 2026-10-01 — stopgap; the PARENA-native synthesis stack is the real work.)
- **Not a license to reimplement the OS.** Core deps = what the product's own behavior depends on.
  Compilers, kernels, system libraries and the like stay as-is; a repo's own CLAUDE.md may record a
  considered, specific exception (same standard as the LZ4 compression convention).
