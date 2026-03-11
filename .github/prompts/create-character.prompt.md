---
mode: agent
description: "Create a new character — choose race, class, attributes, skills, and backstory"
tools:
  - create
  - edit
  - view
  - bash
---

# Character Creation Wizard

Guide the player through creating a new character step by step. **Roll dice where indicated.** Always show rolls.

## Step 1: Name & Concept

Ask the player for:
- **Character name**
- **Brief concept** (e.g., "a grizzled dwarven blacksmith turned adventurer")

If they want random generation, roll on improvised tables.

## Step 2: Choose Race

Present the available races from the core rules with their bonuses and traits:
- Human (+1 all, versatile)
- Elf (+2 DEX, +1 INT, darkvision, fey ancestry)
- Dwarf (+2 CON, +1 STR, darkvision, poison resistance)
- Halfling (+2 DEX, +1 CHA, lucky, brave)
- Orc (+2 STR, +1 CON, relentless endurance, savage attacks)
- Tiefling (+2 CHA, +1 INT, darkvision 120ft, fire resistance)
- Dragonborn (+2 STR, +1 CHA, breath weapon, elemental resistance)

If Dragonborn, also ask for **draconic ancestry** (fire, cold, lightning, acid, or poison).

## Step 3: Choose Class

Present the classes with a one-line pitch:
- **Warrior** — Master of weapons and armor. High HP, devastating attacks.
- **Rogue** — Stealthy striker. Sneak attack damage, skills galore.
- **Mage** — Arcane spellcaster. Fragile but devastating magical power.
- **Cleric** — Divine healer and protector. Spells from the gods.
- **Ranger** — Wilderness expert. Half-caster with martial prowess.
- **Bard** — Jack of all trades. Inspiration, magic, and charm.

## Step 4: Roll Attributes

Use the **4d6 drop lowest** method for each of the 6 attributes:
1. Roll 4d6 for each attribute
2. Drop the lowest die
3. Sum the remaining 3
4. Repeat for all 6 attributes
5. Let the player **assign** the 6 results to STR, DEX, CON, INT, WIS, CHA
6. **Apply racial bonuses** after assignment

Show every roll: `🎲 Attribute roll: [d1, d2, d3, d4] → drop [lowest] → total [sum]`

If the player prefers, offer **standard array** instead: 15, 14, 13, 12, 10, 8

## Step 5: Calculate Derived Stats

- **HP**: Max hit die value + CON modifier
- **AC**: Based on starting equipment (see class defaults)
- **Initiative**: DEX modifier
- **Proficiency Bonus**: +2 (level 1)

## Step 6: Allocate Skill Points

Calculate skill point pool: **4 + INT modifier** (minimum 1, +1 if Human)

Present the full skill list with governing attributes. Let the player spend points:
- **1 point** = proficiency in that skill
- **2 points** = expertise (double proficiency bonus)

Also grant **class skill proficiencies** for free:
- Warrior: Choose 2 from Athletics, Intimidation, Perception, Survival
- Rogue: Choose 4 from Acrobatics, Athletics, Deception, Insight, Intimidation, Investigation, Perception, Performance, Persuasion, Sleight of Hand, Stealth
- Mage: Choose 2 from Arcana, History, Insight, Investigation, Medicine, Religion
- Cleric: Choose 2 from History, Insight, Medicine, Persuasion, Religion
- Ranger: Choose 3 from Animal Handling, Athletics, Insight, Investigation, Nature, Perception, Stealth, Survival
- Bard: Choose any 3 skills

## Step 7: Starting Equipment & Gold

Roll starting gold: **class-based**
- Warrior: 5d4 × 10 GP
- Rogue: 4d4 × 10 GP
- Mage: 2d4 × 10 GP (but start with a spellbook)
- Cleric: 4d4 × 10 GP (start with a holy symbol)
- Ranger: 5d4 × 10 GP
- Bard: 5d4 × 10 GP (start with an instrument)

Give a sensible **starting equipment pack** based on class:
- Weapon(s), armor, adventurer's pack, class-specific item

## Step 8: Spells (if spellcaster)

For casters at level 1:
- **Mage**: Choose 3 cantrips + 6 first-level spells in spellbook (prepare INT modifier + 1)
- **Cleric**: Choose 3 cantrips, prepare WIS modifier + 1 first-level spells from full list
- **Bard**: Choose 2 cantrips + 4 first-level spells known
- **Ranger**: No spells at level 1

Generate spell options appropriate to the character concept and let the player choose.

## Step 9: Backstory

Ask the player to provide a backstory, or offer to **generate one** using the following prompts:
- Where did you grow up?
- What drove you to adventure?
- Who do you care about?
- What is your greatest fear?
- Do you have a rival or enemy?

Weave answers into a 2–3 paragraph backstory.

## Step 10: Save Character

Create the character file at `characters/{name-slug}.json` following the core rules format. Include all stats, inventory, spells, and backstory.

Present the completed character sheet in a readable format and ask: *"Your hero is ready. Shall we begin the adventure?"*
