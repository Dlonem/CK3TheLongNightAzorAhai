# Changelog

Version history for **AGOT: The Long Night & Azor Ahai**. These are the same
notes published with each Steam Workshop update, kept here so the repository
carries its own history.

Newest first.

---

## Hotfix 1.1.1 — The Watch Keeps No Land

A fix release, no new content. Every change was tested in three live runs from a mid-invasion save before it went out. Safe to add to a running game.

### Bug fixes
- The Night's Watch keeps no land. A sworn brother who inherits a county or barony outside the Wall now renounces it to its lawful lord. The Lord Commander was exempt from that rule, which is how the Watch ended up holding a random county in the North. The guard never touches the Wall's own castles, the ranging companies, the First Ranger's title or any adventurer company.
- The dead answer to nobody living. A lord raised by the invasion who still had a living liege stays independent from the day he rises, on every road in: inheritance, conquest and the yearly sweep.
- The Night King's own crown no longer refuses him. The check was asking a different question than the artifact does; it now asks the same one.
- A load-time error on the house of the Others is gone. Twenty-seven "failed to fetch a valid house" lines per load, on saves where the house had no living member yet.

### Balance
- The dead have no control problem. Every county that comes into dead hands is set to full control the day it arrives, and their land recovers control after a siege instead of never. This is the end of the peasant revolts on the Night King's side, and it also means the invasion no longer stalls waiting for one of his own rebellions to finish.
- The Others cannot run schemes. No hostile or personal schemes from the Night King, the White Walkers or the wights.
- Stannis gets Melisandre. Send for a Red Priest as Stannis and she comes if she is free; as a Baratheon lord of Dragonstone she comes three times in four. Both now qualify for the decision, and the AI takes it.

### Notes
- Russian: every key in the mod now exists in Russian. Text added since 1.0.12 shows in English until it is translated, instead of as a raw key.
- The complete reference for every mechanic in the mod, with the numbers, is now one page: https://dlonem.com/mods/the-long-night/wiki

---

## Hotfix 1.1.0b — Keeping pace with A Game of Thrones

A hotfix for this morning's A Game of Thrones update (the 0.5.2 hotfix pushed 4 September), plus one pacing fix from a full Long Night run on Strong. No new content.

### Bug Fixes
- The dead no longer spend a second winter proving a war they have already won. On a 22-year Strong run, every war south of the Wall took one to two years and paid out two to six counties — the Night King was winning every battle and holding the ground, and the scoreboard kept asking for more. An invasion war now counts its goal as held once the dead occupy six tenths of it, and from that day the war score climbs on its own, so held ground plus a won field closes a war inside a season. Nothing the living can do has changed: the defender's own war score, delay and battle cap are untouched, and a lord who keeps the dead off his land still gains on them after a year exactly as before.

### Compatibility
- The seventy-two named dragons look the way AGOT now paints them. AGOT retuned thirty-eight appearance values in its curated dragon table — mostly fire colour, plus a few scale and horn tones on Sunfyre, Tessarion, Vermithor and Arrax. This mod keeps a copy of that table to repair dragons whose stored appearance has gone blank, and it now matches theirs exactly.
- A camp with a dragon in it cannot be moved beyond the Wall. AGOT added this rule today and this mod's copy of the camp-moving rule now carries it — with the two exceptions the rest of this mod already makes: once the dead hold a piece of the Wall the ward is broken and the door is open, and a rider who already forced a dragon over the Wall is not refused a second time.
- Dragon eggs are held by the right people. AGOT changed one line in its portrait animations (who may be shown cradling an egg) and this mod's copy of that file carries the same line.

### Notes
- Safe to drop onto a running save. The pacing change applies to wars declared after you load, not to one already in progress.
- Every scripted rule, effect, trigger, on_action and event this mod shares a name with was re-diffed against the new AGOT build; the rest are current.

---

## Hotfix 1.1.0a — One Host

No new content. Twelve fixes to things 1.1.0 shipped with. The first group are one idea from several directions — the dead are one host: they do not sue each other for land, they do not besiege each other, and nobody keeps a friend on that side of the line. The rest come out of a full playthrough log (a Trial of Seven, a dragon speared out of the sky, and the Night King beaten in the snow), triaged file by file.

### The dead stop fighting the dead

