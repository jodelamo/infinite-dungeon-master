# 🎲 Infinite RPG

A fully AI-driven tabletop RPG campaign system powered by **GitHub Copilot prompt files**. No code — just prompts, dice, and imagination.

## How to Play

Open this project in VS Code with GitHub Copilot Chat enabled. The game is played entirely through conversation using **prompt files** as skills.

### Getting Started

1. Open Copilot Chat
2. Type `#` and select `new-campaign` to generate your world
3. Use `create-character` to build your hero
4. Start adventuring!

### Available Prompts (Skills)

| Prompt | What it does |
|--------|-------------|
| `new-campaign` | 🌍 Generate a new world, setting, factions, and starting quest |
| `create-character` | 🧝 Create a character with race, class, attributes, and skills |
| `explore` | 🔍 Explore your surroundings, search for secrets, investigate |
| `combat` | ⚔️ Fight enemies with initiative, attacks, and tactical combat |
| `skill-check` | 🎯 Roll for any ability or skill test |
| `magic` | ✨ Cast spells and use magical abilities |
| `npc-encounter` | 🗣️ Meet and interact with NPCs |
| `shop` | 🛒 Buy, sell, and trade at merchants |
| `rest` | 🏕️ Take a short or long rest to recover |
| `level-up` | ⬆️ Level up and gain new abilities |
| `loot` | 💰 Generate treasure and magical items |
| `travel` | 🗺️ Journey between locations with random encounters |

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

These files are read and updated automatically by the prompts as you play.

### Tips

- You can say anything — the prompts handle the mechanics, but you drive the story
- Be creative! Propose unorthodox solutions and the GM will set a fair DC
- Your choices have consequences that persist in the campaign file
- Death is real — play smart or roll lucky 🎲
