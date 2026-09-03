# Installation and Load Order

*Part of the [AGOT: The Long Night & Azor Ahai](Home) wiki. The illustrated version of this page, with troubleshooting for GOG, Epic and Game Pass copies, is at [dlonem.com/mods/the-long-night/download](https://dlonem.com/mods/the-long-night/download).*

## If you play on Steam

Subscribe on the [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=3780269495). It is one click, it updates itself the moment a fix goes out, and the launcher sorts the load order for you. The manual install below exists for people who cannot use the Workshop at all.

## The one rule, first

**Disable every other Long Night mod.** *AGOT: The Long Night* and *The Long Night+* must be **unchecked in your playset** — not sorted below this one, disabled. This mod is a fork of both and ships files at the same paths, so either of them enabled anywhere in your list overrides it with older code and brings back the see-through dragon bug. You can unsubscribe from them entirely; this mod replaces both.

This is the single most common cause of "something is broken".

## Load order

1. **A Game of Thrones** — required, and also a manual install if you are not on Steam
2. AGOT submods — AGOT+, Valyrian Steel, Submod Core, Nobility of Westeros, model packs
3. **AGOT: The Long Night & Azor Ahai** — this mod
4. *Optional:* [Supernatural](https://dlonem.com/mods/supernatural)
5. *If you run Supernatural:* [**AGOT: Supernatural & The Long Night Compatibility Patch**](https://steamcommunity.com/sharedfiles/filedetails/?id=3780270228) — always last

The patch reconciles all three mods and needs all three loaded. If you run Supernatural and AGOT *without* this mod, you do not want it.

If you run a large playset, this mod should load after any other submod that touches the same scripted rules — in practice, after everything AGOT-related except the compatibility patch. A quick way to confirm: after a load, `logs/database_conflicts.log` in your CK3 documents folder should name this mod's files as the last definition of `is_alliance_valid`, `is_character_allowed_to_be_player` and `has_natural_death_second_chance`.

## Installing by hand

1. Download the newest archive from [Releases](https://github.com/Dlonem/CK3TheLongNightAzorAhai/releases) and unzip it.
2. Copy **both** `the-long-night-azor-ahai/` and `the-long-night-azor-ahai.mod` into your CK3 mod directory:

   | Platform | Path |
   |---|---|
   | Windows | `Documents\Paradox Interactive\Crusader Kings III\mod\` |
   | macOS | `~/Documents/Paradox Interactive/Crusader Kings III/mod/` |
   | Linux | `~/.local/share/Paradox Interactive/Crusader Kings III/mod/` |

   The folder goes *in* `mod\`. The `.mod` file sits next to it, not inside it. The launcher does **not** read the `descriptor.mod` inside the folder; it reads the separate `.mod` file beside it.
3. Open the Paradox launcher, add the mod to a playset, and set the load order above.

If the launcher reports a descriptor error, it is almost always the `path=` line in the `.mod` file. Use forward slashes even on Windows, and make sure the folder name matches exactly, including case.

## Mid-save, multiplayer, versions

- **Mid-save safe.** The mod can be added to a running campaign and updated on one. Game rules are the exception: CK3 bakes them in when a save is created, so an existing campaign keeps whatever rules it started with. Changing the invasion's timing or difficulty needs a fresh save.
- **Multiplayer.** Everyone needs the same version. A Workshop copy and a manual copy of different versions will not match checksums and the game will refuse to start. Check the version in the launcher against your friends before you host.
- **Game version.** Crusader Kings III 1.19.0.6, built against the current release of *A Game of Thrones*.
- **Languages.** English and Russian.

## A note for dragon-mod users

Dead dragons' looks are baked into your save against the exact list of portrait genes your mods add. Adding or removing *any* gene-adding mod mid-save — this one included — can scramble dragons that are already dead. Living ones are safe. Pick your dragon mods at campaign start and keep them.

## Reporting a problem

The [Discord](https://discord.gg/PTJzPQbqG7) is fastest; [GitHub issues](https://github.com/Dlonem/CK3TheLongNightAzorAhai/issues) work too. Include your CK3 version, your full load order, and whether you are on the Workshop copy or a manual install. Logs and screenshots help more than descriptions.

---
*[Back to Home](Home) · [Full mod page on dlonem.com](https://dlonem.com/mods/the-long-night)*
