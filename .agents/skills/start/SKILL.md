---
name: start
description: Start an infinite autonomous campaign that auto-generates the world, characters, and plays through randomized adventures indefinitely. Use this when the player wants to watch an endless D&D campaign unfold automatically.
---

# Infinite Auto-Play Campaign

Run an autonomous, never-ending D&D campaign. The GM generates or resumes a world, creates or picks up a **party of characters**, then plays through an infinite loop of randomized adventures — exploring, fighting, resting, shopping, traveling, and meeting NPCs — making all decisions via dice rolls, until the player stops the process.

## Table of Contents

- [Workflow Checklist](#workflow-checklist)
- [1. Load or Create Game State](#1-load-or-create-game-state)
- [2. Adventure Loop](#2-adventure-loop)
- [3. Decision Engine](#3-decision-engine)
- [4. Scene Resolution](#4-scene-resolution)
- [5. Character Death](#5-character-death)
- [6. Loop Control](#6-loop-control)

## Workflow Checklist

Copy this checklist and mark each step complete as you go:

```
- [ ] 1. Load existing campaign & party — OR generate new ones
- [ ] 2. Enter the infinite adventure loop
- [ ] 3. (Loop) Roll on the Decision Engine to pick the next scene type
- [ ] 4. (Loop) Execute the scene using the appropriate skill
- [ ] 5. (Loop) Check party status (HP, resources, deaths)
- [ ] 6. (Loop) Repeat from step 3 — forever
```

## 1. Load or Create Game State

### Check for Existing State

Read the `campaigns/` and `characters/` directories.

**If campaign and character files exist:**
- List all available campaigns and characters to the player
- Ask the player: *"Pick up an existing campaign, or start fresh?"*
- If resuming: Load the campaign and all party member JSON files, read the session log, and narrate a brief recap of where things stand — current location, active quests, each character's HP and level, party gold, time of day
- Then proceed directly to **Step 2: Adventure Loop**

**If no files exist (or player chooses fresh):**
- Execute the **new-campaign** skill with all preferences set to "Surprise me" (roll dice for tone, setting hook, and world size)
- Determine party size by rolling d4+1 (2–5 characters). For each party member, execute the **create-character** skill with all choices randomized via dice rolls (race, class, alignment, attributes, background — all rolled, no player input). Ensure **class diversity** — reroll duplicates so the party has a mix of roles (e.g., frontline, healer, damage, utility). Each character gets a unique backstory that ties them to the generated world.
- Save all files and add every character filename to the campaign's `"party"` array, then proceed to **Step 2: Adventure Loop**

## 2. Adventure Loop

This is the **infinite core loop**. After every scene resolves, immediately roll for the next one. Never stop or ask the player what to do — the party acts autonomously based on dice rolls.

The loop repeats this cycle endlessly:

```
LOOP START
  |
  +-> Roll on Decision Engine (Step 3)
  +-> Resolve the scene using the matching skill (Step 4)
  +-> Update all state files (all character JSONs + campaign JSON)
  +-> Check party status (Step 5)
  |     |
  |     +-> If a character died: handle death (Step 5)
  |     +-> If entire party is dead: generate a new full party and continue
  |     +-> If survivors remain: continue with reduced party
  |
  +-> GOTO LOOP START
```

**Pacing:** After each scene, narrate a brief transitional beat (a moment of quiet, a shift in weather, time passing) before rolling the next scene. This keeps the narrative flowing naturally.

**Time Tracking:** Advance the in-game clock after every scene. Track day/night cycles. After 12-16 hours of in-game activity without rest, the party should prioritize resting (weight the Decision Engine toward rest).

## 3. Decision Engine

At the start of each loop iteration, roll to determine what happens next.

### Situational Modifiers

Before rolling, check **every party member's current state** and apply **weighted overrides** based on the party as a whole:

| Condition | Override |
|-----------|----------|
| **Any** member's HP below 25% of max | Force **rest** or **shop** (for healing potions) — roll d6: 1-4 rest, 5-6 shop |
| **Majority** of party below 50% HP | Force **rest** (long rest) |
| 0 active quests | Weight toward **NPC encounter** (quest delivery) — add +3 to roll |
| Just finished combat | Skip combat this roll — reroll if combat comes up |
| 12+ hours without rest | Force **rest** |
| At a town/safe location | Allow **shop** and **NPC encounter** results |
| In wilderness / dungeon | Allow **combat** and **explore** results |
| New location just reached | Force **explore** before other actions |
| **Any** member reached level-up threshold | Force **level-up** for that member before continuing |

### Main Decision Table (d20)

Roll d20 after applying situational overrides:

| d20   | Scene Type | Skill to Execute |
|-------|-----------|-----------------|
| 1-4   | **Combat Encounter** | Use the **combat** skill |
| 5-7   | **Exploration** | Use the **explore** skill |
| 8-9   | **NPC Encounter** | Use the **npc-encounter** skill |
| 10-11 | **Travel** | Use the **travel** skill (pick a destination from the campaign map, or generate a new one) |
| 12-13 | **Rest & Recovery** | Use the **rest** skill (short or long rest based on HP: below 50% = long rest, above = short rest) |
| 14    | **Shopping** | Use the **shop** skill (only if at a settlement; otherwise reroll) |
| 15    | **Magic Event** | Use the **magic** skill (arcane anomaly, wild magic surge, or ritual opportunity) |
| 16-17 | **Skill Challenge** | Use the **skill-check** skill (environmental obstacle, social test, or puzzle) |
| 18-19 | **Quest Progression** | Advance an active quest — pick the most urgent one, generate the next step, and resolve it using the appropriate skill |
| 20    | **Major Event** | Something dramatic happens — roll d6: 1-2 ambush by a powerful enemy (deadly combat), 3-4 discover a legendary location, 5 meet a major faction leader (NPC encounter), 6 find a treasure hoard (loot skill) |

### Autonomous Character Decisions

When a skill requires player choices (e.g., combat actions, dialogue options, shop purchases), the GM makes decisions **for each party member individually, in character**. Every character acts according to their own profile:

1. **Class and abilities**: A wizard prefers spells, a fighter prefers melee, a rogue looks for stealth opportunities. Each party member uses their own strengths.
2. **Alignment**: A Lawful character respects authority and keeps promises; a Chaotic character acts on impulse and resists control; a Good character helps others and avoids harm; an Evil character pursues self-interest. Alignment is the primary driver of moral choices. **Party members may disagree** — let intra-party tension play out narratively when alignments conflict.
3. **Personality**: Derived from each character's backstory, background, and alignment. Different party members should react differently to the same situation.
4. **Tactical sense**: Choose the mechanically smart option most of the time, but occasionally (on a d20 roll of 1-3) make a suboptimal but flavorful choice
5. **Resources**: Conserve spell slots and potions when HP is high; use them freely when things are desperate
6. **Party coordination**: Characters should play to their roles — the healer heals, the tank draws aggro, the rogue flanks. Occasionally roll d6: on a 1, a character acts selfishly or independently instead of coordinating.

#### Who Speaks for the Party?

For scenes where one character takes the lead (e.g., negotiation, bartering, scouting), choose the **most qualified party member** for the task (highest relevant skill modifier). Other members may assist (Help action, granting advantage) or interject based on personality.

For dialogue and social encounters, roll on this table to determine the **lead character's** approach:

| d6 | Approach |
|----|----------|
| 1  | Friendly and diplomatic (Persuasion) |
| 2  | Cautious and observant (Insight) |
| 3  | Boastful and entertaining (Performance) |
| 4  | Deceptive and cunning (Deception) |
| 5  | Direct and intimidating (Intimidation) |
| 6  | Honest and straightforward (no check, just talk) |

## 4. Scene Resolution

For every scene, follow this exact procedure:

1. **Open with a scene banner** — use the scene banner format from RULES.md § "Display Formatting — Scene Banners". Every scene MUST open with the appropriate header banner showing the scene type icon, location, and current in-game time.
2. **Narrate the setup** — describe what the party encounters, using vivid sensory detail. Show how different party members react to the scene based on their personalities.
3. **Execute the matching skill** — follow its full workflow checklist step by step (load state, resolve actions, update state). In combat, every party member rolls initiative and acts on their own turn. In social scenes, choose a lead character (see "Who Speaks for the Party?" above).
4. **Show all dice rolls** — every roll is visible in the standard format: `🎲 [Die] rolled: [Result] + [Modifier] = [Total] vs DC [Target]`
5. **Narrate the outcome** — describe what happened and how **each party member** reacts. Highlight individual moments — the rogue's quip, the cleric's prayer, the fighter's exhaustion.
6. **Update state files** — write to **every** character JSON and the campaign JSON after every scene
7. **Close with a party status footer** — always end each scene with a status footer showing **every party member's** current HP, plus shared gold, XP, and location (see "Party Status Footer" below)
8. **Transition** — brief narrative bridge to the next scene

### Party Status Footer

Replace the single-character footer with a party-wide display:

```
─────────────────────────────────────────
🗡️ Kaelith (Fighter 3)   ❤️ 22/30 HP
🔮 Seraphine (Wizard 3)  ❤️ 11/18 HP
🛡️ Thorne (Cleric 3)     ❤️ 26/26 HP
🗡️ Vex (Rogue 3)         ❤️ 15/22 HP
🪙 128 GP  |  📍 Darkhollow Cave  |  Day 3, Dusk
─────────────────────────────────────────
```

Use class-appropriate icons for each character (⚔️ martial, 🔮 arcane caster, 🛡️ support/tank, 🗡️ finesse/stealth). Mark unconscious members with 💀 and dead members with ☠️ instead of the class icon.

### Skill Chaining

Follow all natural skill chains as defined in each skill:
- **Combat** chains to **loot**, which may chain to **level-up**
- **Explore** may chain to **npc-encounter**, **loot**, or **combat** (traps/ambushes)
- **Travel** may chain to **combat** (random encounters) or **explore** (new locations)
- **NPC encounter** may chain to **quest progression** or **shop**

Let chains resolve fully before rolling the next Decision Engine result.

## 5. Character Death

Death is real and permanent. The campaign handles individual deaths and total party kills differently.

### Individual Death (Party Has Survivors)

When a single party member dies but others survive:

1. **Narrate the death solemnly** — honor the fallen character. Show how the surviving party members react: grief, rage, stoic resolve, or cold pragmatism — each according to their personality and alignment.
2. **Record the death** in the campaign session log with cause, location, level reached, and which party members witnessed it.
3. **Continue the scene** — surviving members finish whatever scene is in progress (combat, exploration, etc.) before a replacement arrives.
4. **Generate a replacement** immediately using the **create-character** skill with all choices randomized. Ensure class diversity — avoid duplicating a class already in the party.
5. **Narrative hook**: The new character joins the party through a dice-rolled circumstance:

| d6 | How the New Character Arrives |
|----|-------------------------------|
| 1  | Was already nearby, drawn by the sounds of the previous battle |
| 2  | A traveling adventurer passing through, stumbles upon the party |
| 3  | Sent by a faction or NPC who learned of the party's loss |
| 4  | Emerges from a nearby dungeon or cave, seeking companions |
| 5  | A prisoner or captive just freed by the party from a nearby threat |
| 6  | Found injured on the road — the party heals them, and they join out of gratitude |

6. **Update state** — add the new character file to the campaign's `"party"` array. Remove the dead character's filename from `"party"` but **do not delete their JSON file** (it serves as a memorial record).
7. **Resume the Adventure Loop** from Step 2.

### Total Party Kill (TPK)

When **every** party member is dead:

1. **Narrate the TPK dramatically** — describe the final moments of the last character standing.
2. **Record the TPK** in the campaign session log as a major event.
3. **The world persists** — the campaign state, quests, NPCs, factions, and world events all continue. The story does not reset.
4. **Generate a completely new party** — roll d4+1 for party size, then create each member with the **create-character** skill (all randomized, class diversity enforced).
5. **Narrative hook for the new party**: Roll d6 for how the new group enters the story:

| d6 | How the New Party Enters |
|----|--------------------------|
| 1  | Hired by a faction to investigate what happened to the previous party |
| 2  | Adventurers who discover the previous party's remains and take up their quest |
| 3  | Prisoners who escape captivity near the previous party's last location |
| 4  | A new group of travelers who arrive at the nearest settlement and hear rumors |
| 5  | Summoned by a divine or arcane entity who needs mortal agents |
| 6  | A mercenary company passing through, drawn by bounties on local threats |

6. **Update state** — replace the campaign's `"party"` array with the new character filenames.
7. **Resume the Adventure Loop** from Step 2.

## 6. Loop Control

This campaign runs **infinitely**. The GM never stops to ask "What do you want to do?" — instead, the Decision Engine drives all action automatically.

**The only way to stop is for the player to interrupt or abort the process.**

### Session Pacing

- Keep scenes varied — the Decision Engine's weighted modifiers prevent repetitive sequences
- Aim for a rhythm: action, exploration, social, rest — with twists from Major Events
- Every 5-10 scenes, introduce a narrative thread that connects recent events (a recurring villain, a building mystery, a faction conflict escalating)
- Track the campaign's evolving story in the session log

### Narrative Continuity

Even though scenes are randomized, maintain coherent storytelling:
- Reference previous events in narration ("The scar from yesterday's goblin ambush still aches across Thorne's shoulder...")
- Have NPCs react to the **party's** growing reputation — refer to the group by a collective name or by their most famous member
- Let party members reference each other's past actions ("Remember when Vex nearly got us killed in that swamp?")
- Advance active quests naturally — don't let them stagnate
- Evolve the world state — factions act, weather changes, time passes, seasons shift
- When a party member dies and is replaced, have survivors occasionally mention the fallen — grief lingers
