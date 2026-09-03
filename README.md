# AGOT: The Long Night & Azor Ahai

A Crusader Kings III mod for the *A Game of Thrones* total conversion, set in the
Long Night — the eight-thousand-year-old war against the Others, and the prophecy
of the prince that was promised.

**If you play CK3 on Steam, use the Workshop.** It is one click, it updates itself
the moment a fix goes out, and it sorts the load order for you. This repository
exists for people who can't use the Workshop at all.

- **Steam Workshop** — https://steamcommunity.com/sharedfiles/filedetails/?id=3780269495
- **Full install guide** — https://dlonem.com/mods/the-long-night/download
- **Mod page** — https://dlonem.com/mods/the-long-night
- **Wiki** — https://github.com/Dlonem/CK3TheLongNightAzorAhai/wiki (mirrors the mod page; carries the full version history)
- **Discord** — https://discord.gg/PTJzPQbqG7

---

## What's in this repository

```
the-long-night-azor-ahai/      the mod itself
the-long-night-azor-ahai.mod   the descriptor the launcher reads
wiki/                          source for the GitHub wiki pages (not part of the mod)
CHANGELOG.md                   every release note, newest first
```

Both are needed. The launcher does **not** read the `descriptor.mod` inside the
mod folder — it reads the separate `.mod` file that sits beside it.

## Installing by hand

The step-by-step version with troubleshooting lives at
[dlonem.com/mods/the-long-night/download](https://dlonem.com/mods/the-long-night/download).
The short version:

1. Download the newest archive from [Releases](https://github.com/Dlonem/CK3TheLongNightAzorAhai/releases)
   and unzip it.
2. Copy **both** `the-long-night-azor-ahai/` and `the-long-night-azor-ahai.mod`
   into your CK3 mod directory:

   | | |
   |---|---|
   | Windows | `Documents\Paradox Interactive\Crusader Kings III\mod\` |
   | macOS | `~/Documents/Paradox Interactive/Crusader Kings III/mod/` |
   | Linux | `~/.local/share/Paradox Interactive/Crusader Kings III/mod/` |

   The folder goes *in* `mod\`. The `.mod` file sits next to it, not inside it.
3. Open the Paradox launcher, add the mod to a playset, and set the load order:

   - **A Game of Thrones** — required, and also a manual install if you're not on Steam
   - AGOT submods — AGOT+, Valyrian Steel, Submod Core, Nobility...
   - **AGOT: The Long Night & Azor Ahai**
   - *Optional:* Supernatural
   - *If you run Supernatural:* the [Compatibility Patch](https://steamcommunity.com/sharedfiles/filedetails/?id=3780270228) — always last

If the launcher reports a descriptor error, it is almost always the `path=` line
in the `.mod` file. Use forward slashes even on Windows, and make sure the folder
name matches exactly, including case.

## The one rule

**Disable every other Long Night mod.** *AGOT: The Long Night* and *The Long Night+*
have to be **unchecked in your playset** — not sorted below this one, disabled.
This mod is a fork of both and ships files at the same paths, so either of them
loaded anywhere overrides it with older code.

## Multiplayer

Everyone in the game needs the same version. Mixing a Workshop copy with a manual
copy of a different version will not match checksums and the game will refuse to
start. Check the version number in the launcher against your friends before you
host.

---

## Standing on other people's work

This is a fork. It builds on **Freeholder**'s original *AGOT: The Long Night*,
**Tehaen**'s 1.19 update, and **Wepo94**'s *The Long Night+* — and on the AGOT
team's total conversion underneath all of it. If you enjoy any of this, that is
where it started, and they deserve the credit for it.

No license is applied here, because it would not be mine to apply. The original
authors retain whatever rights they hold over their work. This is published in the
ordinary spirit of Paradox Workshop modding: freely playable, freely readable,
never sold. If you are one of the authors above and want something changed or
removed, open an issue or reach me at officialdlonem@gmail.com and I'll act on it.

## Reporting a problem

Open an [issue](https://github.com/Dlonem/CK3TheLongNightAzorAhai/issues), or say
so in the [Discord](https://discord.gg/PTJzPQbqG7) — the Discord is usually faster.
Include your CK3 version, your full load order, and whether you're on the Workshop
copy or a manual install.
