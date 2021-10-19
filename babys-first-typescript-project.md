# So you want to start a Typescript project

Good for you! You've made a great choice. You have a grand future ahead of you, but first let's trapse over the bumpy bit. First things first, check out [Captain Scotch's kol-js-starter](https://github.com/docrostov/kol-js-starter) and click "use this template." Set up your hot new repository--give it a name, maybe a description maybe a loving nickname. The repository's README should give pretty detailed instructions as to how to set things up. After you do everything it says, there's a few things you might want to do:

## Symlink your scripts!

A symbolic link is a way of telling your computer "when I tell you to go to folder X, I really want you to just open up folder Y and look in there." It's very useful when you have your own Typescript project up and running! You'll `yarn run build` to build new js files, but without a symbolic link, you'd have to copy and paste those files into your `kolmafia/scripts`directory, which sucks! If you're bugfixing, you'll have to do it over and over and over again. To make a symbolic link, you'll want to open up a terminal with admin powers, and, depending upon your OS, do a thing:

### Windows
`mklink /D "kolmafiadirectory/scripts/your-repository-name" "repositoryfolder/KoLmafia/scripts`.

### Linux
Man, i don't know

### iOS
Who the hell do you think i am? i don't own more than one computer, and i've never in my life learned a thing that didn't directly apply to me

# So how does this all work?

As it turns out, that's not one question. It's a bunch! More good news: you don't have to read this. This is just to illuminate you, and won't contain crucial information for starting a typescript project.

## Webpack

`webpack` is a bundler. Its job is to make sure that, at the end of this whole rigmarole, you have precisely the files you want to have. Editing your `webpack.config.js` will let you change any webpack-related settings. The main reason why you might edit this is to change how many js files get emitted at the end of compilation, and what their names are. You might also fiddle with where they get emitted. [bean-hccs's webpack config](https://github.com/phulin/bean-hccs/blob/main/webpack.config.js) emits 4 compiled js files. We also need to declare external modules here--these will be `kolmafia` and any ASH scripts you want to import. That way, webpack doesn't spend fruitless hours searching your whole damn house for those modules and abort in a huff.

There are a few other relevant settings in your `webpack.config.js`. Luckily for you (and for me, the guy writing this, who now doesn't have to write as much), [kol-js-starter's webpack config](https://github.com/docrostov/kol-js-starter/blob/main/webpack.config.js) is pretty nicely commented.

## babel

`babel` is a compiler, or perhaps more accurately a _trans_piler. It takes all the juicy Typescript you've written in your many days of tireless toil, and turns it into Javascript. The reason why we call it a transpiler instead of a compiler is that, well, Javascript is also a spicy, high-level language. It's not baby-birding your code into chewed-up, digested chunks of worm-sludge, it's just throwing in the proverbial microwave. This metaphor got really away from me, and frankly it doesn't matter that much. So I'm going to stop using it now, and end this little paragraph.

You will probably not do much with your [babel.config.js](https://github.com/docrostov/kol-js-starter/blob/main/babel.config.js). The target is Rhino, the Java-based Javascript engine that Mafia uses to read your tasty little bits of code. We have a few plugins included, because those are good and useful things to have.

## yarn

`yarn` is your package manager, which means it has _two_ configuration files you'll theoretically want to look at. One of them you should eventually become intimately familiar with: your [package.json](https://github.com/docrostov/kol-js-starter/blob/main/package.json). This is where you list your dependencies like `libram` and `kolmafia` and `babel`. Most of these are pretty necessary! The little `^` symbol in front of the numbers for these packages tell yarn that it can use that version of the particular package _or_ later versions. So when we see `"eslint-config-prettier": "^8.3.0"`, we can happily use version 8.3.1, if such a thing exists at the time of your reading this. You can change the packages your code depends on by either editing your package.json directly, or opening a terminal and very politely typing things like `yarn add eslint-plugin-libram` or `yarn upgrade libram@latest`. If you do, please remember to `yarn install` afterwards.

The other is a `yarn.lock` file. Please don't touch it. It lets yarn keep track of what packages it has and hasn't installed in `node_modules`, and should really only get fiddled with when you use `yarn` to change around these packages.
