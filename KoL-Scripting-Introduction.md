# Introduction
## Why script KoL?
When the Kingdom of Loathing (KoL) was first created, it was designed to be a game you could play during your coffee break. Each day you have 40 adventures, and you can spend them fighting Knob Goblins or Fiendish Cans of Asparagus or crafting advanced cocktails. At this point, however, KoL has evolved into a game of enormous scope. You may have thousands of turns to play in a day. You may have hundreds of resources to use. For many players, it is impractical to try to do everything by hand.

If you're reading this, you probably already use [KoLMafia](https://wiki.kolmafia.us/index.php/KoLmafia_Guide). It's a fantastic tool to help play turns quickly and efficiently. With scripts written in ASH or JavaScript, you can have KoLMafia make gameplay decisions for you and execute them: you can automate adventuring, inventory management, and even KMails. Hell, you've probably already used some scripts--[autoscend](https://github.com/Loathing-Associates-Scripting-Society/autoscend) and [garbage collector](https://github.com/Loathing-Associates-Scripting-Society/garbage-collector) are two popular scripts that we here at LASS produce, and there are dozens of other scripts that help automate play, simplify resources, and make the game a better experience for everyone.

That all being said, everyone's specific needs and goals are different. There is probably something you'd like to do that is not currently supported by a script. Maybe you have a great idea for improving an existing script, or maybe you need to automate a task that no one has a public script that does. Whatever you need to do in this game, there's probably a way to make it better by scripting it.

## What are the tools and resources available for scripting KoL?
There are a number of useful resources you should leverage as you start learning about scripting in KoL:
- The [KoLMafia wiki](https://wiki.kolmafia.us/index.php/Main_Page) has documentation for most existing functions used in Mafia scripts
- KoLMafia can read scripts written in ASH or Javascript, so anything that supports writing those is a good tool; the rest of this page will discuss these languages
- [Visual Studio Code](https://code.visualstudio.com/) is a popular software for scriptwriting that offers, among other things, syntax highlighting and source control; it's highly recommended for your development environment!
- Sometimes, the best way to learn is to read scripts made by others. You can find a wealth of these on the [KOLMafia Forums](https://kolmafia.us/#repository.3) or on the [LASS GitHub](https://github.com/Loathing-Associates-Scripting-Society/). 
- Another great place to learn is to visit the [Ascension Speed Society Discord](https://discord.com/invite/k3vR3caDkF); the #mafia-and-scripting channel is full of helpful folk who'd be happy to show you the ropes.

# ASH & Javascript

- ASH is a specific-use KoL language that was built by KoLMafia's developers, starting with [Mafia's inception in 2005](http://forums.kingdomofloathing.com/vb/showthread.php?t=88408) and being improved and maintained since
- Javascript is a fundamental programming language used across the internet, primarily for backend webpage functionality and is supported for code execution in all major browsers

Here are some basic, one-line tasks that you might do in ASH or JS.

| Syntax | ASH | Javascript |
|---------|------|---|
| Look up an item | `$item[squirming slime larva]`  | `Item.get("squirming slime larva")` |
| Restore MP | `restore_mp(69)` | `restoreMp(69)` |
| Buy a Big Rock | `buy(1, $item[big rock])` | `buy(1, Item.get("big rock"))` |

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
	if(available_amount(it) == 0 || weapon_hands(it) != 1) continue;		//skip this item as it fails our criteria
	weapons_by_fam_lbs[count] = it;
	count++;
}
//next we sort it
sort weapons_by_fam_lbs by numericModifier(value, "Familiar Weight");
```
## ASH
### Using Common ASH Functions (via Example)
There are a number of useful starter ASH tutorials on the KoLMafia wiki and scattered about Mafia's old home on sourceforge. One that I find particularly useful is [this set of two basic examples of ASH scripts](https://kolmafia.sourceforge.io/advanced.html). At a high level, when thinking about how to use ASH (or, really, any new programming language), the best way to go about it is to start with a small abstract piece of something useful and extend your reach beyond it by bringing in things that add complication and heft to the initial goal. As a start, let's use a very simple, very effective use-case: drinking a nightcap, via the "drink" command.
```
drink(1,$item[emergency margarita]);
```
This is easy and straightforward. You could simply save this as nightCap.ash, run it at the end of every day, and you'd be good on your last drink of the day so long as you always had an Emergency Margarita in your inventory. But what if you didn't? It turns out nightcaps can be a bit more complicated! Let's add a check that purchases an emergency margarita for you, if you don't have one lying around.
```
item nightcap = $item[emergency margarita]);

if (available_amount(nightcap) == 0) buy(1, nightcap);

drink(1, nightcap);
```
But wait! What if a nefarious actor bought up every single emergency margarita in the mall? Computers are smart, but they're also extraordinarily literal -- if you tell it to purchase a margarita, it will do so, no matter how much meat they cost. Let's add a catch that aborts if margaritas become way too expensive to justify. 

```
item nightcap = $item[emergency margarita]);

if (available_amount(nightcap) == 0) buy(1, nightcap, 60000);

if (available_amount(nightcap) == 0) {
  print("Margs are too pricy for me", "red");
  abort();
}

drink(1, nightcap);
```

There's another issue here -- this code doesn't actually take into account how much drunkenness you have. What if you actually forgot to drink a few points of liver before you ran the script? That might equate to lost adventures, and that just won't do. Let's add a function to this that fills your liver with splendid martinis before the margarita is consumed.


```
item filler = $item[splendid martini];
while (my_inebriety() < inebriety_limit()) {
  if (available_amount(filler) == 0) buy(1, filler, 10000);
  if (available_amount(filler) == 0) {
    print("Splendids are too pricy for me", "red");
    abort();
  }
  drink(1, filler);
}

item nightcap = $item[emergency margarita]);

