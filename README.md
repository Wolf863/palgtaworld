# Palworld: Los Santos (working title)

A 50-50 mashup of **Palworld** (the window you play in, via UE4SS) and **Grand Theft Auto V** (story mode install, required).

**Status: design only.** Nothing is built, tested or published. There is no playable download yet.

## Idea
A Palworld world laid out like Los Santos. Ride any pal you catch with a spear, steal GTA cars, rob shops and banks, and fight Franklin, Michael and Trevor as bosses. Players join a Palworld multiplayer session.

## Required games
- **Palworld** (host)
- **Grand Theft Auto V** (story mode install). Cars, characters, map and sound are meant to be read from the player's own copy.

## Rules
- Everything is played in the Palworld window. GTA V does not run beside it.
- Nothing from either game is copied into this repo or any upload. Every player brings their own copies.
- GTA V is never the multiplayer layer; players join the Palworld session.
- Player counts (120 in world, 500 supported) are targets, not promises. No `maxPlayers` is set until measured.

## Building it
This repo is the design plus a handoff for Claude Code (`CLAUDE.md`). Open the repo in Claude Code on a PC with Palworld and GTA V installed, paste your Melty Publish prompt, and it builds, tests and publishes the mod. There is no `melty.json` yet because a recipe can't be validated until a build exists.

## Layout
- `CLAUDE.md`: handoff instructions for Claude Code.
- `design/mashup_design_sheets.json`: source of truth for every system. Change the sheet before the code.
- `LICENSE`: CC BY 4.0 notice for the original work in this repo.

## Open items
- Prove a runtime route for reading GTA V content into Palworld; if a part is impossible, agree a design change first.
- Verify every sheet cell against the game files (all `verified: false`).
- Build, then test hosting and joining with two Palworld copies.
- Publish on Melty (https://melty.gg) once a build, a passing test and a real screenshot exist.

## Credits and license
By **Wolf001**. Remixing is allowed with credit, under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See `LICENSE`.
Palworld and Grand Theft Auto V belong to their respective owners; this project is unofficial and ships none of their content.
