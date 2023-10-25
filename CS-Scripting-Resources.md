# Community Service Scripts

This document is a list of commonly used scripts for ascensions in the [Community Service](https://kol.coldfront.net/thekolwiki/index.php/Community_Service) challenge path in KoL. Most of them are meant for 1-day, loop-style hardcore runs -- that is, minimizing resource use rather than turncount. Some are not: a few are meant for two-day, or for speed, or for something else entirely. Most of these are written in Typescript, which is then compiled into Javascript for use by kolmafia. A few are written in ash, which conveniently does not need to be compiled.

CS scripts tend to be extraordinarily personal. Because the path rewards owning a long tail of marginal IotMs, and each user's [greenboxen](http://cheesellc.com/kol/profile.php?u=captain%20scotch) are slightly different, scripts will often fail for those other than their single intended user. Take this as a caveat before attempting to run any of these, and expect a few strange failures until you either customize the script or match the scripter's suite of IotM resources. If you click on each user's name, you will arrive at their CC Snapshot, demonstrating the # of IOTMs they are personally utilizing in the service of their script. 

## bean-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [worthawholebean (#1972588)](https://www.cheesellc.com/kol/profile.php?u=worthawholebean) | [here](https://github.com/phulin/bean-hccs) | ? | 107-114 turns | asdon | peppermint |

**bean-hccs** is the mother or grandmother of the majority of scripts on this list. It is thorough, efficient, and clearly written.  The script still has remnants from the 'mode' combat system that can be found in bcas, and features a complex and robust planner object for the use of Sweet Synthesis. Ironically, it is no longer written for use in hardcore.

## phccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [phreddrickkv2 (#1515124)](https://api.aventuristo.net/av-snapshot?u=phreddrickkv2) | [here](https://github.com/horrible-little-slime/phccs) | 10-11 minutes | ~90 turns | asdon | peppermint |

**phccs** is originally descended from bean-hccs, but has been rewritten enough times that at this point the link exists only in spirit. It currently uses an interesting twist on the classic grimoire framework, constructing and destructing separate engines for each Test to mesh more nicely with libram's Community Service logging support. Its maintainer primarily runs it in softcore, but it continues to function nicely in hardcore.

## InstantSCCS 
| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| WARriorer (#1634187) | [here](https://github.com/Pantocyclus/InstantSCCS) | 7-20 minutes | 94-320 turns | model train set | any |

**InstantSCCS** is a highly configurable softcore 1-day CS script designed for low to relatively-high shiny accounts. Unlike many earlier scripts that depend heavily on old IotMs, the core route is planned around 7 relatively recent IotMs from 2022 and 2023, with many being optional as InstantSCCS also supports an extensive range of old to new IotMs (many of which provide subtitutes of functionality required of the original 7). At the highest end (with the right configuration), the script currently boasts a 1/94 in hardcore CS (without pulls and modifications; as of Oct 2023) while remaining competitive in resource and organ usage with other profit-optimized high shiny CS scripts.

## FolgerCS
| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| Seraphiii (#1829137) | [here](https://github.com/Ignose/FolgerCS) | 7-10 minutes | 115-180 turns | asdon/trainset | any |

**FolgerCS** is a fork of InstantSCCS focused on profit maximization, choosing to skip resources that would be negative ROI to use. It's class agnostic, though works best for Pastamancer and Seal Clubber. It is designed to work for a variety of account states, limiting consumption to Astral Pilsners and Legendary Pizza. Borrowed time is optional.

## manny-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [Manendra (#1483803)](https://www.cheesellc.com/kol/profile.php?u=manendra) | [here](https://github.com/lewismd13/manny-hccs) | 5-6 minutes | 109-110 turns | asdon | peppermint |

**manny-hccs** has recently undergone a radical overhaul, combining Libram's new CS support with elements of the restructured bean-hccs, phccs, and the original manny-hccs. It uses Asdon in the workshed, and features a resource-tracking log originally written by worthawholebean. In theory it should eventually support DNA lab, as well as Sauceror and/or Seal Clubber classes.

## bb-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [BurningBman (#1729599)](https://www.cheesellc.com/kol/profile.php?u=burningbman) | [here](https://github.com/burningbman/bb-hccs) | 2.5 minutes | 140-150 turns | pizza | mushroom |

**bb-hccs** is built for much lower-greenbox accounts than any of the scripts listed above. It too is a bean-hccs fork, and is also no longer written for hardcore! bb-hccs is not currently particularly re-entrant--if it throws an error, you may not be able to re-start the script. It is an excellent example of how to adapt high-iotm scripts for lower-iotm use.

## seventy-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| katarn (#786069) | [here](https://github.com/s-k-z/seventy-hccs) | 12 minutes | 70 turns | pizza | peppermint |

**seventy-hccs** is not descended from bean-hccs, nor is it a loop script. Instead, it is designed to do exactly what it says on the tin -- a 1-day, 70-turn run of the challenge path. Katarn is not only the first player to complete a 1/70 run, but he's also the most prolific 1/70 player, and does them often. The design of both diet.ts and events.ts are well worth your time, as is the rest of it; because seventy-hccs isn't descended from bean-hccs, just about every part of it is going to stand out. If you are going for turncount, there's no better script.

## c2t_hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [Zdrvst (#3286685)](https://www.cheesellc.com/kol/profile.php?u=Zdrvst) | [here](https://github.com/c2talon/c2t_hccs) | ~10 minutes | 134-135 turns | pizza | any |

**c2t_hccs** is an actively maintained dedicated ASH script for community service designed to be used by a broad group of players. It requires a fair amount of setup, detailed in the README.md, and one unique aspect of this script is that it works as any class. Zdrvst tends to run it as a Seal Clubber which makes it valuable for barf farming. It is designed to be appropriately re-entrant, and currently terminates before performing any test that takes more than one turn, unless configured to do otherwise.
If run in softcore, it'll shave about 10 turns off of its expected turncount.

## fizz-sccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [MrFizzyBubbs (ign Baden) (#2460823)](https://cheesellc.com/kol/profile.php?u=Baden) | [here](https://github.com/MrFizzyBubbs/fizz-sccs) | ~10 minutes | 111 turns | DNA | Peppermint |

**fizz-sccs** is an ASH script structurally inspired by seventy-hccs that borrows code from c2t_hccs. This script trades flexiblity for reliability and will likely not run for users missing any of the IotMs it uses. It is also re-entrant and aims to minimize usage of profitable daily flags.

## Asmo-HCCS

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [Asmodais (#2071543)](https://www.cheesellc.com/kol/profile.php?u=asmodais) | [here](https://github.com/Tokoeka/asmo_hccs/) | ~15 minutes | 101-103 turns | DNA | peppermint |

**Asmo-HCCS** is a script frankensteined together from bits and pieces of various hccs scripts, primarily **manny-hccs** and **phccs**. Utilising the DNA-lab, it currently assumes you are a pastamancer and is designed to be optimised for Asmodais' set of IOTMs and skills and as re-entrant as feasible should it break. Currently optimised for Hardcore, but has some specific pulls if used in Softcore.

## DC6S

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [DanceCommander6 (#1892258)](https://www.cheesellc.com/kol/profile.php?u=DanceCommander6) | [here](https://github.com/ktpolanski/dc6s) | ~10 minutes | 105 turns | asdon | peppermint |

**DC6S** takes inspiration from a number of established CS scripts, mainly **manny-hccs**, **phccs** and **seventy-hccs**. The author was learning about CS and TS as the script got made, which is evident in the simpler syntax, excessive commenting, and a run plan in spreadsheet form with accompanying discussion. There's also a baked in half-loop script that adds a garbo leg on either side of the ascension for minimum effort to play the game.

## HCCSauto

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [iloath](https://www.cheesellc.com/kol/profile.php?u=iloath) | [here](https://gitgud.io/iloath/HCCSauto) | ??? | 2 days | any | any |

**HCCSauto** is a largely deprecated script known for its simplicity and its ability to complete an ascension with nothing but the VIP & genie bottle, and mortar+weaksauce. It is not re-entrant, and it is a 2-day script rather than 1-day (making it equally good for karma-farming, but much worse for meat-farming). A more thorough writup on it can be found [here](https://www.reddit.com/r/kol/wiki/guides/iloath_hccs2).

##  Auto-2-day-HCCS

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| Malurth et al | [here](https://github.com/Malurth/Auto-2-day-HCCS) | ??? | 2 days | DNA/any | Winter/any |

**Auto-2-day-HCCS** is based on a 2-day HCCS plan Yojimbos_Law sketched out on the fora one day. It requires an odd array of IotMs--Deck of Many Cards, Smithsness, Chateau, and VIP. It's written in ASH, is re-entrant and resource-minimal. It's organized nicely, making it easy to chop up into your own HCCS script, but may be a little dated.


## autoscend

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| [LASS](https://github.com/Loathing-Associates-Scripting-Society) | [here](https://github.com/Loathing-Associates-Scripting-Society/autoscend) | ??? | 2-3 days | any | any |

Do not use **autoscend** for community service. Please. It is structured around completing the quests the Council gives the adventurer in normal paths; while it will do its level best in CS, CS support is not an active part of autoscend development. I'm mentioning it here both to say that, and to point out the one big leg up autoscend has over just about anyone: it has virtually no requirements. Autoscend will do its best to fight tooth and nail to get you to donate that rockin' bod to science, and you don't have to even own a genie bottle. If you, for some reason, need to complete a community service ascension, have 0 iotms, and 0 ability to play turns, sure, fine, use this. But only then, and maybe not even then!

Stacks of two or more dogs should be allowed to vote.
