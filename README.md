# git-cheatsheet
A git cheatsheet

## git basics

1. Clone repo: `git clone <repo>`
The repo will be cloned to whatever folder you use this command from.

2. Checkout existing branch: `git checkout <branch name>`
2. Create new branch and checkout created branch:

3. Check current status: `git status`

4. To add a file: `git add <file>`
This makes git aware of the existence of this file. It does not commit the file or it's changes!

Note: You cannot pull/merge/checkout other branch when you have uncommitted changes.
You'll have to stash them.

5. To merge master into your branch `git merge master`
This will copy and apply changes from master to your branch

6. Commit changes: `git commit -m "<commit message>"`
This commits ("saves") your changes locally, with the given commit message.

7. Add additional changes to an existing commit (i.e. expanding original commit with new changes): `git commit --amend`

8. Push your local commit(s) to the remote repo: `git push`
Now your changes are also in the remote.

## git reset

To undo or discard commits, you can use
* `git reset --hard <commit>` to reset your HEAD to that commit and **discarding** any commits you made on top of that commit.

* `git reset --soft <commit>` to reset your HEAD to that commit without discarding the changes you made on top of that commit, but "uncommitting" them.

## git commit amend
`git commit -a --amend` to amend to previous commit (only if you haven't pushed yet). (Note: if you use `-a` it will include all staged changes, so you might want to `git status` first).

## git push force
`git push --force` will overwrite the status of the branch on the remote with your local status.

**Note:** The original status on the remote will be **destroyed**. If anyone on the team has that branch locally, they'll need to delete it locally and checkout the branch again to get it in the same status as the remote.

## interactive rebase
`git rebase -i <commit hash>` to do an interactive rebase from the given commit hash.

This will open a list of commits with their hashes.

Replace `pick` (keep) with `squash` if you want to squash a commit into the previous commit in the list.

Adter saving the list, update the commit messages as needed.

Alternatively, tools like GitHub and GitLab offer the option to "squash on merge" when merging a feature branch. This will squash all commits in a branch into one commit on master.

### Vi cheat sheet:

To insert (i.e. write/delete), press i

To get out of this mode, press `esc`

To save and quit, type `:wq`

To quit without save (I think) `:q!`

(Note: you can replace vim with another editor!)


## Empty commit
`git commit --allow-empty -m "Commit to trigger build"`

## Reflog
[Recover lost git commits](http://effectif.com/git/recovering-lost-git-commits)
