# 🎲 Infinite RPG

A fully AI-driven tabletop RPG campaign system powered by **GitHub Copilot**. No code — just markdown skill files, dice, and imagination.

## How to Play

Open this project and start a Copilot Chat session. The game is played entirely through conversation. Reference skill files with `#file:skills/<skill>.md` and the rules with `#file:RULES.md` to give Copilot the context it needs.

### Getting Started

1. Open Copilot Chat
2. Reference `#file:RULES.md` and `#file:skills/new-campaign.md` — ask Copilot to generate your world
3. Reference `#file:skills/create-character.md` to build your hero
4. Start adventuring by referencing the relevant skill file for each action!

### Available Skills

| Skill File | What it does |
|------------|-------------|
| `skills/new-campaign.md` | 🌍 Generate a new world, setting, factions, and starting quest |
| `skills/create-character.md` | 🧝 Create a character with race, class, attributes, and skills |
| `skills/explore.md` | 🔍 Explore your surroundings, search for secrets, investigate |
| `skills/combat.md` | ⚔️ Fight enemies with initiative, attacks, and tactical combat |
| `skills/skill-check.md` | 🎯 Roll for any ability or skill test |
| `skills/magic.md` | ✨ Cast spells and use magical abilities |
| `skills/npc-encounter.md` | 🗣️ Meet and interact with NPCs |
| `skills/shop.md` | 🛒 Buy, sell, and trade at merchants |
| `skills/rest.md` | 🏕️ Take a short or long rest to recover |
| `skills/level-up.md` | ⬆️ Level up and gain new abilities |
| `skills/loot.md` | 💰 Generate treasure and magical items |
| `skills/travel.md` | 🗺️ Journey between locations with random encounters |

### Game System

- **D&D-inspired** d20 system with 6 core attributes
- **7 playable races**: Human, Elf, Dwarf, Halfling, Orc, Tiefling, Dragonborn
- **6 classes**: Warrior, Rogue, Mage, Cleric, Ranger, Bard
- **18 skills** with proficiency and expertise
- **XP-based leveling** with class features up to level 10
- **Full spellcasting** system with spell slots and cantrips
- **Every outcome determined by dice** — shown in the open

### Game State

Your game state is persisted as files:
- `characters/` — Character sheets (JSON)
- `campaigns/` — Campaign world state (JSON)

These files are read and updated automatically as you play.

### Core Rules

The full game rules are in `RULES.md` — reference it at the start of your session so Copilot knows the system.

### Tips

- Reference `#file:RULES.md` at the start of each session for consistent mechanics
- You can say anything — the skills handle the mechanics, but you drive the story
- Be creative! Propose unorthodox solutions and the GM will set a fair DC
- Your choices have consequences that persist in the campaign file
- Death is real — play smart or roll lucky 🎲
