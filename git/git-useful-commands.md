# Git useful commands

## Git create branch
```bash
git checkout -b "<new_branch_name>" "<from_branch>"
git checkout -b feature_x main
git checkout -b feature_x
```
* `new_branch_name` – is a name of your branch
* `from_branch` – is a name of branch from which need to create new branch,
could be empty, in that case will be used the current branch

## Git delete branch

### Git delete local branch

```bash
git branch -D "<branch_name>"
git branch -D feature_x
```

### Git delete remote branch

```bash
git push "<remote_name>" --delete "<branch_name>"
git push origin --delete feature_x
```

## Git pipeline to rebase

If you're on the branch `feature_x` and you need to pull changes from the `main`
branch, then the next commands will be useful

```bash
git fetch origin X # pull the latests changes from remote
git checkout feature_x
git rebase origin/main
git push --force
```
