# Submitting a Pull Request: a Simple Overview
## What is a Pull Request?

Let's say you've been on the ASS Discord for a while, or you've been messaging with various LASS contributors asking them to make changes to a script. You've submitted a few code snippets, and shared your ideas and concepts. They finally say: "OK, I think this is a great change -- can you put in a pull request on the project?" 

Before we get into the protocol for a pull request, it's important to understand what exactly a pull request is. GitHub is a wonderful tool, and the best-in-class collaboration engine for coders and scripters throughout the world of programming. But it also can be quite opaque; if you aren't immersed in the specifics of Git workflow, it can be extremely hard to understand exactly what certain terms mean. At a high level, a **pull request** involves writing changes to code within a codebase on GitHub, letting the owners of that codebase know that you're suggesting changes, and giving them the opportunity to look through your changes and accept or reject them. It is, in essence, a request for the owners of the codebase to "pull" your changes in from your sample code into the base repository.

Writing a pull request, even for a simple task, can be a bit daunting. This guide represents our best efforts to demystify that process and outline exactly how you would go about structuring a pull request for any LASS repository you'd like to see changes to. We'll be referring to pull requests as "PRs" for most of this guide, because we respect you, your time, and acronyms. One important caveat -- while this is a genericized guide, some projects may have additional hurdles that your PRs need to pass before being added to the base project. The most important example of this is [autoscend](https://github.com/Loathing-Associates-Scripting-Society/autoscend/blob/master/docs/CONTRIBUTING.md), which has a strict series of rules that must be followed to the letter if you want to add code to it. This guide is largely focused on contributing to TypeScript projects, as there are several layers in here (specifically all the Yarn stuff) that are non-obvious to a new contributor and save you a lot of heartache later.

## Basic Pull Requests

When contributing to a project, there are 7 core steps to keep in mind.

**STEP 1: FORK THE PROJECT**
In non-programmer speak, a "fork" is simply a copy of a project; it is your copy that you can mess with code on without messing up the main project. To "fork" a GitHub codebase, go to the core project on the project's GitHub repository, and use the button in the top right corner. It looks like this!

**STEP 2: CLONE YOUR FORK ONTO YOUR LOCAL MACHINE**
Just making your fork is simply not enough. You must also "clone" the fork. I've always felt "cloning" is a weird term for it, but when we say "clone", we simply mean that you are downloading the code to your local machine and initializing all the fun Git architecture around it that allows you to modify and mess with your repository locally. To do this, you will get the URL of your forked project, like so:

After doing this, you will type the following into your command prompt, once you've navigated to a folder you'd feel comfortable working in:
```
git clone [the URL you copied]
```

**STEP 3: INSTALL DEPENDENCIES, IF IT'S A TYPESCRIPT PROJECT** 
This is a pretty important step. Many ASS repositories are written in TypeScript. When you are working on a TypeScript project, there's a variety of tools and necessary repositories that your code editor (likely VSCode) will need to access in order to tell you if you've written your code correctly or properly format your final saves. Luckily, this is actually a very simple step. Just run the following code, which will force yarn to grab the project's dependencies and install them all into your project folder:
```
yarn install
```

**STEP 4: MAKE A BRANCH**
Branching is an important part of the PR process; it ensures that your copied repository stays relatively clean, and that your changes are confined to an easily accessed place that can be compared against the core development code. The best way to think about a branch is that it's just a segregated project folder that has some changes from the main folder. To make a branch, you will need to run the following commands. The first command shows you the branches, the second command adds a branch, and the third command switches you to your newly created branch. 
```
git branch
git branch newBranchName
git switch newBranchName
```

**STEP 5: MAKE YOUR CODE CHANGES**
I can't walk you through this step. Just do whatever you want to do to the code. Fly freely, modifying code as you see fit to fulfill your basest desires. (Or just make the change you need to make, that works too.)

**STEP 6: COMMIT YOUR CHANGES TO YOUR BRANCH**
Now that you've made your changes (and saved them! YOU HAVE TO SAVE THEM!), you need to add your changes to the internet. To do this, you need to do a series of three commands, listed here. The first command adds your new files and ensures that Git understands that you've made changes. The second command applies a commit message, so that you know what your changes mean later on. And the final command pushes your branch up into the branch stored on GitHub.com, which will allow you to make the pull request we have been teasing this entire article.
```
git add .
git commit -m 'insert a message that describes what changes you've made to the code here'
git push origin
```

**STEP 7: MAKE THE DANG PULL REQUEST**
Hey, guess what! You can finally make a pull request. To make the pull request, go to the base branch on GitHub, and click on the "New Pull Request" button.

From here, click on "compare across forks", like so.

This will allow you to select your fork, and from your fork, select the branch you just made.

Type up a descriptive message about your PR, post it up, and wait for the project owner to see it and provide commentary on your beautiful changes. The world is now your oyster. You have made a PR!

## Advanced Pull Request Resources
- [MakeAPullRequest.com](https://makeapullrequest.com/) features a video tutorial on how to make PRs that don't make project owners tear their hair out. It's a useful thing to watch, but may be a bit overwhelming to first time PR hopefuls.
- [This GIST](https://gist.github.com/Chaser324/ce0505fbed06b947d962) features a ton of commands that help outline ways to manage your own forks and clones and all that nonsense. It's a useful reference tool when you simply cannot remember what terminal command you need.