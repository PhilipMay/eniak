# GIT

# Initialer Checkout
``` bash
git clone <URI>
```

## Branch erstellen und wechseln
``` bash
git checkout -b <new_branch_name>
```

## Alle Branches anzeigen
``` bash
git branch -a
```

## Zu Remote Branch wechseln
``` bash
git branch <lokaler_name> origin/<remote_name>
git checkout <lokaler_name>
```

## Show History of last Ref Updates
``` bash
git reflog
```

## Undo things

### Unstage all files you have staged with git add
``` bash
git reset
```

### Revert all local uncommitted changes
This should be executed in repo root:

``` bash
git checkout .
```

Yet another way to revert all uncommitted changes (longer to type, but
works from any subdirectory):

``` bash
git reset --hard HEAD
```

## Change last Commit
You can change your last commit message by this command:

``` bash
git commit --amend
```

## Updates eines Forks mergen
Zunächst muss das Original Repository hinzugefügt werden:

``` bash
# Zunächst muss das Original Repository hinzugefügt werden:
git remote add upstream <original_repository>

# Dann fetchen:
git fetch upstream

# In den lokalen branch wechseln der akualisiert werden soll (z. B. master):
git checkout master

# und dann mergen:
git merge upstream/master
```

## Squash: Clean dirty commit history
To clean a dirty commit history (before doing a pull request) you can do
a squash.

```  warning:: Do not rebase commits that exist outside of your repository. At least do
   not rebase branches where others are working on.
```

Lets say you want to fix up the last 5 commits you do this:
``` bash
git rebase -i HEAD~5
```

Then you get an editor window where you have to do the changes. Here you
can rename the top commit by writing \"r\" (for reword) and change the
commit text. If you want to discard all other commits you write \"f\"
(for fixup) infront of them. Now you save the file and the GIT magic is
happening.

Here is an overview of all options:
```
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
```

If something bad happens after saving where you have to fix up something
first, you can continue the rebase with:
``` bash
git rebase --continue
```

When everyhing is ok you have to do a forced push:
``` bash
git push -f
```

If you have already done a pull request (on GitHub) this squash still
works afterwards. The \"dirty\" commit history of the PR will also be
changed.

## Configuration

### Global ignore Settings
Create global ignore settings that are used everywhere:
- create `~/.gitignore_global` file with ignore settings
- execute `git config --global core.excludesfile ~/.gitignore_global`
- also see: <https://jayeshkawli.ghost.io/using-global-gitignore-on-mac/>

## Links
- Pro Git book: <https://git-scm.com/book/en/>
- Ry\'s Git Tutorial: <https://www.smashwords.com/books/view/498426>
