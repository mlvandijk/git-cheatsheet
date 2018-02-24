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


### Vi cheat sheet:
To insert (i.e. write/delete), press i
To get out of this mode, press `esc`
To save and quit, type `:wq`
To quit without save (I think) `:q!`
(Note: you can replace vim with another editor!)


## Empty commit
`git commit --allow-empty -m "Commit to trigger build"`