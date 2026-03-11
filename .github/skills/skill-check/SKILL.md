---
name: skill-check
description: Resolve any ability check or skill test the player attempts with dice rolls. Use this when the player attempts an action requiring a skill or ability check.
---

# Skill Check

Resolve any ability check or skill test the player attempts.

## 1. Load Character

Read the character file to get:
- All attribute scores and modifiers
- Skill proficiencies and expertise
- Current conditions that might affect the roll
- Proficiency bonus for current level

## 2. Determine the Check

Based on what the player wants to do, determine:

### The Skill or Ability
Match the action to the most appropriate skill:
| Player wants to... | Skill | Attribute |
|---|---|---|
| Climb a wall | Athletics | STR |
| Sneak past guards | Stealth | DEX |
| Pick a lock | Sleight of Hand | DEX |
| Recall ancient lore | History or Arcana | INT |
| Sense a lie | Insight | WIS |
| Convince someone | Persuasion | CHA |
| Threaten someone | Intimidation | CHA |
| Track an animal | Survival | WIS |
| Diagnose an illness | Medicine | WIS |
| Perform a song | Performance | CHA |
| Balance on a beam | Acrobatics | DEX |
| Calm a wild beast | Animal Handling | WIS |
| Search a room | Investigation | INT |
| Notice something | Perception | WIS |
| Tell a lie | Deception | CHA |
| Identify a plant | Nature | INT |
| Know about a god | Religion | INT |

If the action doesn't clearly map, use a **raw ability check** (just the attribute modifier, no skill bonus).

### The Difficulty Class (DC)
Set a fair DC based on the situation:

| Difficulty | DC | Example |
|---|---|---|
| Trivial | 5 | Climb a ladder |
| Easy | 10 | Climb a rough stone wall |
| Medium | 15 | Climb a slippery cliff |
| Hard | 20 | Climb an overhang |
| Very Hard | 25 | Climb a smooth marble wall |
| Nearly Impossible | 30 | Climb an inverted glass ceiling |

**Explain the DC choice** briefly so the player understands the challenge.

## 3. Check for Advantage/Disadvantage

Apply advantage or disadvantage based on circumstances:
- **Advantage**: Helpful conditions, creative approach, ally Help action
- **Disadvantage**: Hostile conditions, injuries, distractions, relevant condition (poisoned, frightened, etc.)
- If both apply, they cancel out → normal roll

## 4. Roll the Check

```
🎲 d20 rolled: [result]
  + [attribute] modifier: [mod]
  + proficiency bonus: [bonus] (if proficient)
  = Total: [total]
  vs DC [dc]

→ [SUCCESS ✅ / FAILURE ❌]
```

If advantage/disadvantage:
```
🎲 d20 rolled: [roll1] and [roll2] → taking [higher/lower]: [chosen]
```

## 5. Narrate the Outcome

### On Success
Describe the character succeeding. The margin of success can flavor the narration:
- **Beat DC by 5+**: Exceptional success — add a bonus effect or extra detail
- **Beat DC by 10+**: Masterful — something extra happens (find a bonus item, impress onlookers, gain advantage on the next related check)

### On Failure
Describe the failure, but **make it interesting**, not just "you fail":
- **Miss DC by 1–4**: Partial success or "succeed at a cost" — offer a complication
- **Miss DC by 5+**: Clear failure with consequences
- **Miss DC by 10+**: Dramatic failure — something bad happens (alert guards, break the tool, fall and take d6 damage)

### Natural 20 on Skill Checks
Not an automatic success (unlike attacks), but describe the attempt as impressively as possible. If the total still beats the DC, make it spectacular.

### Natural 1 on Skill Checks
Not an automatic failure, but describe the attempt as comically or dramatically poor. If the total somehow still beats the DC, they succeed despite themselves.

## 6. Award XP

For significant skill checks:
- **Easy check in a tense moment**: 10 XP
- **Medium check advancing the story**: 25 XP
- **Hard check with real stakes**: 50 XP
- **Very Hard / Nearly Impossible success**: 100 XP

## 7. Opposed Checks

If the check is **against another creature** (e.g., Stealth vs Perception, Deception vs Insight):
1. Roll for the player: `d20 + modifier`
2. Roll for the opponent: `d20 + modifier`
3. **Higher total wins.** Ties go to the one being checked against (status quo).

Show both rolls clearly.

## 8. Group Checks

If the whole party attempts something (e.g., everyone tries to sneak):
1. Each character rolls individually
2. If **at least half succeed**, the group succeeds
3. Narrate both the successes and failures within the group effort

## 9. Update State

- Record XP gains in character file
- Note any consequences (damage, conditions, changed world state) in campaign file
- Advance time if appropriate (most checks take seconds, but some like tracking take hours)
