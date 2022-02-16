Week 2 
Lesson on undoing changes, taken by instructor Francis. 

Under undoing changes, we have:

* Git checkout.
* Git clean.
* Git revert.
* Git reset.
* Git rm.

We’ll be starting with Git status.
<b><p style="text-align: center;">### Git checkout</p></b>

## Git checkout

Commonly used to switch branch but is command has various use case which is quite outstanding for a single command.

`git checkout` operates on branches, files and commits.


Basic usage:

`git checkout <file|commit|branch>`








<b><p style="text-align: center;">### Git clean</p></b>

## Git clean

`git clean` is a command that shouldn't be used jokingly or as a prank as it deletes file which hasn't been tracked in other words, it deletes file which we haven't used `git add <file>` or `git add .` on.
As such the default behavior of `git clean` will throw an error, which is shown below

![](../../../../tmp/Spectacle.XpFUnO/Screenshot_20220212_155608.png)

If we are entirely sure of our action, then we use

`git clean -f`

Let's say we aren't sure of what `git clean`
will do, we run
`git clean -n`
![](../../../../tmp/Spectacle.Vlazyi/Screenshot_20220212_170801.png)
<p style="text-align: center;">Output of git clean</p>

We can see `database.js` is an untracked file therefore if `git clean -f` is run, `database.js` will be deleted.

By default directories aren't deleted when `git clean -f`  is ran but if we want them gone, we use `git clean -fd`

What if we want files in `.gitignore` gone as well? 
We use :
`git clean -xf`



<b><p style="text-align: center;">### Git revert</p></b>

## Git revert

In simple words, it reverts(reverse) the commit specified.
This commit is very helpful in dire situations, like when a bug has been found and it's cause narrowed down to a specific commit, we get the SHA hash of the commit or if it's the topmost commit(HEAD) we just use

`git revert HEAD` or `git revert <SHA Hash>` 

This will add a new commit which reverts the commit we specified so in our case we revert the bugged commit and our bug should be gone.

`git revert` can be considered as a commit undo and it doesn't mess with our commit history.



<b><p style="text-align: center;">### Git reset</p></b>

## Git reset

Useful in some scenario and deadly in others. It's a command that can reset(undo, remove...) the commit indicated. It basically moves the current HEAD to the specified commit.

Basic usage is 

`git reset <commit hash>`


#### Few options

`git reset --soft <commit hash>`

`git reset --hard <commit hash>`

**--soft:**  This option only resets the commit history.

**--hard:** The most used option and the most dangerous. It resets the commit history, staging area and working directory.



<b><p style="text-align: center;">### Git rm</p></b>

## Git rm

Like the Unix `rm` or `del` on Windows, this command removes files from a git repository.



When `git rm` is used, it removes the specified file then performs a `git add` to add the removal operation to the staging index.

Basic usage: 

`git rm <file>`

\<file> can be an individual file, a group of files or directory.

Lucky, the effect can be reversed using either `git reset HEAD` or `git restore`.


That's all on Undoing changes.