- **The Others no longer declare de jure wars.** 1.0.16 gave the frostborn culture `innovation_casus_belli`, whose only effect in the entire game is to unlock `individual_county_de_jure_cb` and `individual_duchy_de_jure_cb` — no modifier, no unit, nothing else. Since every lord the invasion raises is set to that culture, the whole dead realm inherited the pair, and a Walker could sue another Walker for a county in the middle of his own invasion. The innovation is removed; none of this mod's own casus belli ever asked for one. — **MPREG**
- **And in games already running, the dead cannot fight each other at all.** A history file seeds a culture once, at game start, so the removal alone would have left every existing save unchanged. `common/scripted_triggers/zz_ln_megawar_cb_shadow.txt` shadows AGOT's `agot_mw_war_valid_during_megawar` — twenty-four lines, called from `allowed_against_character` in thirteen casus belli (all three de jure wars, claims, all three conquests, the five dragon wars, tributarize) — and refuses any war where both sides are of the dead. Existing saves are fixed on load. Deliberately *not* extended to the dead attacking the living: `wight_government` carries `government_is_tribal`, so the conquest CBs are probably already load-bearing for the pace players feel today, and weakening the Long Night is not what a hotfix is for.
- **The invasion casus belli can no longer be aimed at the dead.** All three identified them with `NOT = { has_trait = other_trait }`, which spares true Others and nobody else; a lord raised by `mutate_into_other_effect` carries `wight_government` and, as the 1.0.6a finding recorded, frequently no trait at all. He was a legal victim of the Night King's own invasion — and, by the same hole in `war_for_the_dawn_cb`, a legal declarer of the War for the Dawn against his own king. All four now use `ln_is_one_of_them_trigger`, the test the invasion's own target picker already used.

### The dead have no friends

- **The alliance ban now covers all of the dead.** `is_alliance_valid` tested two traits where `ln_is_one_of_them_trigger` tests seven, so the trait-less converted lord kept the alliances he made in life and could form new ones after death — in both directions.
- **And a yearly sweep breaks them regardless of load order.** Scripted rules resolve by name, one definition per playset, last parse wins, and at least four installed mods ship their own `is_alliance_valid` — Legacy of Valyria – AGOT 0.5.1 among them. `ln_the_dead_have_no_allies_effect` runs off the story cycle's existing yearly pulse and breaks every alliance held by every ruler of the dead, whoever won that argument. `every_ruler` rather than the Night King's own realm on purpose: the population this is for is the dead lord who is nobody's vassal.

### From the playthrough log

