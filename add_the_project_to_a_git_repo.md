# Add The Project To A Git Repo

## Goals
* Create a local git repository
* Add all our files to the git repository

In order to publish our application, we need to add our application and any changes we make over time to a "revision control system". In our case we're going to use git because it is (relatively) easy and it is what our app server, Heroku, uses.

## Steps
### Step 1
Type this in the bash tab (aka terminal):
```bash
git init
```
It doesn't look like anything really happened, but `git init` initialized a new repository in a hidden directory called `.git`.

You can see this by typing `ls -a` (list all files).

### Step 2
Type this in the terminal:
```bash
git status
```
`git status` tells you everything git sees as modified, new, or missing.

You should see a ton of stuff under Untracked files.

### Step 3
Type this in the terminal:
```bash
git add .
```
git add . tells git that you want to add the current directory (aka .) and everything under it to the repo.

---
git add

With Git, there are usually many ways to do very similar things.

* git add foo.txt adds a file named foo.txt
* git add . adds all new files and changed files, but keeps files that you've deleted
* git add -A adds everything, including deletions
"Adding deletions" may sound weird, but if you think of a version control system as keeping track of changes, it might make more sense. Most people use `git add .` but `git add -A` can be safer. No matter what, `git status` is your friend.

---

### Step 4
Type this in the terminal:
```bash
git status
```
Now you should see a bunch of files listed under Changes to be committed.

### Step 5
Type this in the terminal:
```bash
git commit -m "Added all the things"
```
`git commit` tells git to actually do all things you've said you wanted to do.

This is done in two steps so you can group multiple changes together.

`-m "Added all the things"` is just a shortcut to say what your commit message is. You can skip that part and git will bring up an editor to fill out a more detailed message.

### Step 6
Type this in the terminal:
```bash
git status
```
Now you should see something like nothing to commit, working directory clean which means you've committed all of your changes.

## Explanation
By checking your application into git now, you're creating a record of your starting point. Whenever you make a change during today's workshop, we'll add it to git before moving on. This way, if anything ever breaks, or you make a change you don't like, you can use git as an all-powerful "undo" technique. But that only works when you remember to commit early and often!

## Next Step:
Go on to [Creating A Migration](creating_a_migration.md)