if (available_amount(nightcap) == 0) buy(1, nightcap, 60000);

if (available_amount(nightcap) == 0) {
  print("Margs are too pricy for me", "red");
  abort();
}

drink(1, nightcap);
```

Please note that while loops can be very dangerous; you need to make sure that what you are doing increments, and if it doesn't, you need to include some sort of catch that allows it to break out of an infinite loop. Regardless, there's one last issue here. What about Stooper, the familiar that gives you +1 drunkenness? Let's make sure we're equipping our little buddy for the extra turns.

```
if (have_familiar($familiar[stooper])) use_familiar($familiar[stooper]);
item filler = $item[splendid martini];
while (my_inebriety() < inebriety_limit()) {
  if (available_amount(filler) == 0) buy(1, filler, 10000);
  if (available_amount(filler) == 0) {
    print("Splendids are too pricy for me", "red");
    abort();
  }
  drink(1, filler);
}

item nightcap = $item[emergency margarita]);

if (available_amount(nightcap) == 0) buy(1, nightcap, 60000);

if (available_amount(nightcap) == 0) {
  print("Margs are too pricy for me", "red");
  abort();
}

drink(1, nightcap);
```

Oh, wait. One last thing! Why not maximize our outfit for adventures, so that this can truly be the last thing we do for the day? Might as well, right?

```
if (have_familiar($familiar[stooper])) use_familiar($familiar[stooper]);
item filler = $item[splendid martini];
while (my_inebriety() < inebriety_limit()) {
  if (available_amount(filler) == 0) buy(1, filler, 10000);
  if (available_amount(filler) == 0) {
    print("Splendids are too pricy for me", "red");
    abort();
  }
  drink(1, filler);
}

item nightcap = $item[emergency margarita]);

if (available_amount(nightcap) == 0) buy(1, nightcap, 60000);

if (available_amount(nightcap) == 0) {
  print("Margs are too pricy for me", "red");
  abort();
}

drink(1, nightcap);

