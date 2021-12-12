# GitHub (GH) CLI
## GH CLI installation
```bash
brew install gh
```

## GH CLI authentication
You authentication via browser
```bash
gh auth login
```
or using prepared access token
```bash
gh auth login --with-token < path_to_token.txt
```

## GH CLI pull request
### GH CLI create pull requests
The next command will create a PR using a default branch as base branch, and
also will fill title and comment of the PR depends on commit messages
```bash
gh pr create -f -a "@me"
```
Command options:
* `-a`/`--assignee` – assignee by their usernames
* `-b`/`--body`     - body for the pull request
* `-r`/`--reviewer` - request reviews from people or teams by their user(group) names

### GH CLI open pull request in browser
```bash
gh pr view --web
```

## Links
* [GitHub CLI](https://github.com/cli/cli)
