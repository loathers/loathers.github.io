# Introduction
## Why script KOL?
When it was first created, KoL was designed to be a game you could play during your coffee break. You have 40 adventures, and you can spend those adventures fighting Knob Goblins or Fiendish Cans of Asparagus or crafting advanced cocktails. At this point, however, KoL is a game of enormous scope. You may have thousands of turns to play in a day. You may have hundreds of resources to use. For many players, it is impractical to try to do everything by hand.

If you're reading this, you probably already use KoLMafia. It's a fantastic tool to help play turns quickly and efficiently. With scripts written in ASH or JavaScript, you can have KoLMafia make gameplay decisions for you and execute them: you can automate adventuring, inventory management, and even KMails. Hell, you've probably already used some scripts--autoscend and garbage collector are two popular script that we here at LASS produce, and there are dozens of other scripts that help automate play, simplify resources, and make the game a better experience for everyone.

That all being said, everyone's specific needs and goals are different. There is probably something you'd like to do that is not currently supported by a script. Maybe you have a great idea for improving an existing script, or maybe you need to automate a task that no one has a public script that does. Whatever you need to do in this game, there's probably a way to make it better by scripting it.

## What are the tools available for scripting KoL?
Things this should contain:
 - The [KoLMafia wiki](https://wiki.kolmafia.us/index.php/Main_Page) has documentation for most existing functions used in Mafia scripts
- KoLMafia can read scripts written in ASH or Javascript, so anything that supports writing those is a good tool
- [Visual Studio Code](https://code.visualstudio.com/) is a popular software for scriptwriting that offers, among other things, syntax highlighting and source control
- Link to Mafia Wiki

# ASH & Javascript

- ASH is a specific-use KoL language that was built by KoLMafia's developers, starting with Mafia's inception in 2010 (?) and being improved and maintained since.
- Javascript is a fundamental programming language used across the internet, primarily for backend webpage functionality and is supported for code execution in all major browsers.

Here are some basic, one-line tasks that you might do in ASH or JS.

| Syntax | ASH | Javascript |
|---------|------|---|
| Look up an item | `$item[squirming slime larva]`  | `Item.get("squirming slime larva")` |
| Restore MP | `restore_mp(69)` | `restoreMp(69)` |
| Buy a Big Rock | `buy(1, $item[big rock])` | `buy(1, Item.get("big rock")` |
| Kmail Gausie a Holiday Fun | - | - |

Here's an example of a more complex task: returning all one-handed weapons that you have, sorted by familiar weight.
In Javascript, this would look like:
```
Item.all()
  .filter((item) => availableAmount(item) > 0 && weaponHands(item) === 1)
  .sort((a, b) => numericModifier(b, "Familiar Weight") - numericModifier(a, "Familiar Weight"));
```
In ASH, the same task would look like
```
item[int] weapons_by_fam_lbs;		//our desired output
int count;			//how many items meet our criteria? will be used as the key
//first we want to go through all items and list those who meet our requirement
foreach it in $items[]	//go through all items one by one
{
	if(availableAmount(it) == 0 || weaponHands(it) != 1) continue;		//skip this item as it fails our criteria
	weapons_by_fam_lbs[count] = it;
	count++;
}
//next we sort it
sort weapons_by_fam_lbs by numericModifier(value, "Familiar Weight");
```
## ASH
### Common ASH functions and their uses
Here we'd describe basic ASH use cases and link a few of the better primers in the mafia wiki.

### Examples of High-Level ASH Code
KoL player dev TheDictator has many complex ASH scripts available on [his pastebin](https://pastebin.com/u/thedictator).

[Autoscend](https://github.com/Loathing-Associates-Scripting-Society/autoscend) is a LASS-maintained general-use ascension script written in ASH.

Notoriously prolific KoL scripter [Ezandora](https://github.com/Ezandora) has scores of ASH scripts available on her github.

### The Pros and Cons of ASH
| Pros | Cons |
| ---- | ---- |
| Quick & easy to use for short and simple scripts | Can get messy when doing more complicated processes |
| Automatically can access all KoLMafia functions, doesn't require importing | -- |

## Javascript

### Why Javascript?

The single biggest advantage that Javascript has over ASH is the fact that it is widely used for other things beyond KoL scripting. What this means is that when you come across a problem or a concept that doesnt make sense, you will have the entirety of the internet's collective Javascript knowledge to provide you an answer as opposed to just things specifically posted about on the KoLmafia forums. As an added bonus, it means that skills you hone while writing KoL scripts will be applicable elsewhere. 

### How Javascript?

This is a very silly question that I've put into your mouth, and so it gets a very silly answer. An answer to one interpretation of this question is Rhino, a Javascript engine written in Java (despite their names, these languages are unrelated), that Mafia uses to read Javascript, uh, scripts.

An answer to another interpretation of this question is pretty similar to ASH: just start writing. When you write in Javascript, you'll need to import any mafia functions you plan on using, by having a big chunk of text at the top of your script that basically looks like this:
```
const {
 adv1,
 availableAmount,
 buy,
 drink,
 eat,
 getProperty
} = require("kolmafia");
```
Other than that, the world is pretty much your oyster. One thing to note is that you won't need to import fundamental Object types used by KoLMafia: Item, Skill, Effect, Familiar, etc. You will, however, have to import any functions that use these types.

### Improving your JS development with Typescript
"Hold on!", you protest, "I have just learned about Javascript and it seems cool. Why would you introduce something new!" This is a fair critisism, and if you are trying to script simple actions you can probably stop here. That being said, maybe your appetite has been whet and you are ready to tackle a larger project. In these scenarios, it makes sense to consider Typescript. Typescript is a superset of Javascript, meaning that it has everything Javascript has, but it also has more! The primary advantage Typescript has over Javascript is that it has static typing, this is a programming concept which means, in practical terms, that you can catch certain errors when you are writing the code, as opposed to when KoLMafia is executing the code. This gets to be very important when you are dealing with a large script with many functions and variables. However, this added functionality does not come for free. It comes at the cost of having to transpile, here meaning compile your Typescript into Javascript so KoLmafia can understand it. This involves doing additional setup for the script you are writing.

### Linting and Libram
