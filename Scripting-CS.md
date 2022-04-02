# Scripting Community Service
## Introduction

[Community Service](https://kol.coldfront.net/thekolwiki/index.php/Community_Service) (CS) has become a commonly scripted challenge path due to its simplicity and speed (both in-game and real-time). Rather than need to perform all of the standard council quests, the player gets 11 tasks that take a single button click each. Said tasks can be accelerated by buffing up things like stats, familiar weight or item drops. It doesn't take a lot of shiny to do a two-day run, and sufficiently loaded accounts can perform replicable one-day ascensions with low turn counts and organ use. This is desirable as it allows for a second shot at valuable once per day item generation, as well as extra aftercore turns for farming or event participation.

Unfortunately, it's not easy to create a one-size-fits-all high-end CS solution due to a lot of moving parts. The path rewards access to a lot of old shinies, but it's possible to get creative and plug holes in your setup in various unconventional ways. Once you have an operational CS run plan, it's not that hard to precisely execute it. Scripting can assist with consistency, doing anything from buffing you up so you don't forget some effect all the way to performing a whole run for you.

## Creating a Run Plan

A typical CS ascension consists of the following stages:
- Using [borrowed time](https://kol.coldfront.net/thekolwiki/index.php/Borrowed_time) and doing coil wire, a 60-turn task that can't be accelerated.
- Using the resulting reward to kick-start your stats, and levelling up as quickly as possible via (free) scaling fights to help with the stat tests.
- Performing the stat tests, and then all others:
    - It's common to group hot resistance, noncombat and familiar weight together as they all benefit from having a heavy familiar - [exotic parrot](https://kol.coldfront.net/thekolwiki/index.php/Exotic_Parrot) helps with hot resistance, while [disgeist](https://kol.coldfront.net/thekolwiki/index.php/Disgeist_(familiar)) helps with noncombat. Plus if you do this early then you can use some of the familiar weight buffs during levelling.
    - A number of buffs are shared between weapon damage and spell damage.
    - Doing the item test last allows the item buffs used to carry over into aftercore, and if you have the [emotion chip](https://kol.coldfront.net/thekolwiki/index.php/Emotionally_Chipped) then you can use [Feeling Lost](https://kol.coldfront.net/thekolwiki/index.php/Feeling_Lost) for an additional +60% on the test; one of your first post-run actions should be to remove the effect due to its built-in Teleportitis.

Levelling is one of the more individualised portions of the run. The general idea is to use free fights with scaling monsters, derived from various IotMs like the [Neverending Party](https://kol.coldfront.net/thekolwiki/index.php/The_Neverending_Party). The more free fights you have the better, and access to the [makeshift garbage shirt](https://kol.coldfront.net/thekolwiki/index.php/Makeshift_garbage_shirt) doubles their yields. The higher you can pump your main stat and your experience gains from fights the better, which makes [Sweet Synthesis](https://kol.coldfront.net/thekolwiki/index.php/Sweet_Synthesis) with its +300% stat and +50% experience gain buffs a very desirable skill to have access to. However, as mentioned, it is possible to use replacement shinies to achieve these goals. For example, one can use a [diabolic pizza](https://kol.coldfront.net/thekolwiki/index.php/Diabolic_pizza) to get a [+500% buff](https://kol.coldfront.net/thekolwiki/index.php/Mallowed_Out) to all stats, which helps both with levelling and the subsequent tests. Another option is to use copies from the backup camera or pocket professor to get extra free scaling monster fights.

The non-stat tests are pretty much just a checklist. Captain Scotch created a [very helpful sheet](https://docs.google.com/spreadsheets/d/1CooctXongsf2nt1JmR8G-Qm_Dhs4V6oHDO04hLRCI_s/edit#gid=1299653939) listing the various buffs that can be used to accelerate the tests. Make a copy of the sheet and filter the lists to what you have access to, possibly adding some buffs or items that got skipped. [Bow-Legged Swagger](https://kol.coldfront.net/thekolwiki/index.php/Bow-Legged_Swagger_(effect)) and [Steely-Eyed Squint](https://kol.coldfront.net/thekolwiki/index.php/Steely-Eyed_Squint_(effect)) save a lot of turns. The [Fourth of May Cosplay Saber](https://kol.coldfront.net/thekolwiki/index.php/Fourth_of_May_Cosplay_Saber) with its wonky combat-ending mechanic allows you to carry out buffs like [Meteor Showered](https://kol.coldfront.net/thekolwiki/index.php/Meteor_Showered) that were not meant to leave combat. But other than that there aren't any crazy turn saves, it's more about how much quantity you can put together. Remember that not every test needs to be capped, and familiar weight and spell damage in particular are likely to take a long time. The sheet is going to be a good estimate of how long your run is likely to take, as stat tests are likely to be quick and there's nothing you can do about coil wire. If it seems that six [astral pilsners](https://kol.coldfront.net/thekolwiki/index.php/Astral_pilsner) plus whatever "free" turn generation you may have won't be enough to get you to finish the run in time, then you'll need to consider how to make extra required turns as part of your plan.

Another aspect of planning a run are softcore pulls. These can be used to cut turns from tests, or compensate for lacking certain IotM. For example, it's common to pull [borrowed time](https://kol.coldfront.net/thekolwiki/index.php/Borrowed_time) to help with generating turns for coil wire if not in possession of [Clip Art](https://kol.coldfront.net/thekolwiki/index.php/Summon_Clip_Art).

If in need of assistance, ask in `#community-service` in the [ASS discord](https://discord.gg/JqwXkyWF4m). Be prepared with your [snapshot](http://forums.kingdomofloathing.com/vb/showthread.php?t=218735), as it allows for better theorycrafting of a levelling plan or whatever else you may need help with. There are a lot of helpful pinned messages, such as a full-shiny ordering of scaling fights based on their caps or lists of easily accessible pizza ingredients. The folks there are very helpful - I went from an inattentive AFK farmer to creating my own CS script in the space of a couple months with their assistance.

## Doing a Run

Putting together a plan can feel nebulous, and it's a good idea to try it out in practice once it takes a bit of shape. Do whatever pre-run preparations your plan assumes, hop the gash, and try to carry things out. While you're doing so, take excruciatingly detailed notes for every single fight you do. Write down buffs you cast, take screenshots of outfits you've put on. Once you clear the stat test hurdle then you can relax a bit with the note-taking as the Scotch sheet has you covered for the tests. If anything, you may find yourself missing some of the buffs you had planned! In that event, use mafia's `modtrace` to compare against the sheet. Something as basic as counting how many modifiers you have in each can help you determine how many you're missing, and then you can go fishing for what you forgot.

The end result will be a nice confidence boost as you perform your plan in action, get a run out of it, and obtain a very solid set of detailed notes to work with going forward. Now if you were to do the run again, the experience and notes will let you do so quicker. The first go through is the hardest, it gets easier once you're done with it.

Another thing that's likely to happen is you'll look over your notes, ponder your plan, and notice certain things you could improve. My original plan assumed using [Map the Monsters](https://kol.coldfront.net/thekolwiki/index.php/Map_the_Monsters) in a zone where the skill does not work, so I had to alter my plans to work around that. I ended up altering the amount of familiar weight that was needed at that point in the run, which led me to change my [hatter buff](https://kol.coldfront.net/thekolwiki/index.php/The_Mad_Tea_Party) and the order in which I was using my familiars. This iterating process is likely to continue going forward. For example, I recently realised that I can sometimes skip summoning a Chubby and Plump bar for my Synthesis plan, if I happen upon an early lavender candy heart.

## Initial Automation

Now that you're armed with an exhaustive set of notes that let you perform your desired CS run, you can continue performing those runs with reduced effort by following your steps. However, this does leave room for human error (seeing how transferring a Scotch sheet to in-game buffs can already be challenging), and sounds rather mundane. Thankfully, scripting is perfect for this sort of thing, and the notes are the perfect foundation to use for it.

Let's consider an example scenario. You are a Pastamancer, you just did coil wire, and you're buffing up your Mysticality to go beat up various free fights. Your notes feature the following list of effects that you acquired to help you with this task:
- [Uncucumbered](https://kol.coldfront.net/thekolwiki/index.php/Uncucumbered)
- [Favored by Lyle](https://kol.coldfront.net/thekolwiki/index.php/Favored_by_Lyle)
- [Starry-Eyed](https://kol.coldfront.net/thekolwiki/index.php/Starry-Eyed)
- [Feeling Excited](https://kol.coldfront.net/thekolwiki/index.php/Feeling_Excited)
- [Song of Bravado](https://kol.coldfront.net/thekolwiki/index.php/Song_of_Bravado_(effect))
- [Glittering Eyelashes](https://kol.coldfront.net/thekolwiki/index.php/Glittering_Eyelashes)
- [Big](https://kol.coldfront.net/thekolwiki/index.php/Big_(effect))
- [Confidence of the Votive](https://kol.coldfront.net/thekolwiki/index.php/Confidence_of_the_Votive)
- [Broad-Spectrum Vaccine](https://kol.coldfront.net/thekolwiki/index.php/Broad-Spectrum_Vaccine)
- [Total Protonic Reversal](https://kol.coldfront.net/thekolwiki/index.php/Total_Protonic_Reversal)
- [Mystically Oiled](https://kol.coldfront.net/thekolwiki/index.php/Mystically_Oiled)
- [Stevedave's Shanty of Superiority](https://kol.coldfront.net/thekolwiki/index.php/Stevedave%27s_Shanty_of_Superiority_(effect))

Now that you are armed in this list of buffs, you can go and retrieve them one by one, visiting the appropriate locations, casting the appropriate skills. But all of them can be acquired via mafia's CLI, which you're likely familiar with. So for example you can get Feeling Excited by writing `cast 1 Feel Excitement` into the CLI, similar to what you could do in chat. Seeking out the equivalent to all of the effects above yields the following list of calls:

```
daycare mysticality;
monorail buff;
telescope look high;
cast 1 Feel Excitement;
cast 1 Song of Bravado;
use 1 glittery mascara;
cast 1 Get Big;
use 1 votive of confidence;
spacegate vaccine 2;
crossstreams;
use 1 ointment of the occult;
cast 1 Stevedave's Shanty of Superiority;
```

You can take the text above and paste it into the CLI and it will acquire the effects for you. This reduces the chance you'll miss anything. You could do a CS run in this fashion - have a list of CLI calls to paste in, then do combats manually, and hit up the tests once prepared. Rather than needing to follow the notes to a dot, you now copy-paste things into the CLI. Things are already getting somewhat automatic, and they can get even more automatic if you want! Next stop - combat.

