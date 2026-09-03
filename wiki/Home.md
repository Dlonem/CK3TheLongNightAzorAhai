# AGOT: The Long Night & Azor Ahai

**AGOT: The Long Night & Azor Ahai** is a submod for *A Game of Thrones*, the Crusader Kings III total conversion, that builds the Long Night into a complete endgame: an undead invasion whose wights are named characters, a Night's Watch you can play from the inside, a scripted collapse of the Wall, a Trial-of-Seven melee against the Night King, and the Azor Ahai prophecy as a working mechanic that every character in the world is measured against.

It is free, it is on the Steam Workshop, and it has shipped twenty-nine updates since 8 August 2026. The current version is **1.1.0a**. It requires *A Game of Thrones* and Crusader Kings III 1.19.0.6, is safe to add to a running save, and is available in English and Russian.

> **The full reference for this mod is its page on dlonem.com: [dlonem.com/mods/the-long-night](https://dlonem.com/mods/the-long-night).** That page has the screenshots, the video showcase, the manual install guide and the FAQ. This wiki mirrors it, carries the complete version history, and exists so that the documentation lives beside the code.

| | |
|---|---|
| **Developer** | [Dlonem](https://dlonem.com) (Dlonem LLC) |
| **Game** | Crusader Kings III 1.19.0.6, with *A Game of Thrones* |
| **First release** | 8 August 2026 |
| **Current version** | 1.1.0a — *One Host* (3 September 2026) |
| **Steam Workshop** | [3780269495](https://steamcommunity.com/sharedfiles/filedetails/?id=3780269495) |
| **Manual install** | [dlonem.com/mods/the-long-night/download](https://dlonem.com/mods/the-long-night/download) |
| **Source** | [github.com/Dlonem/CK3TheLongNightAzorAhai](https://github.com/Dlonem/CK3TheLongNightAzorAhai) |
| **Discord** | [discord.gg/PTJzPQbqG7](https://discord.gg/PTJzPQbqG7) |
| **Languages** | English, Russian |
| **Lineage** | Fork of *The Long Night+* (Wepo94), itself a fork of *The Long Night (Resurrected)* (Tehaen), itself a port of *AGOT: The Long Night* (Freeholder) |

---

## Contents

1. [Before you play: one rule](#before-you-play-one-rule)
2. [The invasion](#the-invasion)
3. [The struggle: four phases](#the-struggle-four-phases)
4. [The Night's Watch](#the-nights-watch)
5. [How the Long Night ends](#how-the-long-night-ends)
6. [Azor Ahai and the prophecy](#azor-ahai-and-the-prophecy)
7. [After the Dawn](#after-the-dawn)
8. [Game rules](#game-rules)
9. [Installation and load order](#installation-and-load-order)
10. [Compatibility](#compatibility)
11. [What the mod overrides in AGOT](#what-the-mod-overrides-in-agot)
12. [Version history](#version-history)
13. [Credits and lineage](#credits-and-lineage)

---

## Before you play: one rule

**Disable every other Long Night mod.** *AGOT: The Long Night* and *The Long Night+* must be unchecked in your playset — not sorted below this mod, disabled. This mod is a fork of both and ships files at the same paths, so either of them enabled anywhere in your list overrides it with older code and brings back the see-through dragon bug. You can unsubscribe from them entirely; this mod replaces both.

Everything else about setup is on the [Installation and Load Order](Installation-and-Load-Order) page and, with troubleshooting for GOG, Epic and Game Pass copies, at [dlonem.com/mods/the-long-night/download](https://dlonem.com/mods/the-long-night/download).

---

## The invasion

The Long Night here is not a doom counter and a stack of skeletons. It is an invasion with characters, politics and a body count you recognise.

**The Night King is a character.** He has a court, a culture (the *frostborn*, with their own traditions and a deliberately Bronze-Age innovation history — the dead do not learn), a faith (the Cold Gods), a realm title, and a face built for him by a player of the mod. He leads his own host in person; a standing command bonus and the invasion-strength rule set his advantage, damage and toughness. Every Night King after the first inherits the same bonuses, so killing him with ordinary steel does not leave the dead weaker for it.

**Wights are characters, not troops.** Every lord the dead beat gets back up wearing his own face, keeping his own titles, ruling his own realm under a new liege. Wights carry a government of their own (unplayable by design — a player who is raised hands off to an heir), their own portraits and their own rot. Since 1.1.0a the dead are one host: they do not declare war on each other, they keep no alliances with the living, and no living man serves one of them as knight, councillor, court official or commander.

**They raise what they kill.** A dragon brought down over ground the dead hold comes back — same name, same face, the wrong colour and the wrong rider. If the dead field no dragon of their own, the Night King can bring one down himself: the spear, added in 1.0.12, targets any rider on the field, hits somewhere between forty percent of the time against a hatchling and five percent against something Balerion's size, climbs beyond the Wall, and takes the dragon rather than killing it. The rider rolls to live.

**The Wall comes down on camera.** A scripted collapse at Castle Black, not a notification — and thirty days later a card that opens in your own station, whether you were a sworn brother on the Wall that morning, a free folk chief, a dragonrider, a northman, a red priest, a lord, or nobody at all. The Wall is also a ward: a rider can force a dragon across it while it stands (the AI is likelier to try the less it knows), a Night King met beyond an intact Wall is near-certain to take that dragon, and once the Wall is breached the ward is gone.

**His host grows with his conquest.** Twenty thousand men beyond the Wall, fifty thousand once the far north is his, a hundred thousand when the Wall falls, two hundred thousand when the North does, two hundred and fifty thousand once he holds a hundred and forty counties — those are the Standard figures, scaled ×0.75, ×1.25 and ×1.5 by the strength rule and capped at half a million, the population of King's Landing. His men cost him nothing to keep, so he can always afford to fight.

**The front marches; it does not jump.** The dead clear the North before they go south and Winterfell falls last. A great house's seat holds while the country around it does. On Standard and above, won wars take extra neighbouring duchies alongside the war goal — more of them on Strong and Insane — and every extra grab must border land the dead already hold.

**Land they hold is dangerous to cross.** Travel danger of +60 in counties held by the dead and everywhere beyond the Wall once the invasion begins, +25 in counties bordering them — visible in the travel planner before a route is committed — with encounter events for wights and for one of the Others. Surviving an Other on the road takes dragonglass or Valyrian steel.

*On dlonem.com: [What you'll play](https://dlonem.com/mods/the-long-night/#invasion).*

---

## The struggle: four phases

The Long Night is a CK3 struggle with four phases, and you can watch it coming for decades. Each phase changes what your counties produce and how close the dead are; the catalyst list shows what moved the tracker.

| Phase | What it is | County modifier |
|---|---|---|
| **The Long Summer** | Peace, a counter you can see from day one, and everything you fail to do with it | +5% |
| **Winter Is Coming** | The rangings stop coming back. A warning of unknown length, which your own losses shorten. Since 1.1.0, a lone White Walker can be met on the snowfield in this phase | −5% |
| **The Long Night** | The invasion proper | −10% |
| **The Dawn** | What is left, and what it cost | — |

The world pushes the dark closer on its own: dead dragons, lost rangings, a hollowed-out Watch, an Other seen north of the Wall and believed. A quiet century still ends on schedule. A bad one ends early. What you do with the warning — dragonglass in the cellars, men and grain sent north, a realm that armed instead of arguing — is the whole difference between surviving the Long Night and being surprised by it.

*On dlonem.com: [The struggle](https://dlonem.com/mods/the-long-night/#struggle).*

---

## The Night's Watch

**Take the black, and mean it.** Lay down your lands, hand the realm to your heir, and serve. You can hold one of the Wall's castles as a sworn brother, or ride out with one of eight ranging companies — the Long, the Deep, the Cold, the Silent, the Black, the Winter, the Far and the Last — landless and oathbound, each with a real camp on the map from day one. Captains compete for First Ranger. A game rule decides whether the Watch fills the companies itself, leaves them for players, or sends all eight out from the start. The Watch is brothers only: a woman is refused at the gate.

**Decisions only the Lord Commander gets.** Call a Great Ranging north for word, and pay two hundred brothers for the answer — the outcome depends on whether he led it himself. Or send a sworn brother gate to gate down the length of Westeros, asking every great lord the old question: how full are your dungeons, and what were you planning to do with the men inside them? Man an empty castle. Restore a ruined one.

**Southern lords have a stake.** *Send Men and Grain* to the Watch — a cart, a season's stores, or your whole vault; the Watch keeps a list and decides what it will do for you later. *Send the Dungeons to the Wall* (1.0.16a) empties your cells onto the Wall in one order, every prisoner who can take the black, with a reason named for each one who cannot, and a game rule for whether the Wall takes counts and below or any rank.

**The Watch keeps its own house.** Sworn brothers cannot inherit or keep southern lands, cannot become regent of a southern kingdom, and a ranging captain's camp moves the way the First Ranger's does. When the dark lifts, the *Question of the North* asks whether the Watch is refounded at all — and it is only refounded if the Watch is genuinely gone.

*On dlonem.com: [Take the black, and mean it](https://dlonem.com/mods/the-long-night/#invasion).*

---

## How the Long Night ends

Since 1.1.0 the Night King is fought, not rolled. The full guide is on the [How the Long Night Ends](How-the-Long-Night-Ends) page; the short version:

1. **Beat the dead in the field once.** That opens the **War for the Dawn**, which only an independent ruler can declare.
2. **Reach him.** Winning the battle he is in opens *The Field Afterwards*: end it, form the line, or sound the retreat.
3. **The Last Hour.** A Trial-of-Seven melee in the snow — you and your companions against him and his White Walkers, blow by blow. Prowess counts for half against them. Castle steel does not bite. Lightbringer, Valyrian steel and dragonglass each open their own option and change the fight; a red priest can pull you back from it; kin and friends on your line can take the blow meant for you.
4. **Bring a bane.** Only dragonglass, Valyrian steel, Lightbringer or dragonfire destroy him. Ordinary steel casts him down and the dark crowns another. Whoever lands the killing blow is **Azor Ahai Reborn** — marks or no marks, named or not.
5. **Lose, and he keeps you.** Your character is raised as one of his before the card even opens, tells you what it felt like, and is his from then on; you play on as your heir, and a later champion may find you standing on his side of the line.

The character page remembers it: the Walker you killed, the night you faced him and lived, the steel that broke in your hand, the day the Wall fell, who paid to bring you back, and the day the dark won or lifted. When it is over, the game writes down who was actually standing there — only the men who were in the fight.

*On dlonem.com: [How it ends](https://dlonem.com/mods/the-long-night/#ending).*

---

## Azor Ahai and the prophecy

Azor Ahai is a mechanic, not a trait you tick in the ruler designer. Every character in the world is measured against the prophecy continuously, standing moves as marks are earned and lost, and the AI competes for the naming as hard as any player. The full page is [Azor Ahai and the Prophecy](Azor-Ahai-and-the-Prophecy).

**Nine marks.** Five are decided at birth — dragon dreams, greensight, born in salt and smoke, born beneath a bleeding star, and hidden blood (a Valyrian bastard raised inside a great house). Four are earned — carrying spellforged steel, waking dragons from stone, walking among the dead and surviving it, and dying without staying dead. Two are checked continuously: lose the sword or the dragon and the claim goes with it. The *Read the Signs* decision tells you which you carry, and costs nothing.

**Someone has to say it.** Deeds alone do nothing; a red priest, a witch, or a greenseer has to name you. Two marks make you **Favored of R'hllor**, four make you **Chosen** — or one and three, or three and six, by game rule. A landless red priest can formally sponsor you. Claimants carry *the Prince That Was Promised* as a nickname, and rival claimants meet, and sometimes ally.

**Lightbringer.** Forged at the price every version of the tale agrees on, or — since 1.0.12 — consecrated from a Valyrian blade you already carry, at the same price. One Lightbringer per world; completing either road closes the other. Dawn is excluded from consecration and asks a different price of whoever carries it.

**The last kiss.** A red priest can spend himself on one person, once, ever. A blessed man who falls in battle gets the argument: a card when you go down, the priest's decision two days later, and coming back is your button to press. Each return needs a fresh priest and takes more out of you. The world hears of about five such returns a year, ten once the dead are walking; asking for one yourself is never refused.

**Whether any of it was true** is decided behind the curtain — a hidden coin at game start, or set by rule — and revealed once, at the end. You can do everything right, be named by every priest in Westeros, and find out you were never him.

*On dlonem.com: [The prophecy](https://dlonem.com/mods/the-long-night/#prophecy).*

---

## After the Dawn

Surviving the invasion starts a second game. The North is scoured: ruins where the great seats stood, wilderness where the rest was. Then the **Question of the North** — restore the Night's Watch, or open the Gift to the free folk. One crown, one choice, and it sticks for the rest of the campaign. Wildling clans migrate into the empty land year by year. Landless survivors walk the Kingsroad home to rebuild their ancestral seats. You can sell colonisation rights to the Free Cities, then watch your northern vassals remember that you did. Turn the *Recurrence* rule to **The Cycle** and the Wall is raised anew, the veterans of the first dawn are known by name, and the second night comes heavier than the first.

*On dlonem.com: [After](https://dlonem.com/mods/the-long-night/#after).*

---

## Game rules

Thirteen rules, all baked in when a save is created. The full option list with the defaults is on the [Game Rules](Game-Rules) page.

**The invasion:** *Chance* (certain to never), *Moment* (a random summer, immediately, in 50 / 100 / 150 years, historical, full random, or only when you say so), *Strength* (weak, standard, strong, insane), *War Tier* (duchy, march, empire), *Resolution* (his death, or the War for the Dawn), *His Dragon* (he raises what he kills, one simply appears, or never), *Iron Throne Reformation*, and *Recurrence* (once, or The Cycle).

**The prophecy and the Watch:** *Was There Ever a Prince?* (let the flames decide, there is a prince, there is no prince), *Naming* (two and four marks, one and three, three and six, or nobody is ever named), *Claimants* (anyone, players only, one at a time), *The Ranging Companies*, and *Send the Prisoners* (tier ceiling).

*On dlonem.com: [Your apocalypse, your rules](https://dlonem.com/mods/the-long-night/#rules).*

---

## Installation and load order

Steam players should use the Workshop — one click, and it updates itself. The manual install (GOG, Epic, Game Pass) is on the [Installation and Load Order](Installation-and-Load-Order) page and in full at [dlonem.com/mods/the-long-night/download](https://dlonem.com/mods/the-long-night/download).

1. **A Game of Thrones** — required
2. AGOT submods — AGOT+, Valyrian Steel, Submod Core, Nobility, model packs
3. **AGOT: The Long Night & Azor Ahai** (this mod)
4. *Optional:* [Supernatural](https://dlonem.com/mods/supernatural)
5. *If you run Supernatural:* **AGOT: Supernatural & The Long Night Compatibility Patch** — always last

Mid-save safe to add and to update. Multiplayer works when everyone has the same version.

---

## Compatibility

Compatible with *AGOT Additional Models and Special Buildings*, *Nobility of Westeros*, *Essos Expanded*, *Legacy of Valyria* and anything else that names its own rulers; the details, and the one warning for dragon-mod users, are on the [Compatibility](Compatibility) page.

---

## What the mod overrides in AGOT

You deserve to know what a submod touches. The mod overrides nineteen named AGOT definitions — six scripted rules, eight scripted triggers, three scripted effects, one decision and one casus belli — each of them AGOT's own body copied in full with one documented change, re-checked against their current version every release. Two more (the ranger-camp domicile and the Night's Watch title-gain handler) merge with AGOT's rather than replacing them. The itemised list is on the [Compatibility](Compatibility) page.

---

## Version history

The complete notes for every release, with reporter credits, are on the [Version History](Version-History) page and on the [Workshop change-notes page](https://steamcommunity.com/sharedfiles/filedetails/changelog/3780269495).

| Version | Name | What it did |
|---|---|---|
| **1.1.0a** | One Host | The dead stop fighting the dead and keeping allies among the living; the Trial of Seven's roll call; the spear card's portraits; twelve fixes from a full playthrough log |
| **1.1.0** | The Last Hour | The melee against the Night King; being raised as an Other; White Walkers in Winter Is Coming; memories; dragons over the Wall; a host that grows with his conquest; a field kill no longer ends the Long Night |
| **1.0.16a** | The Wanderer | The Night King keeps his land and pays his men; Send the Dungeons to the Wall; a limit on resurrections |
| **1.0.16** | The Dead That Frighten You | The Others' culture; the strength rule rebuilt on advantage, damage and toughness; the tempo dial; the Last Hour becomes a duel; the War for the Dawn gated on the dead losing a war |
| 1.0.15a | — | "Missing Title Loc" fixed for every other submod's rulers |
| 1.0.15 | The Repair Release | Killing him wins the war; Azor Ahai Reborn to the right man; only a bane destroys him; the Beric track; the Night King's face |
| 1.0.14 | — | The Lord's Blessing works for players; AGOT 5.0/5.1; the North falls in order |
| 1.0.13 | — | AGOT 0.5.1 compatibility; the mod stops shipping AGOT's rules file |
| 1.0.12 | — | Lightbringer consecration; the Night King's spear; travel danger; the Great Ranging reworked |
| 1.0.11a | — | The three cards know who you are; the priest who names you has a face |
| 1.0.4 – 1.0.11 | — | The struggle, the ranging companies, the Wall's castles, Send Men and Grain, the aftermath, the Russian translation |

---

## Credits and lineage

This is a fork, and it stands on three people's work: **Freeholder**, who wrote the original *AGOT: The Long Night*; **Tehaen**, who brought it forward to 1.19 as *The Long Night (Resurrected)*; and **Wepo94**, whose *The Long Night+* added the wights, the Wall collapse and the aftermath — and on the AGOT team's total conversion underneath all of it. The Night King's face was built by a player of the mod. Nearly every fix since August 2026 started as a report in the [Discord](https://discord.gg/PTJzPQbqG7) or the Workshop comments, and reporters are credited by name in every changelog.

If the AGOT team ever ships their own Long Night, this mod will come down and point at it. If they would rather lift anything from here into the base mod, it is theirs, no strings.

Bugs and suggestions: the [Discord](https://discord.gg/PTJzPQbqG7) is fastest; [GitHub issues](https://github.com/Dlonem/CK3TheLongNightAzorAhai/issues) work too. Include your CK3 version, your full load order, and whether you are on the Workshop copy or a manual install.

Dlonem also maintains [Supernatural](https://dlonem.com/mods/supernatural) — vampires, werewolves, hybrids, hunters and witches for CK3. Everything Dlonem builds is at [dlonem.com](https://dlonem.com).
