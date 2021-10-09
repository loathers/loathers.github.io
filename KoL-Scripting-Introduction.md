# Introduction
## Why script KOL?
Define the goals of KOL scripting with examples of what you can do with scripts (automate ascensions, automate farming, bring up resources, etc; absolute base-level things, to explain what the underlying reasoning is behind scripting. We could even include a snippet of my old farming spreadsheet where I tried to calculate how much time it took to do barf farming in the years I did it manually before I scripted it, maybe?)

## What are the tools available for scripting KoL?
Things this should contain:
- very basic summary of ASH/TS
- Link to VSCode
- Link to Mafia Wiki

# ASH & Javascript
Start with a two-bullet comparison simply describing each language. Something like:

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
Item.all().filter(
  (item) =>
    availableAmount(item) > 0 &&
    weaponHands(item) === 1
  ).sort((a, b) => 
    numericModifier(b, "Familiar Weight") - numericModifier(a, "Familiar Weight")
  )
)
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
