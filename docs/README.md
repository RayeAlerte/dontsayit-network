# Don't Say It Network — docs

Shared, game-agnostic planning for the Don't Say It Network engine and contracts. Game-specific LPS design notes live in [LastPackStanding/docs](https://github.com/RayeAlerte/LastPackStanding/tree/main/docs). Card generation and Flip live in DontSayBot.

## Contents

| Doc | What it covers |
|---|---|
| [module-architecture.md](module-architecture.md) | Engine, kit, contracts, data ports, clients — reusable modules for networked party games |

LPS-only docs (not copied here):

- [spec-decisions.md](https://github.com/RayeAlerte/LastPackStanding/blob/main/docs/spec-decisions.md) — decision log
- [edge-case-review.md](https://github.com/RayeAlerte/LastPackStanding/blob/main/docs/edge-case-review.md) — edge-case proposals and accepted rules

## Parallel Flip work (DontSayBot)

Flip is developed **in parallel** in DontSayBot (`flip/` + `card-packs/`) as the content path that feeds LPS packs. It does not use this network engine; it shares the X3 card-set shape only.

Pack schema changes for that path:

- **`schemaVersion`** — required on each pack (`major.minor`), defined by DontSayBot
- **`adult`** — boolean on the pack and on each card; **default `false`** when missing (18+ is an age filter, not a claim that content is explicit)
- **Packs as JSON** under DontSayBot `card-packs/`
- **`card-packs/index.json`** — Flip's pack list / load index

## Closed scoring note

Ghost Trap credit stays on the non-point `ghostCatches` track. That ruling is closed; do not reopen it in this repo.
