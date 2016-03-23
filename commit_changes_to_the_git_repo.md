# Add The Project To A Git Repo

## Goals
* Commit your recent changes to the git repository

In order to keep track of changes which are being made, and eventually share the code for this application with other developers on our team, we need to add and commit our changes to the git repository that we created earlier.

## Steps
### Step 1
Type this in the bash tab (aka terminal):
```bash
git status
```
As a refresher, `git status` tells you everything git sees as modified, new, or missing.

This command will show a list of files
* `Untracked files` these are files which we've added since our last commit
* `Changes not staged for commit` these are files which are already under version control, but haven't been `staged` (a fancy word for prepared to be commited)
* `Changes to be committed` you may not see this yet, but when you do it means that the files are ready for you to use the `git commit` command (commit adds the changes to your git repository)

### Step 2
Type this in the terminal:
```bash
git add .
```
git add . tells git that you want to add the current directory (aka .) and everything under it to the repo.

### Step 2
Type this in the terminal:
```bash
git status
```
Now you should see that all of files are listed under `Changes to be committed`.

### Step 3
Type this in the terminal (__be sure to use the -m parameter in this command__):
```bash
git commit -m "latest updates to application"
```
`git commit` tells git to actually do all things you've said you wanted to do.

This is done in two steps so you can group multiple changes together.

`-m "Added all the things"` is just a shortcut to say what your commit message is. You can skip that part and git will bring up an editor to fill out a more detailed message.

__IMPORTANT__: if you forget the -m parameter when performing this step on cloud9, you will end up in the vim editor.  To get out of this editor you should be able to type in `:q!` to get out without making any changes.  If that doesn't work, you may be in INSERT mode (look for INSERT in the lower right hand corner of the `bash` tab), you can use the escape (or ESC) key to get out of this mode and try `:q!` again

### Step 6
Type this in the terminal:
```bash
git status
```
Now you should see something like `nothing to commit`, working directory clean which means you've committed all of your changes.

## Explanation
By continually checking your code changes into git, you're maintaining a record of your changes.  This way, if anything ever breaks, or you make a change you don't like, you can use git as an all-powerful "undo" technique. But that only works when you remember to __commit early and often__!

## Next Step:
Go on to [Creating A Migration](creating_a_migration.md)
