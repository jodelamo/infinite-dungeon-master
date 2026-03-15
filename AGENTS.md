# Project D20 — Agent Instructions

This is a zero-code, AI-driven tabletop RPG. No build system, no tests, no application code — only markdown rules and JSON game state.

See @RULES.md for the core game mechanics (dice, attributes, combat, skills, leveling, display formatting). Read it at the start of every session.

## Architecture

- `RULES.md` — Core rules engine. Contains dice, attributes, skills, combat, XP, currency, DCs, display formatting, and GM style guidelines.
- `rules/` — Detailed reference files loaded on demand:
  - `rules/races.md` — 9 playable races with subraces and traits
  - `rules/classes.md` — 12 classes with features (levels 1–10)
  - `rules/spellcasting.md` — Spell slot tables (full caster, half-caster, Pact Magic)
  - `rules/state-formats.md` — Character sheet and campaign state JSON schemas
- `.agents/skills/*/SKILL.md` — Skill files for specific GM procedures (`/combat`, `/explore`, etc.). Each defines a step-by-step workflow. Symlinked from `.github/skills/` for GitHub Copilot compatibility.
- `characters/*.json` — Character sheets. Schema defined in `rules/state-formats.md`.
- `campaigns/*.json` — World state (locations, factions, NPCs, quests, time). Schema defined in `rules/state-formats.md`.

## Display Formatting

Before rendering any game output (character sheets, inventory, loot, shop transactions, scene banners, status footers), always consult [`RULES.md` § "Display Formatting"](RULES.md#display-formatting--icons--items) for the required icon and formatting conventions.

Key rules:
- All items must be prefixed with their category icon (see [`RULES.md` § "Item Icons by Category"](RULES.md#item-icons-by-category))
- Gold uses the 🪙 icon with bold amounts
- Magical items are prefixed with ✨ before their category icon
- Scene banners and status footers have specific formats defined in `RULES.md`

## Character Sheets

When displaying a character sheet, load the `create-character` skill for the ASCII character sheet template. Render equipment items with their category icons from `RULES.md`.

## State Files

- Character data: `characters/{name-slug}.json` (schema in `rules/state-formats.md`)
- Campaign data: `campaigns/{campaign-slug}.json` (schema in `rules/state-formats.md`)
- Icons are a display-layer convention only — never store them in JSON state files
- Always read a JSON file before modifying it
- Update both character and campaign files after combat, rest, shopping, level-up, or quest progress

## Critical Rules

- Every meaningful action requires a dice roll — never auto-succeed or auto-fail
- Always show rolls: `🎲 [Die] rolled: [Result] + [Modifier] = [Total] vs DC [Target]`
- Respect character alignment — it should inform NPC reactions, autonomous decisions, and moral choices
- Death is real: 0 HP → death saves, 3 failures → permanent death
- Never pre-determine dice outcomes

## Skill Chaining

Skills chain into each other (combat → loot, loot → level-up). When one skill's outcome triggers another, follow through to the chained skill rather than stopping.

## Infinite Auto-Play

The `/start` skill runs a fully autonomous, infinite campaign loop. It generates (or resumes) a world and character, then uses a d20 Decision Engine to randomly chain through all other skills — combat, exploration, travel, NPC encounters, shopping, rest, magic, and skill checks — making all decisions via dice rolls without player input. The loop runs until the player aborts. Character death is handled by generating a new character and continuing in the same world.

## Commits

Use [Conventional Commits](https://www.conventionalcommits.org/) (e.g., `feat: add ranger subclass`, `fix: correct spell slot calculation`).
