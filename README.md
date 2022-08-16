# A bit of git
A git cheatsheet

## git basics

### From an existing repository

1. Clone repo: `git clone <repo>`
The repo will be cloned to whatever folder you use this command from.

2. Checkout existing branch: `git checkout <branch name>`
2. Create new branch and checkout created branch:

3. Check current status: `git status`

4. To add a file: `git add <file>`
This makes git aware of the existence of this file. It does not commit the file or it's changes!

Note: You cannot pull/merge/checkout other branch when you have uncommitted changes.
You'll have to stash them.

4. To add all files: `git add .`

5. To merge main into your branch `git merge main`
This will copy and apply changes from main to your branch

6. Commit changes: `git commit -m "<commit message>"`
This commits ("saves") your changes locally, with the given commit message.

7. Add additional changes to an existing commit (i.e. expanding original commit with new changes): `git commit --amend`

8. Push your local commit(s) to the remote repo: `git push`
Now your changes are also in the remote.

### In a new repository
1. Use `git init` to add the current project to Git.

2. Check current status: `git status`

3. Add files you want to add to version control, by using either `git add .` to add all files or `git add <file>` to add individual files.

4. Commit changes: `git commit -m "<commit message>"`
This commits ("saves") your changes locally, with the given commit message.

5. Create a project on GitHub and copy the location from Quick Setup

6. Add that location as a remote: `git remote add origin <remote>`

7. Push your local commit(s) to the remote repo: `git push`



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

Replace `pick` (keep) with `squash` or `fixup` if you want to squash a commit into the previous commit in the list.

(Use `squash` to combine the commit messages of the individual commits; use `fixup` if you want to use the commit message from the first commit)

Adter saving the list, update the commit messages as needed.

Alternatively, tools like GitHub and GitLab offer the option to "squash on merge" when merging a feature branch. This will squash all commits in a branch into one commit on main.

### Vi cheat sheet:

To insert (i.e. write/delete), press `I`

To get out of edit mode, press `esc`

To save and quit, type `:wq`

To quit without save `:q!`

(Note: you can replace vi with another editor! See [Customizing Git](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration))

## Empty commit
`git commit --allow-empty -m "Commit to trigger build"`

## Reflog
[Recover lost git commits](http://effectif.com/git/recovering-lost-git-commits)

## Bisect
[Find which commit broke the test](https://git-scm.com/docs/git-bisect)