- **The Trial of Seven could carve the same name three times.** `ln_lh_bank_the_roll_call_effect` took positions 0, 1 and 2 out of `ln_lh_the_line` with no count guard, so a champion who went out with fewer than three men had positions 1 and 2 cap to position 0 — `ln_dawn_knight_2` and `ln_dawn_knight_3` set to the same character as `ln_dawn_knight_1`, and `ln_reveal.10` reading all three by `has_global_variable`. 1,726 lines of `Given position was bigger than the list` in one session. Each position now carries a matching `count >=` guard, and the empty slots are cleared — they are globals, and a second melee would otherwise inherit the first one's men.
- **"The living do not serve the dead" was never enforced.** `ln_may_serve_trigger` shipped in 1.1.0 as a `trigger_if` / `trigger_else_if` chain with no closing `trigger_else`, which CK3 fails at PostValidate — 40 errors a session, and the A2.1 mirror clause inert at all four call sites (knight, court position, council seat, command). Closed with `trigger_else = { always = yes }`, and a validator for the whole mod now checks the shape (0 other instances).
- **`ln_spear.1` gets its portraits back.** `game/gui/event_windows/fullscreen_event.gui` is 352 lines and contains the string "portrait" zero times — the window has no portrait container of any kind, and no mod in the playset overrides it. So the card's `left_portrait` (the dragon), `right_portrait` (the Night King) and `lower_left_portrait` parsed, threw nothing and drew nothing, defeating the exact thing the 1.0.12b note says the card was built for. Moved to the default character-event window; `override_background` works there (vanilla `ep3_decisions_events.txt:2712`), so the frozen forest is kept. AGOT's own `agot_dragon_character_event` window was considered and rejected: it puts the dragon in the *right* slot, which would mean swapping the Night King into a dragon-shaped frame.
- **`ln_spear.1` and `ln_dawn.2` no longer land on the same day.** Both hang off `on_combat_end_winner` and both were `days = 1`, so the confrontation card could be read before the spear card and describe a dragon the dead had already taken — Thomas's `ln_dawn.2` debug panel still had `ln_dawn_dragon` saved as the speared dragon. `ln_dawn.2` moves to `days = 2`; ordering in the hook was rejected because `ln_dawn_combat` runs before `ln_others_spear` (`zz_ln_00_hooks.txt:226`) and reordering sub-lists moves which saved scopes exist when. `ln_dawn.5` stays at day 3, `ln_dawn.12`'s failsafe at +14/16.
- **`flee_noble_south_effect` read `root` on a road where root is a story.** Called through the yearly service net, the execution root is the story cycle, so `culture = root.culture`, `faith = root.faith` and `FLAVOR_CHAR = root` were reaching for it — 97 errors across two signatures. The lord is now banked with `save_temporary_scope_as` at the top of the effect and read by name.
- **The struggle clock backstop poked a struggle that had ended.** `struggle:ln_long_night_struggle ?=` still resolves to a weak, invalidated handle after `end_struggle`, so the whole monthly body was entered six seconds after the Dawn. Guarded one level up, in `ln_struggle_monthly_work_effect`, on the same `ln_struggle_concluded` global that 1.0.16 introduced for exactly this reason.
- **The snowfield encounter could draw the same companion twice.** Same defect class as the roll call, at `ln_enc_man_2` / `ln_enc_man_3`; guarded, and the three lower portraits now carry `exists` triggers.
- **`ln_crown_the_next_nightking_effect` compared against `root` on the story-cycle road.** Its header says root is the man being crowned; on the `on_owner_death` road root is the story, so the `NOT = { this = root }` in the second-king demotion sweep was never true there and a successor already wearing `nightking` was demoted and re-crowned in one pass. Banked as `scope:ln_the_crowned`. Found by a static sweep of every effect transitively reachable from the story cycle for bare `root` — two hits, the other (`agot_spawn_adult_ice_dragon_effect`, `root.story_owner`) is correct for its context.

### Notes

- Large playsets are worth one look at `logs/database_conflicts.log`. This mod and several other AGOT submods define some of the same scripted rules — including `has_natural_death_second_chance`, which is the entire entry point to the last kiss. This mod should load last.
- **Compatible with AGOT Additional Models and Special Buildings**, measured rather than assumed: 271 of their script symbols against 932 of ours, one shared on_action (`on_game_start_after_lobby`, and both sides use the merging sub-list form), zero same-path files, zero localization collisions. Their Night's Watch content is a new decision and a vassal interaction, both routing through AGOT's own `agot_add_to_nightswatch_effect`. — **lilv1314**

---

## 1.1.0 — The Last Hour

The big one. The Night King is no longer a dice roll: he is fought on foot, in the snow, by you and the people who were actually there, and losing to him is worse than dying. Underneath it, the largest fix pass this mod has had — a full audit of what fires, what never fired, and what the base game had quietly overruled.

This release also contains everything from hotfix 1.0.16a, listed separately below.

### Features

- **The Last Hour.** Reaching the Night King opens a Trial-of-Seven-style melee: you and your companions against him and his Walkers, blow by blow. Castle steel does not bite. Lightbringer, Valyrian steel and dragonglass each open their own option and change the fight; a red priest can pull you back from it; kin and friends can take the blow meant for you.
- **Raised as an Other.** Lose to him and he keeps you — your character is turned before the card opens, tells you what it felt like, and is his from then on. Later champions may find you standing on his side of the line.
- **White Walkers in Winter Is Coming.** Rangers and northern lords can meet a lone Walker before the dead take a single county: a small melee, one Walker against a handful of men, with the Sam Tarly outcome in the deck.
- **Memories.** The character page now records the things worth remembering: killing a Walker, facing him and living, your steel failing against him, being alive when the Wall fell, coming back from the dead and who paid for it, the day the dark won, and the day it lifted.
- **Dragons over the Wall.** A rider can force a dragon across a standing Wall — the AI is likelier to try it the less it knows — and once the Wall is breached the ward is gone.
- **The Wall falls, and the world is told.** The monument card now opens in your own station — sworn brother, free folk, dragonrider, northman, red priest, lord or nobody.

