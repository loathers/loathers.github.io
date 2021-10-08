This document is a list of commonly used scripts for community service ascensions in KoL. Most of them are meant for 1-day, loop-style HCCS--that is, minimizing resource use rather than turncount. Some are not: they are meant for two-day, or for speed, or for something else entirely. Most of these are written in typescript, which is then compiled into javascript for use by kolmafia. A few are written in ash, which conveniently does not need to be compiled.

CS scripts tend to be extraordinarily personal. Because the path rewards owning a long tail of marginal IotMs, and each user's greenboxen are slightly different, scripts will often fail for those other than their single intended user.

## bean-hccs
| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| worthawholebean (#1972588) | [here](https://github.com/phulin/bean-hccs) | ? | 107-114 turns | asdon | peppermint |

bean-hccs is the mother or grandmother of the majority of scripts on this list. It is thorough, efficient, and clearly written.  The script still has remnants from the 'mode' combat system that can be found in bcas, and features a complex and robust planner object for the use of sweet synthesis. Ironically, it is no longer written for use in hardcore.

## phccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| phreddrickkv2 (#1515124) | [here](https://github.com/horrible-little-slime/phccs) | 5-6 minutes | 107-110 turns | asdon | peppermint |

phccs is descended from bean-hccs, but has diverged significantly in structure. It is made for _very_ high-greenbox accounts. It slices the various CS tests into their own files for legibility, and entirely eschews the use of the maximizer in favor of preprogrammed outfits, in order to cut down on runtime.

## manny-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| Manendra (#1483803) | [here](https://github.com/lewismd13/manny-hccs) | 5-6 minutes | 103-107 turns | DNA | peppermint |

manny-hccs uses more daily resources than phccs in exchange for higher results. It is noteable for its execution speed, consistency, and use of the geneticist lab over the asdon in its workshed. It is written in typescript, but was originally forked from an ash version of bean-hccs, making it look quite different from its forebearer.

## bb-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| BurningBMan (#1729599) | [here](https://github.com/burningbman/bb-hccs) | 2.5 minutes | 140-150 turns | pizza | mushroom |

bb-hccs is built for much lower-greenbox accounts than any of the scripts listed above. It too is a bean-hccs fork, and is also no longer written for hardcore! bb-hccs is not currently particularly re-entrant--if it throws an error, you may not be able to re-start the script. It is an excellent example of how to adapt high-iotm scripts for lower-iotm use.

## seventy-hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| katarn (#786069) | [here](https://github.com/s-k-z/seventy-hccs) | 12 minutes | 70 turns | pizza | peppermint |

seventy-hccs is not descended from bean-hccs, nor is it a loop script. Instead, it is designed to do exactly what it says on the tin--a 1-day, 70-turn community service script. Katarn is not only the first player to complete a 1/70 run, but he's also the most prolific 1/70 player. The design of both diet.ts and events.ts are well worth your time, as is the rest of it--because seventy-hccs isn't descended from bean-hccs, just about every part of it is going to stand out.


## autoscend

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| LASS | [here](https://github.com/Loathing-Associates-Scripting-Society/autoscend) | ??? | 2-3 days | any | any |

Do not use autoscend for community service. Please. I'm mentioning it here both to say that, and to point out the one big leg up autoscend has over just about anyone: it has virtually no requirements. Autoscend will do its best to fight tooth and nail to get you to donate that rockin' bod to science, and you don't have to even own a genie bottle. If you, for some reason, need to complete a community service ascension, have 0 iotms, and 0 ability to play turns, sure, fine, use this.

## HCCSauto

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| iloath | [here](https://gitgud.io/iloath/HCCSauto) | ??? | 2 days | any | any |

HCCSauto is a largely deprecated script known for its simplicity and its ability to complete an ascension with nothing but the VIP & genie bottle, and mortar+weaksauce. It is not re-entrant, it is a 2-day script rather than 1-day (making it equally good for karma-farming, and much worse for meat-farming). A more thorough writup on it can be found [here](https://www.reddit.com/r/kol/wiki/guides/iloath_hccs2).

## c2t_hccs

| creator | link | runtime | turns | workshed | garden |
|---------|------|---------|-------|----------|--------|
| Zdrvst (#3286685) | [here](https://github.com/c2talon/c2t_hccs) | ~10 minutes | 134-135 days | pizza | mushroom |

c2t_hccs is an actively maintained dedicated ASH script for community service designed to be used by a broad group of players. It requires a fair amount of setup, detailed in the README.md, and one unique aspect of this script is that it is designed--or at least functions well--as a Seal Clubber, which makes it valuable for barf farming. It is designed to be appropriately re-entrant, and currently terminates before performing any test that takes more than one turn, unless configured to do otherwise.
