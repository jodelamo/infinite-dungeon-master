# Magic & Spellcasting

Handle all magical actions — spellcasting, ritual magic, magical item use, and wild magic events.

## 1. Load Caster State

Read the character file to determine:
- Spellcasting class and ability (INT for Mage, WIS for Cleric/Ranger, CHA for Bard)
- Known/prepared spells and cantrips
- Available spell slots by level
- Spell attack bonus: `proficiency + spellcasting modifier`
- Spell save DC: `8 + proficiency + spellcasting modifier`
- Any active concentration spells

## 2. Spell Selection

If the player names a specific spell, use it. If they describe an effect, suggest the closest matching spell from their known/prepared list.

If the player wants to cast a spell they don't know: **"You don't have that spell prepared/known. Here's what you can cast..."** and list options.

## 3. Spell Slot Check

- **Cantrips**: Always available, no slot needed
- **Leveled spells**: Require and consume a spell slot of the spell's level or higher
- If no slots remain: *"You've exhausted your magical reserves. You need to rest to recover spell slots."*
- **Upcasting**: If cast at a higher slot level, apply enhanced effects (extra damage die, additional targets, etc.)

## 4. Resolve the Spell

### Spell Attack Rolls
For spells requiring an attack roll:
```
🎲 d20 + spell attack bonus vs target AC
→ Hit: Roll damage
→ Miss: Spell fizzles against the target
→ Nat 20: Critical — double damage dice!
```

### Saving Throw Spells
For spells requiring the target to save:
```
Target must make a [Attribute] saving throw:
🎲 d20 + target's [Attribute] modifier = [total] vs your Spell DC [dc]
→ Fail: Full effect
→ Save: Half damage / reduced effect / no effect (spell-dependent)
```

### Healing Spells
Roll the specified healing dice:
```
🎲 [dice] + spellcasting modifier = [total] HP restored
[Character] HP: [old] → [new] / [max]
```

### Area of Effect
For AoE spells, each creature in the area makes a saving throw individually. Roll for each and narrate the results.

### Concentration
If the spell requires **concentration**:
- Note it as active on the character
- If the caster takes damage, they must make a **Constitution saving throw**:
  - DC = 10 or half the damage taken, whichever is higher
  - Failure: Spell ends immediately
- Only one concentration spell at a time — casting another ends the first

## 5. Cantrip Scaling

Cantrip damage scales with **character level** (not class level):

| Character Level | Cantrip Dice |
|----------------|-------------|
| 1–4            | 1 die       |
| 5–10           | 2 dice      |
| 11–16          | 3 dice      |
| 17+            | 4 dice      |

## 6. Spell Compendium (Common Spells)

### Cantrips
| Spell | Class | Effect |
|-------|-------|--------|
| Fire Bolt | Mage | Ranged spell attack, 1d10 fire damage |
| Sacred Flame | Cleric | DEX save or 1d8 radiant damage |
| Vicious Mockery | Bard | WIS save or 1d4 psychic + disadvantage on next attack |
| Minor Illusion | Mage/Bard | Create a small illusory sound or image |
| Mending | Cleric/Mage | Repair a small break or tear in an object |
| Light | Cleric/Mage | Object sheds bright light 20ft, dim 20ft more |
| Prestidigitation | Mage | Minor magical tricks (light, clean, warm, flavor) |

### 1st Level
| Spell | Class | Slot | Effect |
|-------|-------|------|--------|
| Magic Missile | Mage | 1st | Auto-hit, 3 darts of 1d4+1 force each (upcasts: +1 dart per slot) |
| Shield | Mage | 1st (reaction) | +5 AC until start of next turn |
| Healing Word | Cleric/Bard | 1st (bonus) | 1d4 + modifier healing at range |
| Cure Wounds | Cleric | 1st | 1d8 + modifier healing (touch) |
| Bless | Cleric | 1st (conc) | Up to 3 creatures add d4 to attacks and saves |
| Thunderwave | Mage/Bard | 1st | 2d8 thunder, CON save or pushed 10ft |
| Charm Person | Bard/Mage | 1st | WIS save or charmed for 1 hour |
| Detect Magic | All casters | 1st (conc/ritual) | Sense magic within 30ft |
| Sleep | Mage/Bard | 1st | 5d8 HP of creatures fall unconscious |
| Entangle | Ranger | 1st (conc) | STR save or restrained in vines |

### 2nd Level
| Spell | Class | Slot | Effect |
|-------|-------|------|--------|
| Scorching Ray | Mage | 2nd | 3 rays, ranged spell attack, 2d6 fire each |
| Hold Person | All casters | 2nd (conc) | WIS save or paralyzed (humanoids) |
| Spiritual Weapon | Cleric | 2nd (bonus) | 1d8+ force damage, bonus action attacks |
| Misty Step | Mage/Bard | 2nd (bonus) | Teleport 30ft |
| Invisibility | Mage/Bard | 2nd (conc) | Target invisible until they attack/cast |
| Lesser Restoration | Cleric/Ranger/Bard | 2nd | Remove disease or condition |

### 3rd Level
| Spell | Class | Slot | Effect |
|-------|-------|------|--------|
| Fireball | Mage | 3rd | 8d6 fire, 20ft sphere, DEX save for half |
| Counterspell | Mage | 3rd (reaction) | Negate a spell being cast (auto if ≤3rd, check if higher) |
| Revivify | Cleric | 3rd | Raise dead creature (within 1 minute, costs 300 GP diamonds) |
| Dispel Magic | All casters | 3rd | End one spell on a target |
| Haste | Mage | 3rd (conc) | Double speed, +2 AC, extra action |

*Generate additional spells as needed, following the power curve and slot-level guidelines.*

## 7. Wild Magic (Optional)

When a Mage rolls a natural 1 on a spell attack or a natural 20, roll d100 on this wild magic table:

| d100 | Effect |
|------|--------|
| 01–10 | Harmless visual effect (sparkles, color change, phantom music) |
| 11–20 | Caster glows brightly for 1 minute |
| 21–30 | Random creature within 30ft is polymorphed into a sheep for 1 round |
| 31–40 | Caster teleports 10ft in a random direction |
| 41–50 | A spectral butterfly follows the caster for 24 hours |
| 51–60 | Caster's next spell is cast at +1 level for free |
| 61–70 | All creatures within 10ft regain 1d6 HP |
| 71–80 | Caster speaks only in rhyme for 10 minutes |
| 81–90 | Gravity reverses for the caster for 1 round |
| 91–99 | A small explosion — 1d6 force damage to everything within 5ft |
| 100   | Caster's most powerful available spell triggers centered on self |

## 8. Update State

After spellcasting:
- Deduct the spell slot used from the character file
- Update HP if healing or damage occurred
- Note active concentration spells
- Record any conditions applied to enemies/allies
- Award XP for creative spell use (25–50 XP)