if (have_familiar($familiar[left-hand man])) use_familiar($familiar[left-hand man]);
maximize("Adventures", false);
```

Fantastic. We have a script. We've used quite a few functions in this script,, including [insert list here]. When you're building your own scripts, one of the best ways to learn is to simply pick a simple task and start thinking through what kind of complications could make a simple thing less straightforward. When you figure those out, and start solving them via mafia functions, you quickly turn a very simple one-line script into a larger scale construction that teaches you about all sorts of new functions and commands. 

### Examples of High-Level ASH Code
TheDictator (a player /dev) has many complex ASH scripts available on [his pastebin](https://pastebin.com/u/thedictator).

[Autoscend](https://github.com/Loathing-Associates-Scripting-Society/autoscend) is a LASS-maintained general-use ascension script written in ASH.

Notoriously prolific KoL scripter [Ezandora](https://github.com/Ezandora) has scores of ASH scripts available on her github.

### The Pros and Cons of ASH
| Pros | Cons |
| ---- | ---- |
| Quick & easy to use for short and simple scripts | Can get messy when doing more complicated processes |
| Automatically can access all KoLMafia functions, doesn't require importing | -- |

## Javascript

### Why Javascript?

The single biggest advantage that Javascript has over ASH is the fact that it is widely used for other things beyond KoL scripting. This means that when you come across a problem or a concept that doesn't make sense, you will have the entirety of the internet's collective Javascript knowledge to provide you an answer as opposed to just things specifically posted about on the KoLmafia forums. As an added bonus, it means that skills you hone while writing KoL scripts will be applicable elsewhere. 

### How Javascript?

This is a very silly question that I've put into your mouth, and so it gets a very silly answer. An answer to one interpretation of this question is Rhino, a Javascript engine written in Java (despite their names, these languages are unrelated), that Mafia uses to read Javascript, uh, scripts.

An answer to another interpretation of this question is pretty similar to ASH: just start writing. When you write in Javascript, you'll need to import any mafia functions you plan on using, by having a big chunk of text at the top of your script that essentially looks like this:
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

One other important note: the KoLMafia Wiki was written to support ASH. This means that functions on the Mafia wiki are described using their ASH naming conventions (and with written-out ASH examples). Generally speaking, JS uses camel case (e.g. thisIsYourVariable) while ASH uses snake case (e.g. this_is_your_variable). Tactically, what this means is that when you access an ASH page to get information about a specific function (like, say, [elemental_resistance](https://wiki.kolmafia.us/index.php/Elemental_resistance)), you need to be cognizant of the fact that any JS script that references this function will require elementalResistance instead of elemental_resistance. It's a small change, but important to keep in mind when using the wiki to inform your available functions. The other biggest difference is that any fnction that returns a Map in ASH will return an Object in Javascript, so doing `getCampground().has("Witchess Set")` won't tell you anything helpful.

### Improving your JS development with Typescript
"Hold on!", you protest, "I have just learned about Javascript and it seems cool. Why would you introduce something new!" This is a fair criticism, and if you are trying to script simple actions you can probably stop here. That being said, maybe your appetite has been whet and you are ready to tackle a larger project. In these scenarios, it makes sense to consider Typescript. Typescript is a superset of Javascript, meaning that it has everything Javascript has, but it also has more! The primary advantage Typescript has over Javascript is that it has static typing, this is a programming concept which means, in practical terms, that you can catch certain errors when you are writing the code, as opposed to when KoLMafia is executing the code. This gets to be very important when you are dealing with a large script containing many functions and variables. However, this added functionality does not come for free. It comes at the cost of having to transpile, here meaning compiling your Typescript into Javascript so KoLmafia can understand it. This involves doing additional setup for the script you are writing.

### Linting and Libram

LASS provides two very helpful packages for TypeScript projects. The first is [Libram](https://github.com/Loathing-Associates-Scripting-Society/libram), an all-purpose toolkit meant to extend existing mafia functions, with the end goal of making it just about the only external module any KoL scripter will ever need. Its features include the `get()` function, which is a modified version of mafia's `getProperty()` that returns objects of the appropriate type. It also has a system of template literals that makes it slightly easier to talk about Items and Familiars and Skills and the sort. This small change adds up a lot:
```
if (get("_sourceTerminalDigitizeMonster").meatDrop > $monster`garbage tourist`.meatDrop)
```
is much shorter and more legible than
```
if (toMonster(getProperty("_sourceTerminalDigitizeMonster")).meatDrop > Monster.get("garbage tourist").meatDrop)
```
The other spicy package we provide is libram-linked: it is the [eslint Libram plugin](https://github.com/Loathing-Associates-Scripting-Society/eslint-plugin-libram), which is used across all LASS projects. ESLint is a tool that analyzes Javascript and TypeScript code for bad code and bad form, and the plugin adds a variety of features, the most important of which is its ability to verify constants. Normally, in Javascript, if I write something like
```
Item.get("Unwrapped retro knock-off superhero cape")
```
the code will get through just fine, it'll reach mafia, and mafia'll throw a tantrum over the fact that there is no such item. With the eslint Libram plugin, however, it'll catch that
```
$item`Unwrapped retro knock-off superhero cape`
```
is wrong, and you'll be able to correct it before compiling and running your code.
