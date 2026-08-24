# Changelog

Version history for **AGOT: The Long Night & Azor Ahai**. These are the same
notes published with each Steam Workshop update, kept here so the repository
carries its own history.

Newest first.

---

## Hotfix 1.0.14

Being brought back from the dead by a red priest has never worked for a player. There were four separate reasons for that, and all four are fixed. This release also compatibility-patches AGOT 5.0/5.1, makes the dead take the North in order, and repairs several things that were quietly broken on older saves.

### Bug Fixes

- **Fixed dozens of empty character portraits across the mod's events.** Fifty-eight portrait slots could render blank — most visibly the dragon that turns back at the Wall, which never had a dragon in it. Every one is now either filled correctly or left out, instead of showing an empty frame.
- **Fixed the issue with red priests never offering the Lord's Blessing.** The interaction was missing the block that tells the AI which characters to consider, so it was almost certainly never evaluated once in anybody's game. Priests now weigh their liege, their court and their own kin, once a year.
- **Fixed the issue with the blessing becoming permanently useless when the priest died.** Nothing ever released the bond, so a lord whose priest died could neither be saved nor be blessed again by anyone else — silently, forever. It is now released the day the priest dies, and also if he spends himself on somebody else.
- **Fixed the issue with players having no way to ask for the blessing at all.** The interaction only ever appeared for red priests, aimed at other people. If you were not a priest yourself you could not see it and could not request it.
- **Fixed the issue with the battlefield resurrection being unavailable for most of a campaign.** It required the struggle to already be in Winter Is Coming or the Long Night, and most of a game is neither — so a blessed man who fell in a normal year was not unlucky, it simply could not happen to him. A priest's promise does not have a calendar on it.
- **Fixed the issue with two AGOT governments losing all of their modifiers.** AGOT 5.0 added the Lorathi Principality and Norvos, and this mod's government list had not followed — which quietly stripped the opinion and contribution modifiers off both of them and put 24 errors in the log. Spotted and reported by **AlbionPCJ**. The list is now generated from AGOT's own, so it cannot fall behind again.
- **Fixed the issue with the dead skipping the North.** They could cross into the Riverlands with Winterfell and half the northern holds still standing, because the only rule was "attack something next to you" and the choice was random. They now clear the North before going south, and Winterfell falls last.
- **Fixed several things that only failed on saves started before they were added.** Most of the prophecy's payoff, Beric's and Lady Stoneheart's resurrections, and a handful of others were set up once at game start and never on a load — so an older save simply never got them, with nothing in the log to say so. They are now repaired on the next yearly tick.

### Also in this update

- **New decision: Ask for the Lord's Blessing.** Available whenever a red priest who can give it is within reach — your court chaplain, a ranging company's camp priest, or anyone else in your hall. It stays visible after you have one and tells you why it is closed, rather than quietly disappearing.
- **New event: What the Red Priest Is For.** Fires once, the first year a priest who could do it is standing close enough. Nothing previously told a player the blessing existed.
- **The fire pays closer attention as the dark gets nearer.** A blessed champion can be caught in any year, but the odds tier: half weight in the Long Summer, standard once the cold winds start, and half again on top during the Long Night.
- **No faith requirement, and there never was one.** A red priest can spend himself on a man who does not believe a word of it.
- **You are now told what is happening to you, in three parts.** A card when you go down, your priest's decision two days later, then a second card telling you what they chose — and coming back is your button to press, not something that happens off-screen at five speed. A refusal arrives the same way, and the death is on that card rather than on nothing at all.
- **A red priestess may want something for it.** Where she is willing, an extra option lets her spend herself on a man and make sure he knows what it cost her. It never replaces the plain choice.
- **Red priests no longer need to be prominent to do this.** Lowered to piety level 1, or a learning of 10, from a threshold tuned for a landed ruler rather than the landless holy woman who is usually the one standing there.
- **A red priest now looks for the person the story needs, not the person with the biggest title.** He weighs deeds, courage, skill at arms and the Lord of Light's own virtues, but also the marks of someone the world is already pointing at: a Valyrian steel sword, the blood of the dragon, dragon dreams, greensight. A landless wanderer carrying any of that is worth more to him than a comfortable duke. He will never settle for a random courtier — if nobody in reach is worth his one life, he waits another year.

### Note

