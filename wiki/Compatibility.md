# Compatibility

*Part of the [AGOT: The Long Night & Azor Ahai](Home) wiki. On dlonem.com: [Setup](https://dlonem.com/mods/the-long-night/#setup) and [Full disclosure](https://dlonem.com/mods/the-long-night/#overrides).*

## Requirements

- Crusader Kings III **1.19.0.6**
- **A Game of Thrones** (the current release)
- No other Long Night mod. *AGOT: The Long Night* and *The Long Night+* must be **disabled**, not sorted — this mod ships files at the same paths and either of them loaded anywhere overrides it with older code.

## Other mods

| Mod | Status |
|---|---|
| **AGOT+**, **Valyrian Steel**, **Submod Core**, model packs | Compatible. Load them above this mod. |
| **Supernatural** (Dlonem) | Compatible with the [AGOT: Supernatural & The Long Night Compatibility Patch](https://steamcommunity.com/sharedfiles/filedetails/?id=3780270228), loaded last. The patch needs all three mods; it is not for Supernatural + AGOT without this mod. |
| **AGOT Additional Models and Special Buildings** | Compatible, in either order after AGOT. Checked symbol by symbol and file by file: its Night's Watch content is a separate decision and a vassal interaction, both of which go through AGOT's own recruitment effect, exactly as this mod's do. One shared on_action, and it is the merging kind. |
| **Nobility of Westeros**, **Essos Expanded**, **Essos Expanded: The Further East**, **Legacy of Valyria** | Their rulers are named correctly alongside this mod since 1.0.15a, with no patch from either side. Load this mod after them — several of them define the same scripted rules as this mod, and whichever loads last is the one the game keeps. Legacy of Valyria targets an older CK3 than AGOT itself; if you run it, expect no support for it here. |
| **Seasons of Ice and Fire** | The two mods detect each other and nothing collides. Deeper integration is planned. |
| **Kiss of Life (Revival)** | HadesOria maintains a cross-mod patch; this mod's side is limited to free flag reads. |
| **Any mod that adds portrait genes** | See the dragon warning below. |

Nobility of Westeros and Essos Expanded: The Further East replace the same file as each other, so those two conflict independently of this mod.

## The dragon warning

Dead dragons' appearances are stored in your save against the exact list of portrait genes loaded at the time they died. Adding or removing **any** gene-adding mod mid-save — this one included — can scramble dragons that are already dead. Living dragons are unaffected. Pick your dragon mods at campaign start and keep them.

## Mid-save and multiplayer

Safe to add to a running save and to update on one; fixes repair themselves as you play. Game rules are baked in at save creation. Multiplayer requires everyone to have the same version — a Workshop copy and a manual copy of different versions will not match checksums.

## What the mod overrides in AGOT

You deserve to know what a submod touches. The mod overrides **nineteen named AGOT definitions**. Every one is a same-name override — AGOT's body copied in full, one documented change, the change marked in the file — and every one is re-checked against AGOT's current version on each release. Two more merge with AGOT's definitions rather than replacing them.

### Six scripted rules

| Rule | The change |
|---|---|
| `is_alliance_valid` | Nothing living keeps an alliance with the dead |
| `is_character_allowed_to_be_player` | A character raised as one of the dead hands off to an heir |
| `has_natural_death_second_chance` | The red priest's last kiss (with Supernatural, its compatibility patch owns this one) |
| `can_be_activity_guest` | The dead are not guests |
| `is_diarch_valid` | A sworn brother cannot be regent of a southern kingdom |
| `can_move_domicile` | Ranging captains move their camps as the First Ranger does |

### Eight scripted triggers

| Trigger | The change |
|---|---|
| `can_be_knight_trigger` | The living do not serve the dead as knights, and the dead do not serve the living |
| `base_court_position_validity_trigger` | Nor as court officials |
| `can_be_councillor_basics_trigger` | Nor on the council |
| `can_be_commander_basic_trigger` | The Night King may lead his own host in person |
| `desirable_for_capture_trigger` | Taken in a siege, the Night King is imprisoned rather than randomly slain |
| `regency_for_personal_reasons_trigger` | No regency for a wight |
| `ai_can_valid_to_create_laamp_trigger` | The dead never become landless adventurers |
| `agot_mw_war_valid_during_megawar` | One check thirteen AGOT casus belli share: the dead cannot declare war on the dead |

### Three scripted effects

| Effect | The change |
|---|---|
| `set_title_localization_effect` | Wights, ranging captains and wardens get their titles; every other mod's titles pass through untouched |
| `dragon_combat_result_grab` | A dragon dying in a dragon duel may be claimed by the dead instead |
| `multi_duel_battle_theme_effect` | The Last Hour is fought in snow, not on a tourney ground |

### One decision, one casus belli

| | The change |
|---|---|
| `restore_the_nights_watch` | The Watch is refounded only when it is genuinely gone |
| `independence_war` | A sworn brother cannot declare independence from the Lord Commander, and nobody can secede from the Watch |

### Two that merge

The `agot_ranger_camp` domicile type, so a ranging captain can hold a camp at all (AGOT built it for exactly one title), and the `agot_on_title_gain_nightswatch` handler, so appointing a ranging captain does not force a government change on him.

Everything else sits alongside AGOT rather than on top of it. Since 1.0.13 the mod no longer ships its own copy of AGOT's scripted-rules file, and since 1.0.15a it no longer redefines the effect AGOT uses to name every ruler in the game — both were replaced with narrower overrides so that AGOT's changes reach you directly.

---
*[Back to Home](Home) · [Full mod page on dlonem.com](https://dlonem.com/mods/the-long-night)*