### Reworks

- **The Night King's host grows with his conquest** — 20,000 beyond the Wall, 50,000 once it is his, 100,000 when the Wall falls, 200,000 when the North does — scaled by the invasion strength rule and capped at half a million. His men cost him nothing to keep; he can always afford to fight. Raised by **Enigmatic Clown**.
- **A field kill no longer ends the Long Night.** Ordinary steel casts him down and another is crowned; only a bane destroys him. Beating him in the field does, however, open the War for the Dawn.
- **Advantage across the four strength rules is now 10 / 15 / 20 / 20.** One Night King at a time, one War for the Dawn at a time.
- **The dead employ nobody and serve nobody.** A living lord can no longer sit on the Night King's council or hold his court positions, one of them can no longer hold a place under a living lord, and any living vassal the dead pick up by conquest is taken within the year.

### Bug Fixes

- **The endgame respawn.** A gate that ran inside on_death asked a dead man's death reason before he was dead, failed every time, and crowned a new Night King on every sanctioned kill. The war never ended and Azor Ahai was never granted.
- **Three overrides that had never run.** The Watch-restoration override, the Night's Watch title-gain hook and the siege hook had been losing their parse races to base AGOT since the fork. Moved to where they win.
- **The Cycle.** The aftermath switch was never cleared between waves, so a second Long Night ran with half its machinery locked. Cleared at every opening.
- **Faces and stacking.** The Night King and White Walker faces replaced; foreign-mod genes that had shipped since 1.0.x stripped; wight government no longer errors on tribal holdings; several permanent modifiers no longer stack; a card that had lost its portraits and theme to a parse error is whole again.
- **Text.** Dragons are no longer all "she"; no clocks; options tightened; the prisoner count on Send the Dungeons to the Wall is now actually shown.

---

## Hotfix 1.0.16a — The Wanderer

A hotfix off two log sets and a week of reports. One of these was shipped in 1.0.16 itself; another had been quietly ending the Long Night early for anyone unlucky enough to win a small fight.

### The Night King

- **He keeps his land.** The invasion handed him his fifteen counties before it handed him his realm title, so through that whole setup he counted as a mere count — and AGOT caps a count at one settled county, turning the rest back into wilderness. Fresh games have nothing settled beyond the Wall, so nobody saw it. Old saves do, and he was stripped inside a day. Reported by **Achillyz**, **Matt** and **Mat.gopack**.
- **He answers to nobody.** Those same grants left him standing wherever the previous holder sat in the pecking order, so the Others could arrive as somebody's vassal — usually a wildling king's. He is now made independent at setup. Reported by **Mat.gopack**.
- **He can pay his men again.** 1.0.16 gave the Others' culture its traditions, and one of them carried a heavy monthly prestige drain. His government buys and reinforces men-at-arms with prestige, so his host could never recover after a battle. Reported by **Enigmatic Clown**.
- **The post-Dawn land cleanup can no longer run mid-invasion.** It only ever checked whether the Others' realm title had a holder, so any moment that title sat empty read as "the dark is over".

### The ending and the Wall

- **Beating a small detachment no longer ends the Long Night.** The killing-blow scene fired whenever anyone won a battle against a side he owned — he did not have to be in it. He now has to actually be on the field. Reported by **RedSaintNino**.
- **The Question of the North no longer takes the Wall off the living.** If wildlings hold Castle Black when the dark lifts, that is a thing they did. It refounds the Watch only when the Watch is genuinely gone. Reported by **RedSaintNino**.

### Features

- **Send the Dungeons to the Wall.** One decision, every prisoner who can take the black. It tells you why when it cannot — four reasons, each one named — and it is an order, not an offer.

### Reworks

- **A limit on how many people the red priests can bring back.** Nothing in the mod ever counted how many priests exist, so resurrections scaled with how far R'hllor had spread. The world will now hear about five a year, ten once the dead are walking. Asking for one yourself is never refused and never counts against it. Raised by **Ser Brinda "the Bad Apple"**.
- **Ten game rule descriptions rewritten to fit** the fixed box CK3 gives them. Reported by **Diomedian_Swap**.

---

## 1.0.16 — The Dead That Frighten You