- Works with AGOT 5.0 and 5.1, and still works on an older AGOT.
- Safe to drop onto a running save. If your priest died at some point and you have been quietly unblessable ever since, the next yearly tick releases you.
- If the battlefield resurrection still does not complete, please open an issue. The four causes above are fixed and every branch of that path now writes a trace to the debug log, but it has not yet been observed end to end in a live game.
- What the blessing does: if you fall in battle, your priest gets the chance to argue about it. It is not a shield — you can still be wounded or maimed on any roll it does not win, it can only happen to you once, and the priest still has to choose to spend himself.

---

## Hotfix 1.0.13

A Game of Thrones updated to 0.5.1 and moved several things this mod was reading. If you have that update, you want this one.

### Bug Fixes

- **Fixed the issue with river travel along the Rhoyne being unavailable.** The base mod added a Rhoynar Sailing innovation to gate it; this mod was carrying an older copy of that rule and quietly switching it off for everyone.
- **Fixed the issue with Lorath, Rhoynish and several royal titles rendering incorrectly.** Princes' scions, royal spouses and the Dragonstone heir were all affected. The mod's title override was one base-mod version behind and was swallowing eight of their title names.
- **Fixed the issue with dragons raised by the Night King no longer resembling the dragon that died.** 0.5.1 moved where a dragon's appearance is stored, and the undead-dragon code was still reading the old place — so a raised Vhagar came back with a stranger's face.
- **Fixed the issue with the restoration pass repainting named dragons in their old colours.** 0.5.1 retuned all 72 named dragons and added thirteen new colour channels. The reference table has been rebuilt from their current values.
- **Fixed the issue with the yearly sweep re-rolling the face of an existing undead dragon.** The check it used to decide whether a dragon needed repairing became true for every dragon under 0.5.1.
- **Fixed the issue with the Others' dragons losing their pale colouring.** The base mod's own migration fills in the new colour channels after thirty days and would have decided how they look. They now carry their own.
- **Fixed the issue with the Great Other's portrait missing ten of the new dragon genes.**
- **Fixed the issue with a player raised as a wight continuing to play as one.** They are now handed off to an heir, as intended. That rule had been in the mod for months and had never actually run.

### Also in this update

- **The mod no longer ships its own copy of the base mod's rules file.** It was carrying 62 of their rules in order to change 7, which meant every change they made to the other 55 silently never reached you — the Rhoyne travel bug above is exactly that. Only the rules this mod actually changes ship now. Everything else follows the base mod directly, from here on.

### Note

- Safe to drop onto a running save. No action needed from the player.
- If your error log is larger after this update, that is the base mod's new dragon genes meeting older portrait data across the whole mod stack. It is cosmetic and it is not this mod.
- The dead can still open a front in a new region before finishing the one they are in. Known, and being worked on for the next release.

---

## Update 1.0.12

### New Features

- **Added a second route to Lightbringer.** A champion of R'hllor carrying a Valyrian steel blade can consecrate it without a forge, at the cost the first forging demanded
  - The blade keeps its own name, history and house
  - Dawn is excluded from this route and asks a different price of whoever carries it
  - Only one Lightbringer can exist in a game; completing either route closes the other
- **Added the Night King's spear.** If the dead field no dragon of their own, he can bring a dragon down on the battlefield
  - Every dragonrider present is a valid target, commanders and knights alike
  - Hit chance scales with the size of the dragon, from roughly 40% against a hatchling to 5% against a dragon of Balerion's size
  - Hit chance increases beyond the Wall
  - Rider survival is calculated from prowess, physique, dragon size and prophecy traits; survivors are severely wounded
  - A dragon brought down this way is taken rather than killed, and returns under the Night King with its own name, age and rider history
  - Added a follow-up event for the surviving rider, with an additional option for champions of R'hllor
- **Added travel danger to territory held by the dead.** — Lyon, Dlonem
  - +60 travel danger in counties held by the Others, and in all land beyond the Wall once the invasion begins
  - +25 travel danger in counties bordering their territory
  - Danger is visible in the travel planner before a route is committed
- **Added two travel events for crossing that ground** — an encounter with wights, and an encounter with one of the Others
  - Surviving an encounter with an Other requires dragonglass or Valyrian steel

### Reworks

