# Handoff: build and publish "Palworld: Los Santos" on Melty

Claude Code reads this file automatically. The owner is **Wolf001**. All design questions are already answered; do not ask them again. Technical decisions are yours. Once you start building, ask the owner only for a sign-in or payment only they can do.

## What the owner decided
- A **50-50 mashup**: **Palworld** is the game players play in (loader: UE4SS) and **Grand Theft Auto V** (story mode) is a **required** game.
- **Single window.** Everything happens inside Palworld. GTA V does NOT run beside it.
- **Real GTA content:** cars (Futo, Sultan, Buffalo), characters (Franklin, Michael, Trevor as bosses), the Los Santos map and sound are read **at runtime from the player's own GTA V install**. Nothing from either game is ever copied into the repo or an upload.
- **Multiplayer:** players join a Palworld session. GTA V is never the multiplayer layer. The 120 and 500 player figures are unmeasured targets: test, then set `maxPlayers` to the tested number only.
- **Credits/license:** Wolf001, CC BY 4.0. Remixing allowed, credit required.
- Full system design: `design/mashup_design_sheets.json` (source of truth; change the sheet before the code; every cell is `verified: false` until checked against the game files).

## Known obstacle
Loading GTA V's RPF-archive content (map, models, vehicles, characters, audio) into Unreal at runtime is unproven. Pick a route (runtime reader/converter via UE4SS or a companion tool). If a part turns out impossible, explain exactly why and **get the owner's agreement before changing the design**. Do not swap in stand-ins or drop GTA V silently.

## Current state
Design only. No mod code, build, test, screenshot or Melty draft exists yet. Do not call it playable or one-click until `one_click_check` says yes and a Melty install test passes.

## Task
1. Connect to Melty using the owner's Publish prompt (paste it in the session; the token must never be written to any file, commit or reply). Call `list_my_mods`; reuse a draft only if clearly this project. Use `search_games` and `game_info` for palworld and gta-v to confirm requirements, UE4SS loader and install paths.
2. Install what the work needs from official sources (UE4SS, build tools) and tell the owner what you installed.
3. Build the mod in this repo (e.g. `mod/`), starting with the v1 scope in the sheets: GTA-layout region, pal mounts without saddles, spear catching, 5 stealable GTA vehicles, 3 weapons at an ammu shop, 1 bank, 1 GTA boss, XP cap 300, bases at 3x radius.
4. Multiplayer: run `setup_multiplayer`, add the join/host lines, test host + join with two Palworld copies on this PC, and send both logs.
5. Package, then `inspect_package`, `validate_recipe`, `one_click_check`. Package only the owner's own work (plus licensed third-party libraries with credit). Never upload game content or secrets.
6. `create_mod` (pass `githubRepo` with this repo's URL), `start_upload` / `finish_upload`, `submit_release`. Save the validated recipe as `melty.json` at the repo root and commit it once the owner agrees, so Melty reads setup from GitHub and new releases publish themselves.
7. Capture a real screenshot of this build running (game only, no tokens or private windows) with `add_screenshot` / `finish_screenshot`.
8. `test_release`, play it during the runs, fix what it lists, retest.
9. Show the owner a short summary, then ask whether to publish. Publish only when they say yes.

Draft the listing from the real build (title, tagline, short description). Keep it a draft until a real build, a passing test and a real screenshot exist.
