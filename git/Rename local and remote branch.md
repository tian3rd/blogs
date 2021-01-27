## How to rename both local and remote branches?

1. Find out local and remote branches
   1. local: `git branch -vv --all`
   2. remote: `git remote -v`
2. Rename local branch
   1. `git branch -m <old-name> <new-name>`
3. Rename the remote if necessary
   1. `git remote rename <old-remote> <new-remote>`
4. Delete old branch on remote (make sure it's not the default branch, i.e. main or master)
   1. `git push <new-remote> --delete <old-name>`
5. Unlink the upstream for the old branch
   1. `git branch --unset-upstream <old-name>`
6. Link the new branch with the new remote and push
   1. `git push -u <new-remote> <new-name>`

#### Reference

[Stackoverflow](https://stackoverflow.com/questions/30590083/how-do-i-rename-both-a-git-local-and-remote-branch-name)