1.0.15 made the ending reachable. This one makes it cost something. The Others are a real army now, the invasion moves at the pace the difficulty setting promises, and the Last Hour is a duel you can lose. Underneath all of that, a pile of text that was never showing up finally does.

This release also contains everything from hotfix 1.0.15a, which went out on the Workshop between releases and is listed separately below.

### The Others

- **The Others' culture has traditions and an innovation history.** It had neither — no traditions at all, and not one innovation — which capped the Night King's men-at-arms types at the bottom of the ladder while every realm he invades sits at the top. Reported by **Zobertus**.
- **Rebuilt the strength game rule.** Weak through Insane were one field each, levy size, and levies cannot take a castle. They now carry advantage, army damage, army toughness and knight effectiveness.
- **Cut Insane's headcount by roughly 5x and raised its combat power.** Choosing a setting your machine can run should not also mean choosing the easy game. Raised by **Corvo**.
- **Doubled the dead's per-man siege contribution**, so a smaller host grinds a castle down at the same rate.
- **Every Night King after the first inherits the standing command bonus and the wave escalation.** Both were applied once, at setup, and never again — so killing him made his heir permanently weaker.
- **Both undead units have their counter tables.** They shipped empty.
- **Raised the Night King's domain limit and pinned his dread at maximum.**
- **The Night King has the trait he was written with.** His history file gives him both Callous and Sadistic, the game treats those as opposites, and Sadistic was silently thrown away every load — costing him the prowess he was meant to bring to the duel. Callous is gone and Sadistic stays.
- **His name shows up.** It was printing a raw key.
- **Cut the invasion's trebuchet train from 1,000 men to 100.** Siege strength takes the highest tier in the army and the Ice Spiders already matched them, so the rest were buying nothing.

### The pace of the invasion

- **The strength rule now sets the tempo of the conquest, not only the size of the host.** Measured from a full Strong run: the dead reached year twenty-three of the Long Night holding twelve northern counties — one small war roughly every twenty months — and the North was still standing when the Night King fell.
- **Won invasion wars take extra neighboring duchies alongside the war goal.** One on Standard during the Long Night; one on Strong during the Cold Winds and two during the Long Night; two on Insane in both phases. Weak keeps the old one-goal march. A duchy holding a living great house's seat is never taken as a bonus, and every extra grab must border land the dead already hold — the front marches faster, it does not jump.
- **Kingdom-tier invasion wars pay the extra grabs too.** They were only ever wired into duchy wars, and since 1.0.14 nearly every southern war is fought at March tier, so the dial would have missed almost every war the dead actually fight.
- **Cut the pause between southern wars on Strong and Insane to 1–3 months**, from 2–6.
- **Cut the freeze after a lost war on Strong and Insane to 6–18 months**, from 1–3 years. The endgame still opens the moment the dead lose once, on every difficulty.

### The Long Night's ending

- **The Last Hour is a duel now, not a button.** It read "End the Long Night" and killed him with no roll. It reads "Go in for the kill" and can go wrong. Raised by **MPREG**.
- **Dragonglass is no longer as good as Valyrian steel.** Carrying only obsidian makes the duel materially harder.
- **The man who can actually hurt him is the man who gets sent.** Carrying dragonglass, Valyrian steel or a dragon was worth exactly as much as being crippled was worth against you, so the two cancelled — and a hale knight carrying nothing that can scratch the King of Winter would win the pick over a wounded man holding the one weapon in the realm. He'd reach the confrontation with no way to end it.
- **Knights sworn to a lord who can't fight are eligible again.** If the lord himself was dead, a child, or a dragon, his entire retinue was skipped along with him — so Jon Snow riding under the wrong banner was never a candidate.
- **AI champions can reach the confrontation.** It required a human commander, so Jon Snow could never fight him.
- **Dragons can no longer be chosen as the Dawn's champion.** A dragon that won the ordering could break off and leave the Long Night unendable. The dragon is still named in the record if its rider strikes the blow. This now covers the captor as well, who was the one candidate with no check on him at all.
- **The field scene can't be lost anymore.** It is offered once per wave, and it was marked as offered a full day before the card actually arrived — so a commander who won the battle and died that night took the mod's flagship scene with him for the rest of the wave, silently. It re-arms now if the card never lands.
- **Fixed the kill being credited to the war's leader** instead of the champion the story picked, when the champion's scene was lost.

