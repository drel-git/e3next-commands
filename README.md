# E3Next Command Guide

A searchable community reference for E3Next slash commands, INI/spell parameters, troubleshooting tools, and common usage.


> `Ctrl+F` to search: `follow`, `loot`, `buff`, `rez`, `bank`, `debug`, `hud`, `bard`, `xtarget`, `burn`, `corpse`, `memory`, `sell`, `resist`, `movement`, `ui`.

This handbook was built from:

- Existing command scrape from E3Next release notes up to v1.54, `/e3listcommands`, and wiki command notes.
- See [Rekka's E3Next Github page](https://github.com/RekkasGit/E3Next) for more info. 

---

## Table of Contents


- [Commands by Category](#commands-by-category)
  - [Assist and Combat](#assist-and-combat)
  - [Movement and Following](#movement-and-following)
  - [Bot Broadcasts and Groups](#bot-broadcasts-and-groups)
  - [Buffs, Blocking, and Casting Requests](#buffs-blocking-and-casting-requests)
  - [Debuffs, DoTs, Dispel, and Resist Tracking](#debuffs-dots-dispel-and-resist-tracking)
  - [Burns and Cooldowns](#burns-and-cooldowns)
  - [Loot, Selling, and Inventory](#loot-selling-and-inventory)
  - [Rez, Corpses, and Wipe Recovery](#rez-corpses-and-wipe-recovery)
  - [Bard Commands](#bard-commands)
  - [UI, HUD, and Configuration](#ui-hud-and-configuration)
  - [Diagnostics and Debugging](#diagnostics-and-debugging)
  - [Veteran AAs and Utility](#veteran-aas-and-utility)
  - [Server-Specific Commands](#server-specific-commands)
- [INI and Spell Parameters](#ini-and-spell-parameters)
- [What Are You Trying To Do?](#what-are-you-trying-to-do)
- [Dangerous Commands](#dangerous-commands)
- [Global Filters and Modifiers](#global-filters-and-modifiers)
- [Common Recipes](#common-recipes)
- [Newer or Experimental Features](#newer-or-experimental-features)
- [Command Index](#command-index)

---


# Commands by Category

## Assist and Combat

| Command | Description | Example | Tags |
|---|---|---|---|
| `/assistme` | Makes bots assist you; newer behavior turns off clear-targets. | `/assistme` | common, assist, combat |
| `/assisttype` | Sets assist behavior/mode. | `/assisttype off` | assist, combat, toggle |
| `/backoff` | Stops attacking. | `/backoff` | common, panic, combat |
| `/backoffme` | Stops attacking you/your target context. | `/backoffme` | combat, safety |
| `/e3assistdistance` | Set assist range locally from `1–100` or `max`. | `/e3assistdistance 75` | assist, range |
| `/e3smarttaunt` | Toggle smart taunt behavior. | `/e3smarttaunt on` | tank, taunt |
| `/cleartargets` | Clear-targets helper command. | `/cleartargets` | xtarget, assist |
| `/cleartargets usemytarget` | Uses your current target for clear-target logic. | `/cleartargets usemytarget` | xtarget, assist |
| `/cleartargets FindLowestHPTarget` | Clear-target variant that picks the lowest HP target. | `/cleartargets FindLowestHPTarget` | xtarget, assist |
| `/cleartargets FindHighestHPTarget` | Clear-target variant that picks the highest HP target. | `/cleartargets FindHighestHPTarget` | xtarget, assist |
| `/cleartargets stick` | Makes the tank stick to the selected clear-target mob. | `/cleartargets stick` | tank, stick, xtarget |
| `/pbaeon` | Enables PBAE behavior. | `/pbaeon` | ae, nuke |
| `/pbaeoff` | Disables PBAE behavior. | `/pbaeoff` | ae, nuke |

## Movement and Following

| Command | Description | Example | Tags |
|---|---|---|---|
| `/followme` | Standard follow command. | `/followme` | common, movement, follow |
| `/followoff` | Stops follow. | `/followoff` | common, movement |
| `/followoff tome` | Stops follow after bots move to your current location. | `/followoff tome` | movement, follow |
| `/chaseme` | Active chase/follow behavior. | `/chaseme` | common, movement |
| `/anchoron` | Enables anchor behavior. | `/anchoron` | movement, camp |
| `/anchoroff` | Disables anchor behavior. | `/anchoroff` | movement, camp |
| `/mtm` | Move-to-me style movement command. | `/mtm` | movement, group |
| `/rtz` | Return-to-zone/return-to-anchor style movement command. | `/rtz` | movement |
| `/scatter` | Scatters/spreads bots. | `/scatter` | movement, positioning |
| `/clickit` | Movement/click helper command. | `/clickit` | movement, click |
| `/coth` | Call of the Hero command; release notes mention it can be used in combat. | `/coth` | mage, movement |
| `/e3movetoloc` | Move to a specific location. | `/e3movetoloc` | movement, loc |
| `/e3movetorandomloc` | Move to a random location. | `/e3movetorandomloc` | movement, random |
| `/e3follow` | Experimental nav-assisted follow. Use `/followme` or `/chaseme` unless testing. | `/e3follow` | new, experimental, movement |
| `/e3follow replay` | Slower replay-follow mode that attempts to replay your movement path. | `/e3follow replay` | experimental, movement |
| `/e3follow nonav` | Follow mode with stuck-nav behavior disabled. | `/e3follow nonav` | experimental, movement |
| `/e3follow replay nonav` | Replay follow without nav assistance. | `/e3follow replay nonav` | experimental, movement |
| `/e3movement pause` | Pauses E3 movement logic without shutting down all automation. | `/e3movement pause` | movement, pause |
| `/e3movement resume` | Resumes E3 movement logic. | `/e3movement resume` | movement, resume |

## Bot Broadcasts and Groups

| Command | Description | Example | Tags |
|---|---|---|---|
| `/e3bc` | E3 bot broadcast command. | `/e3bc /say hi` | broadcast, bots |
| `/e3bca` | Broadcast to all relevant E3 bots. | `/e3bca /followme` | broadcast, all |
| `/e3bcaa` | Broadcast variant, commonly all/all-style. | `/e3bcaa /buffme` | broadcast, all |
| `/e3bct` | Broadcast to a target/specific toon. | `/e3bct Toonname /sit` | broadcast, target |
| `/e3bcr` | Broadcast to raid. | `/e3bcr /assistme` | broadcast, raid |
| `/e3bcra` | Broadcast raid/all variant. | `/e3bcra /backoff` | broadcast, raid |
| `/e3bcrz` | Broadcast raid-zone variant. | `/e3bcrz /followme` | broadcast, raid, zone |
| `/e3bcraz` | Broadcast raid/all/zone variant. | `/e3bcraz /buffme` | broadcast, raid, zone |
| `/e3bcg` | Broadcast to group. | `/e3bcg /followme` | broadcast, group |
| `/e3bcga` | Broadcast group/all variant. | `/e3bcga /buffme` | broadcast, group |
| `/e3bcgz` | Broadcast group/zone variant. | `/e3bcgz /followme` | broadcast, group, zone |
| `/e3bcgza` | Broadcast group/zone/all variant. | `/e3bcgza /buffme` | broadcast, group, zone |
| `/e3bcz` | Broadcast zone variant. | `/e3bcz /say test` | broadcast, zone |
| `/e3bcza` | Broadcast zone/all variant. | `/e3bcza /say test` | broadcast, zone |
| `/e3bcchannel` | Sends E3 commands to characters in a named E3 channel. | `/e3bcchannel Healers /buffme` | broadcast, channel |
| `/e3GlobalBroadcast` | Global broadcast command. | `/e3GlobalBroadcast` | broadcast, global |
| `/e3botreport` | Reports bot/group stats such as HP/mana/spell shield/spell damage/AA. | `/e3botreport` | report, status |
| `/savegroup` | Saves current group. | `/savegroup` | group |
| `/listgroups` | Lists saved groups. | `/listgroups` | group |
| `/group` | Group utility command. | `/group` | group |

## Buffs, Blocking, and Casting Requests

| Command | Description | Example | Tags |
|---|---|---|---|
| `/buffme` | Request buffs. Supports minimum duration. | `/buffme MinDuration\|6` | common, buffs |
| `/buffit` | Buff request/helper command. | `/buffit` | buffs |
| `/buffpet` | Request pet buffs. | `/buffpet` | pet, buffs |
| `/queuecast` | Queue a cast request. | `/queuecast` | casting, buffs |
| `/nowcast` | Force/perform now-cast behavior. | `/nowcast` | casting |
| `/dropbuff` | Drop a buff by name. | `/dropbuff Spirit of Wolf` | buffs, remove |
| `/dropbuffid` | Drop a buff by spell/buff ID. Useful for duplicate-name cases. | `/dropbuffid 1234` | buffs, remove, id |
| `/blockbuff` | Block a buff. | `/blockbuff` | buffs, block |
| `/e3buffs-clear` | Clears buffs from the group. | `/e3buffs-clear` | dangerous, buffs |
| `/e3clearbufftimers` | Clears internal buff timer tracking. | `/e3clearbufftimers` | buffs, debug |
| `/dropinvis` | Removes invis from the group. | `/dropinvis` | invis, buffs |
| `/droplev` | Removes levitate from the group. | `/droplev` | levitate, buffs |
| `/e3consume` | Repeatedly clicks/consumes an item until gone; can use cursor item. | `/e3consume` | item, click, consume |

## Debuffs, DoTs, Dispel, and Resist Tracking

| Command | Description | Example | Tags |
|---|---|---|---|
| `/debuff` | Debuff toggle/helper. | `/debuff` | debuff, combat |
| `/debuffon` | Static on variant for debuff behavior. | `/debuffon` | debuff, toggle |
| `/debuffoff` | Static off variant for debuff behavior. | `/debuffoff` | debuff, toggle |
| `/debuffson` | Enables debuff behavior. | `/debuffson` | debuff, toggle |
| `/debuffsoff` | Disables debuff behavior. | `/debuffsoff` | debuff, toggle |
| `/dot` | DoT toggle/helper. | `/dot` | dot, combat |
| `/dotson` | Enables DoT behavior. | `/dotson` | dot, toggle |
| `/dotsoff` | Disables DoT behavior. | `/dotsoff` | dot, toggle |
| `/e3dispel` | Enables dispel-assist behavior similar to debuff/dot assist. | `/e3dispel` | dispel, debuff |
| `/e3dispeloff` | Disables dispel behavior. | `/e3dispeloff` | dispel, toggle |
| `/e3offassiston` | Enables off-assist debuff/dot behavior. | `/e3offassiston` | offassist, debuff |
| `/e3offassistoff` | Disables off-assist debuff/dot behavior. | `/e3offassistoff` | offassist, debuff |
| `/e3offassistignore` | Ignores off-assist target/mob. | `/e3offassistignore` | offassist, ignore |
| `/e3print-debuffdottimers` | Prints internal DoT/debuff timers. | `/e3print-debuffdottimers` | debug, debuff, dot |
| `/e3clear-debuffdottimers` | Clears internal DoT/debuff timers. | `/e3clear-debuffdottimers` | debug, debuff, dot |
| `/e3resist-magic` | Mark current target/mob name as resistant or immune to magic-type spells. | `/e3resist-magic immune` | resist, magic |
| `/e3resist-disease` | Mark current target/mob name as resistant or immune to disease-type spells. | `/e3resist-disease` | resist, disease |
| `/e3resist-poison` | Mark current target/mob name as resistant or immune to poison-type spells. | `/e3resist-poison` | resist, poison |
| `/e3resist-cold` | Mark current target/mob name as resistant or immune to cold-type spells. | `/e3resist-cold` | resist, cold |
| `/e3resist-fire` | Mark current target/mob name as resistant or immune to fire-type spells. | `/e3resist-fire immune` | resist, fire |
| `/e3resist-corrupt` | Mark current target/mob name as resistant or immune to corruption-type spells. | `/e3resist-corrupt` | resist, corrupt |

## Burns and Cooldowns

| Command | Description | Example | Tags |
|---|---|---|---|
| `/e3burns` | Burn command/helper. | `/e3burns` | burns |
| `/quickburns` | Fires quick burn setup. | `/quickburns` | burns, common |
| `/longburns` | Fires long burn setup. | `/longburns` | burns |
| `/fullburns` | Fires full burn setup. | `/fullburns` | burns |
| `/epicburns` | Fires epic burn setup. | `/epicburns` | burns, epic |
| `/swarmpets` | Swarm pet burn/helper command. | `/swarmpets` | burns, pet |
| `/e3burnreport` | Lists burn timers/cooldowns. | `/e3burnreport` | report, burns |

## Loot, Selling, and Inventory

| Command | Description | Example | Tags |
|---|---|---|---|
| `/looton` | Enables looting. | `/looton` | common, loot |
| `/lootoff` | Disables looting. | `/lootoff` | common, loot |
| `/looton force` | Unhides corpses, clears ignore collections, and reprocesses loot. | `/looton force` | loot, fix |
| `/lootkeep` | Adds/uses a keep loot rule. | `/lootkeep Item Name` | loot, rules |
| `/lootsell` | Adds/uses a sell loot rule. | `/lootsell Item Name` | loot, sell |
| `/lootskip` | Adds/uses a skip loot rule. | `/lootskip Item Name` | loot, skip |
| `/lootdestroy` | Adds/uses a destroy loot rule. | `/lootdestroy Item Name` | dangerous, loot |
| `/E3LootAdd` | Adds a loot rule. | `/E3LootAdd` | loot, rules |
| `/E3LootStackAdd` | Adds a stack-aware loot rule. | `/E3LootStackAdd` | loot, stack |
| `/e3lootall` | Loot-all command. | `/e3lootall` | loot |
| `/e3loot-area` | Experimental area-loot command. | `/e3loot-area` | experimental, loot |
| `/e3sell` | Sell command. Preview first; confirmation required to actually sell. | `/e3sell pack1` | sell, vendor |
| `/autosell` | Auto-sell helper command. | `/autosell` | sell, vendor |
| `/syncinv` | Inventory sync helper. | `/syncinv` | inventory |
| `/e3autobank` | Stacks inventory items into matching bank stacks; may navigate to banker if needed. | `/e3autobank` | bank, inventory |
| `/e3autostack` | Older/deprecated auto-stack command. Prefer `/e3autobank`. | `/e3autostack` | bank, deprecated |
| `/autostack` | Wiki auto-stack command. | `/autostack` | bank, stack |
| `/e3getfrombank` | Gets item from bank. | `/e3getfrombank "Item Name" 10` | bank, inventory |
| `/getfrombank` | Wiki version for getting item from bank. | `/getfrombank "Item Name" 10` | bank, inventory |
| `/e3getfrominv` | Gets item from inventory. | `/e3getfrominv "Item Name"` | inventory |
| `/getfrominv` | Wiki version for getting item from inventory. | `/getfrominv "Item Name"` | inventory |
| `/e3getfrominventory` | Mentioned inventory get command variant. | `/e3getfrominventory` | inventory |
| `/finditem` | Finds item. | `/finditem "Item Name"` | inventory, search |
| `/upgrade` | Upgrade helper command. | `/upgrade` | inventory, gear |
| `/fic` | Inventory helper command from command list. | `/fic` | inventory |
| `/fds` | Inventory helper command from command list. | `/fds` | inventory |
| `/e3inventoryfile_sync` | Writes inventory/bank data to a SQLite DB file. | `/e3inventoryfile_sync` | inventory, database |
| `/e3restock` | Vendor restock for food/water/emeralds; supports filters. | `/e3restock emerald 500 /only\|Healers` | vendor, restock |
| `/restock` | Deprecated restock command. Prefer `/e3restock`. | `/restock food` | deprecated, restock |
| `/giveme` | Give/request item command. | `/giveme Item Name` | inventory, give |
| `/E3DestroyItem` | Destroys an item by name. | `/E3DestroyItem "Orb of Mastery"` | dangerous, delete |
| `/E3DestroyNoRent` | Replacement for `/DestroyNoRent`. | `/E3DestroyNoRent` | dangerous, no-rent |
| `/destroynorent` | Destroys no-rent cursor item. | `/destroynorent` | dangerous, no-rent |

## Rez, Corpses, and Wipe Recovery

| Command | Description | Example | Tags |
|---|---|---|---|
| `/rezit` | Rez helper command. | `/rezit` | rez |
| `/grez` | Group rez helper. | `/grez` | rez, group |
| `/rrez` | Raid rez helper. | `/rrez` | rez, raid |
| `/aerez` | AE rez helper. | `/aerez` | rez, ae |
| `/autorezon` | Enables auto-rez behavior. | `/autorezon` | rez, auto |
| `/e3prez` | Pre-rez helper command. | `/e3prez` | rez |
| `/TellRez` | Tell-based rez helper. | `/TellRez` | rez, tell |
| `/WaitRez` | Wait-for-rez helper. | `/WaitRez` | rez, wait |
| `/gathercorpses` | Gather corpses. | `/gathercorpses` | corpse, recovery |
| `/gathercorpse` | Wiki command: summons nearby corpses and requests permission for others. | `/gathercorpse` | corpse, recovery |
| `/lootcorpses` | Loot corpse helper after recovery. | `/lootcorpses` | corpse, loot |
| `/wipe` | Wipe recovery helper command. | `/wipe` | wipe, recovery |
| `/reload` | Used by rez logic for an EMU rez bug. | `/reload` | rez, emu |

## Bard Commands

| Command | Description | Example | Tags |
|---|---|---|---|
| `/playmelody` | Plays the melody matching a named `MelodyIf=` entry; supports `stop`. | `/playmelody stop` | bard, melody |
| `/e3bard-automez` | Toggle bard auto-mez. Commonly invoked through `/e3bct <bard>`. | `/e3bct Bardname /e3bard-automez on` | bard, mez |

Useful bard-related parameters:

| Parameter | Description | Example |
|---|---|---|
| `/SongRefreshTime\|18` | Bard song refresh timing config. | `Song=/Some Song/SongRefreshTime\|18` |
| `/NoMidSongCast` | Prevents odd AAs/abilities from firing mid-song. | `AA=Vainglorious Shout/NoMidSongCast` |

## UI, HUD, and Configuration

| Command / Setting | Description | Example | Tags |
|---|---|---|---|
| `/e3config` | Windows GUI config editor. Back up INIs first. | `/e3config` | ui, config |
| `/e3config-old` | Old config GUI after rename. | `/e3config-old` | ui, config |
| `/e3imgui` | Old name renamed to `/e3config`. | `/e3imgui` | renamed, ui |
| `/e3ui` | E3 UI command. | `/e3ui` | ui |
| `/e3ui-debug` | Debug E3 UI. | `/e3ui-debug` | ui, debug |
| `/e3ui-kill` | Kill/close E3 UI. | `/e3ui-kill` | ui |
| `/ui` | UI command from NetMQServer class. | `/ui` | ui |
| `/e3hud_casting` | Opens lightweight casting HUD replacement for MQ2Hud. | `/e3hud_casting` | hud, casting |
| `/e3hud_hub` | Newer ImGui hub with scaling/font options and expanded pet/target buff visibility. | `/e3hud_hub` | hud, ui, new |
| `config\e3 bot inis\Toon_Server_UI.ini` | Newer UI settings file location. | n/a | ui, config, backup |
| `/e3settings createdefault` | Generates a new defaults file to copy values from. | `/e3settings createdefault` | config |
| `/e3printini` | Prints character INI. | `/e3printini` | config, debug |

## Diagnostics and Debugging

| Command | Description | Example | Tags |
|---|---|---|---|
| `/e3listcommands` | Lists E3Next commands via reflection. | `/e3listcommands` | discovery, debug |
| `/e3version` | Shows current E3Next version. | `/e3version` | version, debug |
| `/e3memstats` | Shows group memory usage. Requires newer MQ2Mono. | `/e3memstats` | memory, crash |
| `/e3debug_memory_count` | Shows internal memory collection sizes. | `/e3debug_memory_count` | memory, debug |
| `/e3debug_buffTimers` | Shows internal buff timers for a toon. | `/e3debug_buffTimers` | buffs, debug |
| `/e3debug_disablewrites` | Debug command for disabling/testing E3 output writes. | `/e3debug_disablewrites` | debug, writes |
| `/e3debug_check_targetbuffs` | Diagnostic check for target buff state. | `/e3debug_check_targetbuffs` | debug, buffs |
| `/e3debug_check_buffs` | Diagnostic check for character/group buff state. | `/e3debug_check_buffs` | debug, buffs |
| `/e3debug_check_petbuffs` | Diagnostic check for pet buff state. | `/e3debug_check_petbuffs` | debug, pets |
| `/e3debug_check_xtargets` | Diagnostic check for XTarget data/state. | `/e3debug_check_xtargets` | debug, xtarget |
| `/e3debug_check_spawndelta` | Diagnostic check for spawn delta/change tracking. | `/e3debug_check_spawndelta` | debug, spawns |
| `/e3debug_spawns_list` | Prints/lists internal spawn data. | `/e3debug_spawns_list` | debug, spawns |
| `/e3debug_spawns_list_names` | Prints/lists internal spawn names. | `/e3debug_spawns_list_names` | debug, spawns |
| `/e3debug_list_disc` | Diagnostic list of known discs. | `/e3debug_list_disc` | debug, discs |
| `/e3debug_list_aa` | Diagnostic list of known AAs. | `/e3debug_list_aa` | debug, aa |
| `/e3debug-config` | Debug config command. | `/e3debug-config` | debug, config |
| `/e3printAA` | Prints AAs you currently have. | `/e3printAA` | aa, debug |
| `/e3printDics` | Prints discs you currently have. | `/e3printDics` | discs, debug |
| `/e3listexposeddata` | Prints `${E3N.State...}` and `${E3N.Settings...}` paths. | `/e3listexposeddata` | exposed, mq, debug |
| `/e3broadcastwrites` | Broadcasts every `MQ.Write` message for consolidated output. | `/e3broadcastwrites` | debug, broadcast |
| `/e3cpudelay` | Sets polling/delay settings such as publish intervals. | `/e3cpudelay` | performance, debug |
| `/e3xtargetfix` | XTarget fix toggle. | `/e3xtargetfix on` | xtarget, emu, debug |
| `/e3bugs_xtargetfix` | Attempts to unstick XTargets on emu. | `/e3bugs_xtargetfix toggle` | xtarget, emu, debug |
| `/e3xtarget` | Setup for XTarget healing and related behavior. | `/e3xtarget` | xtarget, healing |
| `/e3zonedump` | Dumps current zone NPC data. | `/e3zonedump` | zone, debug |
| `/e3zonerecord` | Dumps current zone NPC data. | `/e3zonerecord` | zone, debug |
| `/debug` | Debug helper command and/or spell flag context. | `/debug` | debug |
| `/e3echo` | Echo through E3Next; useful for E3 variables. | `/e3echo ${E3N.State...}` | debug, variables |
| `/e3echobool` | Boolean echo helper. | `/e3echobool` | debug, variables |

## Veteran AAs and Utility

| Command | Description | Example | Tags |
|---|---|---|---|
| `/origin` | Origin command, like `/throne`. | `/origin` | veteran, travel |
| `/throne` | Throne veteran AA command. | `/throne` | veteran, travel |
| `/lesson` | Lesson veteran AA command. | `/lesson` | veteran, xp |
| `/armor` | Armor veteran AA command. | `/armor` | veteran |
| `/expedient` | Expedient veteran AA command. | `/expedient` | veteran |
| `/infusion` | Infusion veteran AA command. | `/infusion` | veteran |
| `/intensity` | Intensity veteran AA command. | `/intensity` | veteran |
| `/jester` | Jester veteran AA command. | `/jester` | veteran |
| `/servant` | Servant veteran AA command. | `/servant` | veteran |
| `/staunch` | Staunch veteran AA command. | `/staunch` | veteran |
| `/evac` | Evac command. | `/evac` | travel, escape |
| `/e3gate` | Gate command for EQMight. | `/e3gate` | server, travel |
| `/e3manastone` | Manastone helper command. | `/e3manastone` | mana, item |
| `/e3forage` | Toggle forage feature. | `/e3forage on` | forage |
| `/e3p` | Pause command; newer behavior pauses/resumes afollow/stick. | `/e3p on` | pause |
| `/e3yes` | E3 yes helper. | `/e3yes` | utility |
| `/e3no` | E3 no helper. | `/e3no` | utility |
| `/yes` | Yes helper. | `/yes` | utility |
| `/no` | No helper. | `/no` | utility |
| `/pizza` | Fun/basic command from command list. | `/pizza` | fun |
| `/wiki` | Opens/prints wiki helper. | `/wiki` | help |
| `/reportaa` | Reports AA. | `/reportaa` | aa, report |
| `/e3treport` | Lists configured report items in character INI. | `/e3treport` | report, config |

## Server-Specific Commands

| Command | Description | Example | Tags |
|---|---|---|---|
| `/baz` | Lazarus: launches the Lazarus bazaar page. | `/baz` | lazarus, bazaar |
| `/e3laz-count-nv` | Lazarus/Nightveil item count helper. | `/e3laz-count-nv` | lazarus, nightveil |
| `/e3lazsymbolfileupdate` | Lazarus symbol file update command. | `/e3lazsymbolfileupdate` | lazarus |
| `/e3godturnin` | Lazarus symbol/data-file turn-in helper. | `/e3godturnin` | lazarus |
| `/e3popturnin` | Lazarus symbol/data-file turn-in helper. | `/e3popturnin` | lazarus |
| `/e3gate` | EQMight gate helper. | `/e3gate` | eqmight, gate |
| `/e3autojointasks` | Enables joining task invites from guild members; can use `GuildList.txt`. | `/e3autojointasks` | tasks, guild |

---

# INI and Spell Parameters

These are not always standalone slash commands. Many are spell-line modifiers or settings that belong in character/general INI files.

## Spell / ability line flags

| Parameter | Description | Example | Tags |
|---|---|---|---|
| `/AfterEventDelay\|...` | Spell-level delay after an event. | `/AfterEventDelay\|2s` | spell, delay |
| `/AfterSpellDelay\|...` | Spell-level delay after spell. | `/AfterSpellDelay\|2s` | spell, delay |
| `/BeforeEventDelay\|...` | Spell-level delay before event. | `/BeforeEventDelay\|1s` | spell, delay |
| `/BeforeSpellDelay\|...` | Spell-level delay before spell. | `/BeforeSpellDelay\|1s` | spell, delay |
| `/AfterCastDelay\|...` | Delay after cast. | `/AfterCastDelay\|2s` | spell, delay |
| `/delayaftercast\|time` | Adds per-spell/per-ability delay after casting; useful for latency. | `/delayaftercast\|2s` | spell, delay |
| `/CastType\|AA` | Forces cast type to AA. | `/CastType\|AA` | spell, casttype |
| `/CastType\|Spell` | Forces cast type to Spell. | `/CastType\|Spell` | spell, casttype |
| `/CastType\|Disc` | Forces cast type to Disc. | `/CastType\|Disc` | spell, casttype |
| `/CastType\|Item` | Forces cast type to Item; useful for temp items that appear not to exist. | `/CastType\|Item` | spell, item |
| `/MinHPTotal` | Canni safety; helps avoid shamans killing themselves. | `/MinHPTotal\|50` | shaman, safety |
| `/SongRefreshTime\|18` | Bard song refresh timing. | `/SongRefreshTime\|18` | bard, song |
| `/NoMidSongCast` | Prevents odd AAs from firing mid-song. | `/NoMidSongCast` | bard, song |
| `/ExcludedClasses\|...` | Exclude classes from a spell/action. | `/ExcludedClasses\|WAR,SHD` | filter, spell |
| `/ExcludedNames\|...` | Exclude names from a spell/action. | `/ExcludedNames\|Toonname` | filter, spell |
| `/IgnoreResistanceCheck` | Bypasses E3 resist-skip logic for spells with strong resist mods. | `/IgnoreResistanceCheck` | resist, spell |
| `/debug` | Enables debug statements for a specific spell/ability. | `/debug` | debug, spell |

---

## What Are You Trying To Do?

| I want to... | Look here | Useful commands |
|---|---|---|
| Move my bots | [Movement and Following](#movement-and-following) | `/followme`, `/chaseme`, `/followoff`, `/e3follow`, `/anchoron`, `/scatter` |
| Make bots attack | [Assist and Combat](#assist-and-combat) | `/assistme`, `/assisttype`, `/e3assistdistance` |
| Stop bots attacking | [Assist and Combat](#assist-and-combat) | `/backoff`, `/backoffme`, `/assisttype off` |
| Fix looting | [Loot, Selling, and Inventory](#loot-selling-and-inventory) | `/looton`, `/lootoff`, `/looton force`, `/e3lootall` |
| Sell or bank items | [Loot, Selling, and Inventory](#loot-selling-and-inventory) | `/e3sell`, `/autosell`, `/e3autobank`, `/syncinv` |
| Get buffs | [Buffs, Blocking, and Casting Requests](#buffs-blocking-and-casting-requests) | `/buffme`, `/buffpet`, `/queuecast` |
| Drop/block buffs | [Buffs, Blocking, and Casting Requests](#buffs-blocking-and-casting-requests) | `/dropbuff`, `/dropbuffid`, `/blockbuff`, `/e3buffs-clear` |
| Use burns | [Burns and Cooldowns](#burns-and-cooldowns) | `/quickburns`, `/longburns`, `/fullburns`, `/epicburns` `/e3burns nameofcustomburn` |
| Recover after a wipe | [Rez, Corpses, and Wipe Recovery](#rez-corpses-and-wipe-recovery) | `/grez`, `/rrez`, `/rezit`, `/gathercorpses`, `/wipe` |
| Debug a problem | [Diagnostics and Debugging](#diagnostics-and-debugging) | `/e3memstats`, `/e3debug_*`, `/e3listexposeddata` |
| Change UI/HUD | [UI, HUD, and Configuration](#ui-hud-and-configuration) | `/e3config`, `/e3hud_hub`, `/e3hud_casting`, `/e3ui` |
| Work with bard melody/mez | [Bard Commands](#bard-commands) | `/playmelody`, `/e3bard-automez` |
| Mark spell resists/immunities | [Debuffs, DoTs, Dispel, and Resist Tracking](#debuffs-dots-dispel-and-resist-tracking) | `/e3resist-magic`, `/e3resist-fire`, `/IgnoreResistanceCheck` |

---

## 

```txt
E3Next quick commands:

/e3reload        reload settings
/e3version       show E3Next version
/e3listcommands  print available commands
/followme        bots follow you
/followoff       stop following
/chaseme         active chase/follow
/assistme        assist your target
/backoff         stop attacking
/buffme          ask group/network for buffs
/looton          enable looting
/lootoff         disable looting
/looton force    retry skipped/hidden corpses
/e3botreport     group status report
/e3config        open config GUI
```

---

## Dangerous Commands

These commands can delete items, sell items, clear buffs, or shut things down.

| Command | Risk | Safer description / hover text |
|---|---|---|
| `/E3DestroyItem` | Destroys an item by name. | **Dangerous.** Double-check spelling and quotes before use. |
| `/E3DestroyNoRent` | Destroys a no-rent item. | Safer than arbitrary destroy, but still deletes an item. |
| `/destroynorent` | Older/wiki no-rent cursor destroy command. | Destroys the item on cursor if it is **NO RENT**. |
| `/e3buffs-clear` | Removes buffs from the entire group. | **Dangerous.** Use only when you truly want group buffs cleared. |
| `/lootdestroy` | Loot rule/action that destroys matching loot. | Check item name/rule before adding. |
| `/shutdown` | Completely shuts down E3Next. | Use only when intentionally stopping E3. |
| `/e3movement pause` | Pauses E3 movement. | Not destructive, but can make bots stop moving unexpectedly. |

---

## Global Filters and Modifiers

Many group-style commands can use filters so only certain bots respond.

| Filter | Meaning | Example |
|---|---|---|
| `/only\|NameOrClass` | Only matching names/classes/groups respond. | `/e3restock emerald 500 /only\|Healers` |
| `/not\|NameOrClass` | Excludes matching names/classes/groups. | `/followme /not\|Cleric` |
| `/all` | Includes out-of-group bots in your network. | `/buffme /all` |
| `/ignoreme` | Everyone except the driver responds. | `/followme /ignoreme` |

Examples:

```txt
/followme /only|Warrior
/buffme /all
/e3restock emerald 500 /only|Healers
/backoff /not|Tankname
```

---

## Common Recipes

### Reload after editing INIs

```txt
/e3reload
```

### Make everyone follow you

```txt
/followme
```

### Stop everyone from following

```txt
/followoff
```

### Stop combat immediately

```txt
/backoff
```

### Turn assist off

```txt
/assisttype off
```

### Ask group/network for buffs

```txt
/buffme
/buffme MinDuration|6
```

### Restock after a run

```txt
/e3restock food
/e3restock water
/e3restock emerald 500
/e3restock emerald 500 /only|Healers
```

### Loot got stuck, hidden, or skipped

```txt
/looton force
```

### Preview sellables before selling

```txt
/e3sell pack1
```

Then only confirm once you are sure:

```txt
/e3sell pack1 yes
```

### Check high memory or crash reports

```txt
/e3memstats
/e3debug_memory_count
/e3version
```

### See what E3 exposes to MQ expressions

```txt
/e3listexposeddata
```

### Mark a mob as immune or resistant to a spell type

Target the mob first, then:

```txt
/e3resist-magic
/e3resist-fire immune
/e3resist-magic clear
```

---

# Newer or Experimental Features

| Feature | Description | Use carefully because... |
|---|---|---|
| `/e3follow` | Experimental nav-assisted follow. | Release notes say `/followme` and `/chaseme` are still safer defaults. |
| `/e3follow replay` | Attempts to replay your movement path. | Slower; not ideal for long-distance travel. |
| `/e3loot-area` | Experimental area-loot command. | Release notes say it was not tested. |
| `/e3hud_hub` | Newer ImGui hub HUD/window. | Requires newer MQ2Mono/ImGui support. |
| `/e3resist-*` | Remembers mob spell-type resist/immune handling. | Make sure you target the right mob before marking. |
| `/e3movement pause/resume` | Pause/resume E3 movement logic. | Can make bots stop moving while other automation remains active. |

---

# Command Index

Search-friendly index of commands mentioned in this document:

```txt
/assistme /assisttype /backoff /backoffme /e3assistdistance /e3smarttaunt
/bark /bark-send /e3bark /e3bark-send /debug /dropinvis /droplev /e3allowmanual
/e3bugs_xtargetfix /e3burnreport /e3camp /e3cpudelay /e3echo /e3echobool
/e3forage /e3listcommands /e3manastone /e3p /e3printAA /e3printDics
/e3printini /e3reload /e3settings /e3treport /e3yes /e3no /evac /group
/listgroups /no /pizza /reportaa /savegroup /shutdown /wiki /yes
/buffit /buffme /buffpet /queuecast /nowcast /blockbuff /dropbuff /dropbuffid
/e3buffs-clear /e3clearbufftimers /e3consume
/e3bc /e3bca /e3bcaa /e3bcchannel /e3bcg /e3bcga /e3bcgz /e3bcgza
/e3bcr /e3bcra /e3bcraz /e3bcrz /e3bct /e3bcz /e3bcza /e3botreport /e3GlobalBroadcast
/e3burns /epicburns /fullburns /longburns /quickburns /swarmpets
/e3restock /restock /e3resetcounters /e3varbool /e3varcalc /e3varclear /e3varlist /e3varset /e3varvalue
/charmoff /charmon /cleartargets /e3commandset /CastingRadiantCure
/debuff /debuffon /debuffoff /debuffson /debuffsoff /dot /dotson /dotsoff
/e3clear-debuffdottimers /e3offassistignore /e3offassistoff /e3offassiston /e3print-debuffdottimers
/e3dispel /e3dispeloff /e3resist-magic /e3resist-disease /e3resist-poison /e3resist-cold /e3resist-fire /e3resist-corrupt
/E3DestroyItem /E3DestroyNoRent /destroynorent /giveme
/e3xtarget /e3xtargetfix /e3getfrombank /e3getfrominv /e3getfrominventory /getfrombank /getfrominv
/fds /fic /finditem /upgrade /e3inventoryfile_sync /e3godturnin /e3popturnin /e3lazsymbolfileupdate
/E3LootAdd /E3LootStackAdd /lootdestroy /lootkeep /lootoff /looton /lootsell /lootskip /e3lootall /e3loot-area
/anchoroff /anchoron /chaseme /clickit /coth /e3movetoloc /e3movetorandomloc /e3follow /e3movement /followme /followoff /mtm /rtz /scatter
/e3debug-config /e3ui-debug /e3ui-kill /ui /e3config /e3config-old /e3hud_casting /e3hud_hub
/aerez /autorezon /e3prez /gathercorpses /gathercorpse /grez /lootcorpses /reload /rezit /rrez /TellRez /WaitRez /wipe
/autosell /e3autobank /e3autostack /autostack /e3sell /syncinv
/e3broadcastwrites /e3ListExposedData /e3listexposeddata /e3version /e3memstats
/e3debug_memory_count /e3debug_buffTimers /e3debug_disablewrites /e3debug_check_targetbuffs /e3debug_check_buffs /e3debug_check_petbuffs /e3debug_check_xtargets /e3debug_check_spawndelta /e3debug_spawns_list /e3debug_spawns_list_names /e3debug_list_disc /e3debug_list_aa
/e3laz-count-nv /baz /e3autojointasks /e3tribute-list /tribute
/armor /expedient /infusion /intensity /jester /lesson /origin /servant /staunch /throne
/e3zonedump /e3zonerecord /playmelody /e3bard-automez
```
