---
mode: agent
description: "Visit a shop — buy, sell, and trade equipment, potions, and magical items"
tools:
  - view
  - edit
  - bash
---

# Shop & Trading

Handle all buying, selling, and trading interactions.

## 1. Load State

Read character file for: gold, inventory, CHA modifier, Persuasion skill.
Read campaign file for: current location and known merchants.

## 2. Generate a Shop (if new)

### Shop Type (d8)
| d8 | Shop |
|----|------|
| 1 | General Store — adventuring supplies, rations, rope |
| 2 | Blacksmith — weapons and armor |
| 3 | Apothecary — potions, herbs, antidotes |
| 4 | Arcanist — scrolls, components, magical curiosities |
| 5 | Tavern — food, drink, rooms, rumors |
| 6 | Fence — stolen goods, questionable items, information |
| 7 | Exotic Trader — rare materials, foreign goods, pets |
| 8 | Wandering Merchant — random assortment, unique items |

Generate the merchant as an NPC with personality and describe the shop's atmosphere.

## 3. Inventory Generation

### Standard Items (always available by shop type)

**General Store:**
| Item | Price |
|------|-------|
| Rations (1 day) | 5 SP |
| Rope (50ft) | 1 GP |
| Torch (10) | 1 GP |
| Backpack | 2 GP |
| Bedroll | 1 GP |
| Tinderbox | 5 SP |
| Waterskin | 2 SP |
| Healing Kit (10 uses) | 5 GP |
| Lantern | 5 GP |
| Oil (flask) | 1 SP |

**Blacksmith:**
| Item | Price | Stats |
|------|-------|-------|
| Dagger | 2 GP | 1d4 piercing, finesse, light, thrown |
| Shortsword | 10 GP | 1d6 piercing, finesse, light |
| Longsword | 15 GP | 1d8 slashing (1d10 versatile) |
| Greataxe | 30 GP | 1d12 slashing, heavy, two-handed |
| Shortbow | 25 GP | 1d6 piercing, range 80/320 |
| Longbow | 50 GP | 1d8 piercing, range 150/600 |
| Light Crossbow | 25 GP | 1d8 piercing, range 80/320 |
| Leather Armor | 10 GP | AC 11 + DEX |
| Chain Shirt | 50 GP | AC 13 + DEX (max 2) |
| Chain Mail | 75 GP | AC 16, STR 13 required |
| Plate Armor | 1,500 GP | AC 18, STR 15 required |
| Shield | 10 GP | +2 AC |

**Apothecary:**
| Item | Price | Effect |
|------|-------|--------|
| Healing Potion | 50 GP | Restores 2d4+2 HP |
| Greater Healing Potion | 150 GP | Restores 4d4+4 HP |
| Antitoxin | 50 GP | Advantage on poison saves for 1 hour |
| Potion of Resistance | 300 GP | Resistance to one element for 1 hour |
| Healer's Kit | 5 GP | 10 uses, stabilize dying creature |

**Arcanist:**
| Item | Price | Effect |
|------|-------|--------|
| Spell Scroll (1st level) | 75 GP | One-use spell, requires check if not on class list |
| Spell Scroll (2nd level) | 250 GP | One-use spell |
| Component Pouch | 25 GP | Replaces non-costly material components |
| Arcane Focus | 10 GP | Replaces non-costly material components |
| Spellbook (blank) | 50 GP | For recording spells |

### Special Stock (d6 items, rolled on rarity table)
Roll d100 for each special item:
| d100 | Rarity | Price Multiplier |
|------|--------|-----------------|
| 01–50 | Common | ×1 |
| 51–75 | Uncommon | ×3 |
| 76–90 | Rare | ×10 |
| 91–98 | Very Rare | ×50 |
| 99–100 | Legendary | ×500 |

Generate creative items appropriate to the rarity and shop type. Magical items should have interesting effects, not just stat boosts.

## 4. Buying

1. Player selects items
2. Calculate total cost
3. If player can afford it: deduct gold, add items to inventory
4. If player can't afford it: merchant says so, suggest haggling

## 5. Selling

Players can sell items at **half their base value** (round down).

Merchants will only buy items relevant to their shop type. A blacksmith won't buy potions.

## 6. Haggling

Player can attempt to get a better price:

**Persuasion check:**
- **DC 15**: 10% discount (buying) or 10% bonus (selling)
- **DC 20**: 20% discount/bonus
- **DC 25**: 30% discount/bonus (merchant's best offer)
- **Failure by 5+**: Merchant is offended, refuses to deal for the rest of the visit

**Deception check** (lying about item value):
- Same DCs as Persuasion
- If caught (merchant's Insight beats Deception): banned from the shop

Each player gets **one haggle attempt per transaction**.

## 7. Special Services

Some shops offer services:
- **Blacksmith**: Repair equipment (10% of item value), commission custom weapons (double price, 1d4 days)
- **Arcanist**: Identify magical items (25 GP), enchant items (varies)
- **Apothecary**: Cure disease (50 GP + Medicine check), brew custom potions (varies)

## 8. Update State

- Update character gold and inventory
- Save shop and merchant to campaign file for future visits
- Shop inventories refresh after d4 days of in-game time