### The War for the Dawn

- **Only independent rulers can declare it.** There was no tier, liege or independence check at all, which is why the Hightowers kept declaring it. Reported by **KhanSaru**.
- **It cannot be declared until the dead have lost a war.** Beating them in the field is now the thing that opens the endgame.
- **Reduced its battle war score from 300 to 200.** Upstream's version of that line was misspelled and never did anything, so the number had never actually been played.

### The Last Kiss

- **A returned man can be blessed again.** The player-facing route still refused anyone who had already come back once, so after one return you were locked out of the track. Reported by **Juring**.
- **Added a commander-side entry to the battlefield interception.** It covered knights only. Reported by **Juring**.
- **Dragonglass mining is open to landless rulers, including Night's Watch rangers.** It required land, which shut out adventurers and the Watch — the two people most likely to need it. Landless rulers also stop being charged a duke's price.

### Fixes

- **The red priest actually turns up.** Sending to Essos for one has been quietly producing nobody: the priest was created into a court that couldn't hold him, the game refused him, and nothing said so. He's born in your lands now and then walks into the hall — which matters, because seating him as Court Chaplain is the road to being named Chosen.
- **The Iron Throne is no longer asked to swear fealty to itself.** The reformation card went to every independent Westerosi lord, and the king is one — same face in both portrait slots, and the option did nothing when taken.
- **Feeding the Watch no longer charges you for nothing.** Two of the three replies to a wandering crow paid out an opinion change to whoever holds the Wall without checking that anyone does. One of them takes 50 gold first.
- **Living rulers left on a Risen Thrall government are restored to a normal one.** They were being detected as dead every year and having their counties scoured. Reported by **MPREG**.
- **Death by the Dawn now has text.** It printed raw keys in the kill record. Reported by **MPREG**.
- **All twenty struggle phase descriptions now appear.** Every phase was printing raw keys.
- **Restored twelve portrait genes removed in an earlier version.** They still existed in saved characters and ruler designer files, which threw errors on every load.
- **Stopped overriding three of AGOT's textures.** One replaced the eye map for every male character in the game; another was quietly altering AGOT's greying hair.
- **Under The Cycle, a second Long Night now starts clean.** The roll call of who stood at the last dawn carried over into the next one — naming men decades dead as having been there — and the new gate on the War for the Dawn stayed unlocked against a Night King who had beaten nobody.
- **The Cold Winds rumours stop burning their own cooldown.** Once you had seen all the cards in your region, the pulse still spent its two-to-four-year silence on an empty roll.
- **Halved the Others' background processing.**
- **Added missing text** for the Scouring war, the undead crime opinion, the Ice Spiders' description, and a faction line missing from the base game.
- **A pass of guards across the error log.** The Wall's collapse, the wight conversion, the Night's Watch fleeing south, the Others' portraits, the aftermath's settlers, and the atmosphere pulses all had places where they read something that wasn't there. None of it broke play; all of it was noise between you and a real bug.

Reported by **KhanSaru**, **Zobertus**, **Corvo**, **MPREG** and **Juring**. Keep them coming — the Discord is the best place for logs and screenshots.

---

## Hotfix 1.0.15a

Submod compatibility, and two event cards that were showing you raw code instead of names. Workshop players got this one between releases; it is included in 1.0.16 above.

### Compatibility

- **Fixed "Missing Title Loc" on rulers added by other submods.** This mod used to redefine the effect AGOT uses to name every ruler in the game. Only one copy of that can exist in a playset and ours was the one that won, so any other submod adding titles to it lost them — quietly in most cases, and as a visible error wherever the other mod also added a government of its own. It no longer redefines it. Essos Expanded, Essos Expanded: The Further East, Legacy of Valyria, Nobility of Westeros and anything else that names its own rulers now work alongside this mod with no patch needed from either side, and load order does not matter. Wights, ranger captains and wardens are unaffected. Reported by **MAGNUM** and **Buggyriot**, and diagnosed from the other side by **TXMaverick** of Essos Expanded — thank you all three.
- **Any ruler this mod still cannot name reads "Lord" or "Lady" rather than a warning string.** A safety net for submods nobody has told us about yet. A developer's error message does not belong in a player's UI.

### Bug Fixes

