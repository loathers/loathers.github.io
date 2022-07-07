# Awesome KoL Scripts

This document contains a list of commonly used and (largely) regularly updated scripts that are used for a wide variety of different use cases. We've sorted these scripts out into four distinct categories, which are (in some cases) split into smaller sub-categories, such as farming & ascension within automation:

- **Automation**: Scripts that allow you to automate pieces of KOL, usually for farming purposes.
- **Organization**: Scripts that organize items and resources in specific ways
- **Informational**: Scripts that can be used to give you information and summaries for your account
- **Relay**: Scripts that create or modify pages in KoLMafia's relay browser, for added UI benefits and information

If you would like to submit a script to be placed on this page, please post in the **#mafia-and-scripting** channel in the [Ascension Speed Society discord](https://discord.gg/8p7hh8BRSF); tag Captain Scotch (whose Discord name is DocRostov#7004) to ensure it gets seen in a timely fashion.

## Automation (Ascension)

### LoopCasual
| owner | link | usage |
|---------|------|---------|
| Kasekopf (#1210810) | [LoopCasual GitHub](https://github.com/Kasekopf/loop-casual) | Compile the script's JS file, import into your scripts folder, then run the script in the GCLI |

**LoopCasual** aims to complete a casual ascension in one day. It tries to use as few turns as possible to accomplish this, allowing someone to use one of the farming scripts below to use the rest of a character's turns. At a high level, this will power your character up to level 13 and complete quests using a relatively customized quest engine. It was originally built by Kasekopf to work very specifically for Kasekopf's account; it is more flexible than it used to be, but we would recommend having patience and being ready to work with account-specific bugs as you work your account into a place where LoopCasual works out-of-the-box. Kasekopf is an active member on the [ASS discord](https://discord.gg/8p7hh8BRSF); if you have questions regarding LoopCasual, please post issues on the GitHub or reach out in the **#mafia-and-scripting** channel. Please note as well that **LoopCasual requires compiling JavaScript from TypeScript**. For more on how to do that, please visit our [KOL TS Starter repository](https://github.com/docrostov/kol-ts-starter).

## Automation (Farming)

### Garbage Collector (AKA Garbo)
| owner | link | usage |
|---------|------|---------|
| [L. A. S. S.](https://github.com/Loathing-Associates-Scripting-Society) | [GARBO GitHub](https://github.com/Loathing-Associates-Scripting-Society/garbage-collector) | Run the script in the GCLI |

**Garbage Collector** (more commonly known as "Garbo") is the Loathing Legion Knife of Barf Mountain farming scripts. It does it all! Barf Mountain is a zone from the 2015 Dinseylandfill IOTM. It features the highest ambient meat drop in an infinitely accessible zone in the game. Garbo will buy a ticket to Barf Mountain and use every drop of a player's resources to earn meat -- it features bespoke valuations engines that analyze the value of every free fight source, a knapsack-style dieting system that tabulates potential profit given current mall prices of every possible diet configuration, and both Embezzler/Yachtzee maximization chain logic to use every copier in the game. Garbo is actively developed, and generally supports new IOTMs within a week after their release; for questions or comments, there is a well-described system for bug reports and feature requests within the pins in the **#garbage-collector** channel within the [ASS discord](https://discord.gg/8p7hh8BRSF).

### freecandydotexe
| owner | link | usage |
|---------|------|---------|
| [L. A. S. S.](https://github.com/Loathing-Associates-Scripting-Society) | [freecandy GitHub](https://github.com/loathing-Associates-Scripting-Society/freecandydotexe) | Run the script in the GCLI |

**freecandydotexe** is a script meant to run a large gob of turns for trick or treating. In KOL, Halloween is a massively valuable exercise, often netting users tens of millions of meat in a single day; freecandy is a script that both trick or treats and fights things like guaranteed kramcos, voting monsters, and nemesis hitmen. It handles familiar swaps (to properly utilize your Trick or Treating Tot) and fills your Pantsgiving stomach. Freecandydotexe is actively developed, and (with some exceptions) will support new IOTMs within 1-2 Halloweens of the IOTM's introduction. For questions, bug reports, or comments, please post relevant details in the **#freecandydotexe support thread** thread within the **#garbage-collector** channel on the [ASS discord](https://discord.gg/8p7hh8BRSF).

### COMBO
| owner | link | usage |
|---------|------|---------|
| [L. A. S. S.](https://github.com/Loathing-Associates-Scripting-Society) | [COMBO GitHub](https://github.com/loathing-Associates-Scripting-Society/combo) | Run the script in the GCLI |

**COMBO** is a beach-combing script that will harvest known scarce tiles for fun and profit. When the beach comb was introduced in KOL, TPTB introduced 1000 "scarce" tiles; these tiles, when refreshed, contain the rarest items the beach has to offer, such as cursed pirate gear, meteorite fragments, and rainbow pearls. The tiles refresh on an unknown cadence, and when they are not refreshed, they are indistinguishable from common tiles. However, many enterprising souls spent years combing the beach to figure out exactly where these 1000 tiles are, so that they would be more likely than anyone else to get the scarce items when the tiles refreshed -- COMBO is a project that publicizes these tiles, allowing anyone to have that increased chance at getting rares from their beach. COMBO is a nonprofit project supported by volunteers. Please do not yell at us. For questions, bug reports, and comments, please post relevant details in the **"sharing-new-scarce-tiles"** thread within the **#spading** channel on the [ASS discord](https://discord.gg/8p7hh8BRSF).

## Organization (Inventory Management)

### Philter
| owner | link | usage |
|---------|------|---------|
| [L. A. S. S.](https://github.com/Loathing-Associates-Scripting-Society) | [Philter GitHub](https://github.com/loathing-Associates-Scripting-Society/philter) | Run the script in the GCLI, after relay-organizing your items |

**Philter** is a next-generation version of a classic KOL script, the "OCD Inventory Control" system designed by Bale of the KOLMafia forums. Philter's goal is to cleanse your inventory of junk items, autoselling & using items that warrant that action and mallselling or Sellbot-sending items that warrant mall action. This involves a detailed relay interface that can be used to sort, organize, and create rulesets around what you want Philter to do with your items. For a sample ruleset, Butts McGruff has shared his rules on the [ASS discord](https://discord.gg/8p7hh8BRSF) in a pinned post within the **#mafia-and-scripting** channel. It is worth noting that making a ruleset you are comfortable with takes quite a lot of time -- expect a significant period of adjustment even if you start at Butts' well-designed sample ruleset. 

### Keeping Tabs
| owner | link | usage |
|---------|------|---------|
| ReverKiller (#892618) | [Keeping Tabs GitHub](https://github.com/pstalcup/keeping-tabs) | Run the script in the GCLI, after tab-organizing your items |

**Keeping Tabs** is a lower-user-effort version of Philter (discussed above), which uses the native KOL inventory tab system to organize your items and allow users to modify their desired tab behavior. Essentially, you as a user just need to make a number of custom-named tabs that reflect what you want to do to your items; running `keeping-tabs` will then do exactly what you told it to do, flushing your inventory out and emptying it in the way you outlined. There is no active support system for Keeping Tabs -- if you have questions, please post an [issue](https://github.com/pstalcup/keeping-tabs/issues) on the GitHub linked above and Rev will get to it on his own time. 

## Informational

### KoLAccountVal
| owner | link | usage |
|---------|------|---------|
| Irrat (#3469406) | [KolAccountVal GitHub](https://github.com/pstalcup/keeping-tabs) | Run the script in the GCLI |

**AccountVal** is a rewrite of a script by the wise and curious Soolar by the also-wise and ever-curious Irrat. It will analyze your inventory and report back on the value of everything you've got, and will do so slightly faster than the script it was re-written from, as it was written in JavaScript and has some limited caching support. It also has an option that only generates the value of your tradeable items; ergo, you can both revel in the riches you've bound to your account and get excited about the un-accumulated riches your tradeable items could give you.

## Relay (General Purpose)
## Relay (Supplemental UI for IOTMs)
