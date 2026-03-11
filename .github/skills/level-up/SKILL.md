---
name: level-up
description: Handle character advancement when XP reaches the level-up threshold. Use this when a character levels up or the player asks to level up.
---

# Level Up

Handle character advancement when XP reaches the threshold.

## 1. Load Character

Read the character file. Verify:
- Current XP ≥ XP threshold for next level
- Current level and class
- All current stats for reference

If XP is insufficient: *"You need [X] more XP to reach level [N]. Keep adventuring!"*

## 2. Announce the Level Up

Narrate the level-up dramatically:
*"Experience courses through you like fire. Battles fought, lessons learned, secrets uncovered — it all crystallizes into newfound power. You are now **Level [N]**!"*

## 3. Apply Core Improvements

### Hit Points
Roll the class hit die (or take the average, player's choice):
- **Warrior**: `🎲 d10 + CON modifier` (average: 6 + CON)
- **Rogue**: `🎲 d8 + CON modifier` (average: 5 + CON)
- **Mage**: `🎲 d6 + CON modifier` (average: 4 + CON)
- **Cleric**: `🎲 d8 + CON modifier` (average: 5 + CON)
- **Ranger**: `🎲 d10 + CON modifier` (average: 6 + CON)
- **Bard**: `🎲 d8 + CON modifier` (average: 5 + CON)

Show the roll: `🎲 HP roll: [result] + CON mod [mod] = +[total] HP → New max HP: [new_max]`

Minimum HP gain per level: 1 (even with negative CON modifier).

### Proficiency Bonus
Update if crossing a threshold:
| Levels | Bonus |
|--------|-------|
| 1–4    | +2    |
| 5–8    | +3    |
| 9–12   | +4    |
| 13–16  | +5    |
| 17–20  | +6    |

### Hit Dice
Gain 1 additional hit die of the class type.

## 4. Allocate Skill Points

Calculate new skill points: **2 + INT modifier** (minimum 1)

Present the player's current skill proficiencies and let them spend points:
- **1 point** → Gain proficiency in a new skill
- **2 points** → Upgrade proficiency to expertise (if class allows expertise)

Show the updated skill list after allocation.

## 5. Class Features by Level

### Warrior
| Level | Feature |
|-------|---------|
| 1 | Fighting Style (choose: Defense +1AC, Dueling +2 damage, Great Weapon reroll 1s/2s, Archery +2 ranged) |
| 2 | Action Surge (1 extra action, 1/short rest) |
| 3 | Martial Archetype (Champion: crit on 19–20, Battlemaster: maneuvers, Eldritch Knight: spellcasting) |
| 4 | Ability Score Improvement (+2 to one attribute or +1 to two, or a Feat) |
| 5 | Extra Attack (2 attacks per Attack action) |
| 6 | Ability Score Improvement |
| 7 | Archetype Feature |
| 8 | Ability Score Improvement |
| 9 | Indomitable (reroll a failed save, 1/long rest) |
| 10 | Archetype Feature |

### Rogue
| Level | Feature |
|-------|---------|
| 1 | Sneak Attack +1d6, Expertise (double proficiency on 2 skills) |
| 2 | Cunning Action (Dash, Disengage, or Hide as bonus action) |
| 3 | Roguish Archetype (Thief: fast hands/climb speed, Assassin: auto-crit surprised foes, Arcane Trickster: spellcasting) |
| 4 | Ability Score Improvement |
| 5 | Uncanny Dodge (halve one attack's damage, reaction) |
| 6 | Expertise (2 more skills) |
| 7 | Evasion (DEX save AoE: success=0, fail=half) |
| 8 | Ability Score Improvement |
| 9 | Sneak Attack +5d6 (cumulative: +1d6 every odd level) |
| 10 | Ability Score Improvement |

### Mage
| Level | Feature |
|-------|---------|
| 1 | Arcane Recovery (recover slots = half level on short rest, 1/day) |
| 2 | Arcane Tradition (Evocation: sculpt AoE, Abjuration: ward, Divination: portent) |
| 3 | 2nd-level spell slots |
| 4 | Ability Score Improvement |
| 5 | 3rd-level spell slots |
| 6 | Tradition Feature |
| 7 | 4th-level spell slots |
| 8 | Ability Score Improvement |
| 9 | 5th-level spell slots |
| 10 | Tradition Feature |

### Cleric
| Level | Feature |
|-------|---------|
| 1 | Divine Domain (Life: bonus healing, Light: fire powers, War: bonus attacks) |
| 2 | Channel Divinity (Turn Undead + domain power, 1/short rest) |
| 3 | 2nd-level spell slots |
| 4 | Ability Score Improvement |
| 5 | Destroy Undead (CR ½), 3rd-level slots |
| 6 | Channel Divinity (2/short rest), Domain Feature |
| 7 | 4th-level spell slots |
| 8 | Ability Score Improvement, Domain Feature |
| 9 | 5th-level spell slots |
| 10 | Divine Intervention (roll d100 ≤ level for divine help) |

### Ranger
| Level | Feature |
|-------|---------|
| 1 | Favored Enemy (+2 to track/recall info), Natural Explorer (ignore difficult terrain in favored land) |
| 2 | Fighting Style + Spellcasting (2 first-level slots, 2 spells known) |
| 3 | Ranger Archetype (Hunter: combat bonuses, Beast Master: animal companion) |
| 4 | Ability Score Improvement |
| 5 | Extra Attack, 2nd-level spell slots |
| 6 | Favored Enemy improvement (+1 type), Natural Explorer (+1 terrain) |
| 7 | Archetype Feature |
| 8 | Ability Score Improvement, Land's Stride |
| 9 | 3rd-level spell slots |
| 10 | Hide in Plain Sight (+10 Stealth in natural terrain) |

### Bard
| Level | Feature |
|-------|---------|
| 1 | Bardic Inspiration d6 (CHA mod uses/long rest), Spellcasting |
| 2 | Jack of All Trades (+half proficiency to non-proficient checks), Song of Rest (d6 bonus healing on short rest) |
| 3 | Bard College (Lore: extra skills + Cutting Words, Valor: martial + Combat Inspiration), Expertise (2 skills) |
| 4 | Ability Score Improvement |
| 5 | Bardic Inspiration d8, Font of Inspiration (recharge on short rest) |
| 6 | College Feature, Countercharm |
| 7 | 4th-level spell slots |
| 8 | Ability Score Improvement |
| 9 | Song of Rest d8, 5th-level spell slots |
| 10 | Bardic Inspiration d10, Expertise (2 more skills), Magical Secrets (learn 2 spells from any class) |

## 6. Ability Score Improvements (Levels 4, 8, etc.)

When an ASI is earned, the player chooses:
- **+2 to one attribute** (max 20)
- **+1 to two attributes** (max 20 each)
- **A Feat** (special ability in place of stat increase)

### Sample Feats
| Feat | Effect |
|------|--------|
| Alert | +5 initiative, can't be surprised |
| Tough | +2 HP per level (retroactive) |
| Lucky | 3 luck points/long rest — reroll any d20 |
| Sharpshooter | −5 attack for +10 ranged damage, ignore cover |
| Great Weapon Master | −5 attack for +10 melee damage (two-handed), bonus attack on crit/kill |
| War Caster | Advantage on concentration saves, somatic with hands full |
| Resilient | +1 to chosen attribute, gain save proficiency in it |
| Mobile | +10 speed, no opportunity attacks from creatures you attack |

## 7. New Spells (Casters)

If the character is a spellcaster, they gain new spells at the new level:
- **Mage**: +2 spells added to spellbook (any level they can cast)
- **Cleric**: Access to full cleric list up to new max spell level
- **Bard**: +1 spell known (can swap 1 old spell for a new one)
- **Ranger**: +1 spell known at levels when new slots appear

Present appropriate spell options and let the player choose.

## 8. Update XP Threshold

Set the new XP target for the next level per the XP table in core rules.

## 9. Present the Updated Character

Display the full updated character sheet showing all changes highlighted. Save the updated character file.

End with: *"You feel stronger, sharper, more capable. The road ahead holds new challenges worthy of your growing power."*