- **Fixed names showing as raw code in three event cards.** "A Face I Know", the fallen-friend card after a battle, and the last-kiss card were written with a token form CK3 does not read, so the dead man's name came through as bracketed script instead of a name. 82 of them across English and Russian. Thanks **Ō**.
- **Fixed "A Sword Drawn From Fire" naming a priest it had not chosen.** The card asked "do you have a red priest?" one way and looked one up another, stricter way — so a chaplain who counted for the question but not for the lookup produced a card full of blank names with a woods witch's portrait next to them. Both now use the same rule. Thanks **Ō**.

### Note

- Safe to drop onto a running save. Titles and event text are worked out fresh every time they are drawn.
- Nobility of Westeros and Essos Expanded: The Further East replace the same file as each other, so those two conflict independently of this mod. That one is not something we can fix from here.

---

## 1.0.15 — The Repair Release

Mostly about making sure everything the mod already promised actually happens. A lot of what follows was built in earlier versions and then never quite reached the player — a missing block here, a scope that silently did nothing there. Existing saves are fine; the fixes repair themselves as you play.

### The Long Night now ends properly

- **Fixed the issue with killing the Night King invalidating the War for the Dawn instead of winning it.** His death tore down the Others' kingdom title, and the war then looked at a defender who no longer held anything and threw the whole thing out — a won war that vanished with nothing to show for it. Reported by **erine120**.
- **Fixed the issue with Azor Ahai Reborn going to the wrong person.** The title went to whoever happened to be leading the war rather than to whoever had actually earned it. Reported by **breakfastenjoyer**.
- **The ending happens on screen now, every time.** Whether you win on war score or take him alive, the worthiest champion is chosen — weighed by deeds, blessings, Lightbringer, Valyrian steel and wounds — and strikes the final blow himself.
- **He can only be destroyed by dragonglass, Valyrian steel or dragonfire.** Kill him with ordinary steel and he is cast down rather than destroyed: the dark crowns another, and the Long Night goes on.
- **The confrontation is a real duel now, not a coin flip.** Prowess is a genuine contest, and an outmatched champion always keeps a chance — that is what the songs are about.
- **Fixed the issue with the dead outliving the Long Night.** Wights, undead dragons and Others are now removed when it ends, however it ends. Existing saves clean themselves up on the next yearly tick.

### Bug Fixes

- **Fixed the issue with captured Others demanding trial by combat or serving as your knights.** The cold gets the sword instead. Suggested by **breakfastenjoyer**.
- **Fixed the issue with Night's Watch brothers keeping inherited southern lands.** They no longer hold the land or the claims on it, and existing saves self-heal. Reported by **NHNster**.
- **Fixed the issue with living characters getting corpse skin after a mid-save mod list change.** The undead skin rules were being applied without checking whether the character was actually one of theirs. Reported by **Ereska** and **KngZawd**.
- **Fixed the issue with the Long Night wars never resolving.** Taking the enemy's seat now wins the war. Previously the dead won every battle and got almost no credit for it, so sieges dragged for years with the war score barely moving.
- **Fixed the issue with the dead storming great seats out of nowhere.** A seat holds while the country around it does, so they have to take the countryside before they can come for Winterfell.
- **Fixed the issue with AI realms never arming themselves with dragonglass.** The decision existed and was effectively unreachable — checked too rarely, blocked by a money test that ignored what year it was, and never weighted by whether that lord believes in any of this. All three are fixed.

### Also in this update

- **Resurrection — the Beric track.** Being returned by R'hllor is no longer once per lifetime. Each return needs a fresh priest, takes more out of you, and climbs the trait. Several bugs in the priest's own decision were fixed along the way.
- **The Night King has a face.** A proper show-inspired model, built by a player of the mod. Until now he was wearing a randomly generated one.
- **Azor Ahai Reborn carries the standing he was always meant to have.**
- **Undead dragons breathe blue fire.**

### Compatibility

- **Groundwork for AGOT: Seasons of Ice and Fire.** The two mods detect each other cleanly and nothing collides — handled inside this mod, with no separate patch to install. Deeper integration is planned. Asked for by **ashen03**.
- **Dawn can be consecrated into Lightbringer**, and is the priority blade if a Dayne carries it. Asked about by several of you; it already worked, and this confirms it.

Thanks to everyone reporting issues in the comments — nearly every fix above started as one of your posts.

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
