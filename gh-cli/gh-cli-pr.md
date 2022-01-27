# GitHub (GH) CLI pull request
## GH CLI create a pull request
The next command will create a PR using a default branch as base branch, and
also will fill title and comment of the PR depends on commit messages
```bash
gh pr create -f -a "@me"
```
Command options:
* `-a`/`--assignee` – assignee by their usernames
* `-b`/`--body`     - body for the pull request
* `-r`/`--reviewer` - request reviews from people or teams by their user(group) names
* `-d`/`--draft`    – mark pull request as a draft

## GH CLI open pull request in browser
```bash
gh pr view --web
```
## Links
* [GH CLI | Create Pull Request](https://cli.github.com/manual/gh_pr_create)
* [GH CLI | View Pull Request](https://cli.github.com/manual/gh_pr_view)