- The Great Ranging now stays visible on the Lord Commander's decision list during its cooldown and states the reason it cannot be taken
- Reduced the Great Ranging cooldown to four years during Winter is Coming and two years during the Long Night
- The Great Ranging outcomes now account for whether the Lord Commander led the expedition in person
- Added AI weighting to the Great Ranging based on the Lord Commander's age, wounds and personality
- Watch recruitment cooldown now scales with the struggle phase: one year in peacetime, two during Winter is Coming, four during the Long Night
- Added ten northern cultures to the struggle as Involved, including the giants and the children — bug
- Moved the Nightfort to the end of the keepership ladder
- Increased the frequency of named red priests, weighted by progress through the prophecy
- Rebalanced struggle phase county modifiers to +5% in the Long Summer, −5% in Winter is Coming, and −10% in the Long Night
- Renamed "Open Another Castle" to "Restore a Ruined Castle"

### Bug Fixes

- Fixed the issue with the Others ceasing to attack after capturing the Wall — dewi1994, Grantma
- Fixed the issue with the dragonglass decision applying its modifier to dragons — Keir Starmer
- Fixed the issue with historical dragons rendering with missing layers as they aged, caused by the 1.0.11 appearance repair writing to records that are intentionally left blank. Affected records are restored automatically — thefoxking554, MPREG
- Fixed the issue with dragons receiving the wight trait when caught in territory held by the dead. Affected dragons are restored automatically
- Fixed the issue with the ranger camp being placed at the character's previous location after taking the black
- Fixed the issue with children and close family following a character to the Wall instead of passing to the heir
- Fixed the issue with four Wall castles becoming permanently unavailable once the Nightfort was granted
- Fixed the issue with a dragon refusing to cross the Wall being triggered months after the crossing
- Fixed three on_action handlers that had never executed
- Fixed the issue with the woods witch failing to be created, which broke two follow-up events
- Fixed the issue with Night's Watch camps failing to construct their assigned buildings
- Fixed 24 missing English localization entries
- Fixed the issue with two Night's Watch events displaying an empty portrait
- Fixed the issue with the consecration decision displaying its internal key and having no cost
- Fixed the issue with the Great Ranging reporting an expedition as still active after its return
- Fixed the issue with the War for the Dawn requirements panel displaying raw script tokens — Lyon
- Fixed the issue with dragons raised from a corpse being created at age zero
- Fixed the incorrect use of "crow" in Night's Watch dialogue

### Compatibility

- Fixed the issue with rulers added by other submods displaying MISSING TITLE LOC. Unknown rulers now display as Lord or Lady, for every mod in the playset — Buggyriot
- Russian localization covers content through 1.0.11. Text added in this update displays in English until the next translation pass

---

## Update 1.0.11a

A localization sweep across the three cards that mark the turn of the age, plus the prophecy events that name you.

### The three cards now know who you are

- **All three fullscreen cards are written for your place in the world.** The card in the long summer, the one when Winter Is Coming, and the one when the Long Night begins each now have separate text for the Night's Watch, the free folk, the North, Targaryen blood, followers of R'hllor, landed lords, and landless adventurers. Most of these events previously had two or three variants, and everyone else shared one generic version.
- **The long summer card and the Winter Is Coming card change their backdrop to match** — the Wall, the lands beyond it, a heart tree, the Dragonpit, a night fire, a council chamber, or open farmland. The Long Night cards keep one image throughout; by then the answer is the same everywhere.
- **Landless adventurers are no longer told what "my maester" said.** An adventurer can carry a titular title, which was quietly handing them a landed lord's text.

### Being named

- **The priest who names you is a person now, with a name and a portrait.** The same one comes back when the realm starts agreeing with them, and again when they begin to have doubts. These events previously had no portraits at all.
- **A Red Priestess on your council counts as your red priest.** The check required a specific trait most appointed chaplains never carry, so the game could show you a Red Priestess on your council while the mod insisted you had none. This affects the whole naming ladder, the pledge and conversion events, and the Lightbringer checks.
- **The naming events say plainly what is being claimed**, and which of the nine marks were counted to get there.
- A prophecy event was showing the wrong text to characters with dragon dreams.

---

Earlier versions predate this repository. Their notes are on the
[Steam Workshop change notes page](https://steamcommunity.com/sharedfiles/filedetails/changelog/3780269495).
