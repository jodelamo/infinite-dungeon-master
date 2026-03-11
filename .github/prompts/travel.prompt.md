---
mode: agent
description: "Travel across the world — journey between locations with random encounters and events"
tools:
  - view
  - edit
  - bash
---

# Overworld Travel

Handle journeys between locations with travel events, random encounters, and world-building.

## 1. Load State

Read campaign and character files for:
- Current location and destination
- Known map locations and routes
- Party supplies (rations, water, torches)
- Time of day and weather
- Character's Survival, Perception, and Nature skills

## 2. Determine Travel Details

### Distance & Duration
If the route is known, use the campaign data. If new, generate:

| Distance | Travel Time (on foot) | Travel Time (mounted) |
|----------|----------------------|----------------------|
| Nearby   | 1–4 hours            | 30 min – 2 hours     |
| Near     | 1 day                | Half day              |
| Far      | 2–3 days             | 1–2 days             |
| Distant  | 1–2 weeks            | 3–7 days             |

### Terrain Type
If not established, roll d8:
| d8 | Terrain |
|----|---------|
| 1 | Road — safe, fast travel |
| 2 | Forest — moderate cover, foraging |
| 3 | Mountains — slow, dangerous, scenic |
| 4 | Swamp — slow, disease risk, ambush territory |
| 5 | Plains — fast, exposed, long sightlines |
| 6 | Desert — hot, dehydrating, navigation risk |
| 7 | Coast — salt air, seafood, pirates |
| 8 | Underdark/Cave — dark, deadly, exotic |

### Weather (d8)
| d8 | Weather |
|----|---------|
| 1 | Clear and calm |
| 2 | Overcast |
| 3 | Light rain |
| 4 | Heavy rain/storm — disadvantage on Perception, difficult terrain |
| 5 | Fog — visibility reduced to 30ft |
| 6 | Wind — ranged attacks at disadvantage |
| 7 | Extreme heat — CON save DC 10 every 4 hours or gain exhaustion |
| 8 | Extreme cold — CON save DC 10 every 4 hours or gain exhaustion |

## 3. Travel Narration

Describe the journey in atmospheric prose:
- The terrain and scenery changing
- The time of day shifting (dawn → midday → dusk → night)
- Sounds, smells, and wildlife
- How the character feels

Break multi-day journeys into segments with narration for each.

## 4. Random Encounters (per travel segment)

Roll d20 for each half-day of travel:

### Road / Safe Territory
| d20 | Encounter |
|-----|-----------|
| 1 | Bandits! (combat encounter) |
| 2–3 | Merchant caravan — opportunity to trade |
| 4–5 | Fellow travelers — exchange news and rumors |
| 6–7 | Patrol/guards — may ask for papers or offer directions |
| 8–9 | Broken cart/camp — investigate or pass by |
| 10–20 | Uneventful travel |

### Wilderness
| d20 | Encounter |
|-----|-----------|
| 1–2 | Monster attack! (scale to party level) |
| 3–4 | Natural hazard (rockslide, flash flood, sinkhole) — DEX/STR save |
| 5–6 | Lost! Navigation check (Survival DC 15) or add d4 hours |
| 7–8 | Mysterious structure — ruins, shrine, or cave entrance |
| 9–10 | Wounded NPC needing help |
| 11–12 | Beautiful landmark — describe, award 25 XP for discovery |
| 13–14 | Tracks of something large — Survival DC 12 to identify |
| 15–16 | Foraging opportunity — Nature DC 10 for d4 rations |
| 17–18 | Weather change (reroll weather) |
| 19–20 | Uneventful segment |

### Dangerous Territory
| d20 | Encounter |
|-----|-----------|
| 1–5 | Monster attack! (hard difficulty) |
| 6–7 | Ambush! Perception vs Stealth or surprised |
| 8–9 | Trap (pit, snare, magical ward) |
| 10–11 | Lair entrance — dangerous but potentially great loot |
| 12–13 | Hostile NPC (bounty hunter, rival adventurer, cultist) |
| 14–15 | Environmental hazard requiring saves |
| 16–17 | Eerie signs — bones, warnings, abandoned camps |
| 18 | Friendly NPC who knows a secret |
| 19 | Hidden shortcut — Perception DC 18 to spot, saves d4 hours |
| 20 | Something extraordinary — portal, ancient artifact, slumbering dragon |

## 5. Resource Management

### Rations
Each character consumes **1 ration per day**. Track rations:
- If rations run out, must forage: **Survival DC 10** for d4 rations (takes 1 hour)
- Failure: No food. After 3 + CON modifier days without food, gain 1 exhaustion per day

### Water
In hot or desert terrain, require **2 waterskins per day** or CON save DC 15 or gain exhaustion.

### Torches / Light
In dark areas (caves, nighttime forest), require a light source:
- Torch: 1 hour, bright 20ft, dim 20ft
- Lantern: 6 hours per oil flask
- Darkvision: Characters with darkvision are fine in dim light

### Navigation
In unfamiliar territory without a road:
- **Survival DC 12**: Stay on course
- **Failure**: Add d4 hours, possibly encounter something unexpected
- **Failure by 5+**: Lost. Must make another check to reorient, or backtrack

## 6. Arrival

When the party arrives at the destination:
1. Describe the approach (what they see from a distance)
2. Note the time of arrival and current weather
3. Present immediate options (enter the town, scout the area, make camp)
4. Update the campaign file with the new location

If it's a new location, generate it:
- Name, type, size
- Notable features (3–5)
- Inhabitants and atmosphere
- Potential hooks and dangers

## 7. Update State

After travel:
- Update current location in campaign file
- Deduct rations consumed
- Update time (hours/days elapsed)
- Record any new locations discovered
- Record any encounters and their outcomes
- Award XP for travel encounters and discoveries
- Update HP if any damage occurred during travel
