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

Then, a table with some short 1-liners of how you'd accomplish things in one versus the other. 

| Syntax | ASH | Javascript |
|---------|------|---|
| Look up an item | $item[squirming slime larva]  | Item.get("squirming slime larva") |
| Restore MP | restore_mp(69) | restoreMp(69) |
| Buy a Big Rock | buy(1, $item[big rock]) | buy(1, Item.get("big rock") |
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
I'm actually not entirely sure how to do that
That's just me not knowing how to do nontrivial ASH though
```
## ASH
### Common ASH functions and their uses
Here we'd describe basic ASH use cases and link a few of the better primers in the mafia wiki.

### Examples of High-Level ASH Code
This would probably just be a link to Dictator's pastebin and then "lol" 

### The Pros and Cons of ASH
Bulleted list in a table outlining good/bad of ASH as a language.

## Javascript

### Why Javascript?

### Improving your JS development with Typescript

### Linting and Libram
