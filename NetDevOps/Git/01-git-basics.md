---
tags: [git, version-control, netdevops]
validation: reference
---

# Git — Basic operations

[🇬🇧 English](01-git-basics.md) · [🇨🇴 Español](01-git-basics.es.md) · [↩ NetDevOps](../README.md)

## `git status --short`

```bash
git status --short
```

- **Purpose:** Lists modified, untracked and staged files compactly.
- **Arguments:** --short: two-column concise status.
- **Use case:** Check what changed before staging.

## `git diff --check`

```bash
git diff --check
```

- **Purpose:** Checks unstaged changes for whitespace errors.
- **Arguments:** --check: report whitespace errors.
- **Use case:** Validate documentation edits before a commit.

## `git diff -- README.md`

```bash
git diff -- README.md
```

- **Purpose:** Shows unstaged edits to the chosen file.
- **Arguments:** --: separate file path from options.
- **Use case:** Inspect the main README before publishing.

## `git log --oneline -5`

```bash
git log --oneline -5
```

- **Purpose:** Shows recent commit hashes and messages.
- **Arguments:** --oneline: compact format; -5: five entries.
- **Use case:** Locate a known-good change.

## `git branch --show-current`

```bash
git branch --show-current
```

- **Purpose:** Displays the checked-out branch name.
- **Arguments:** --show-current: only branch name.
- **Use case:** Avoid committing directly to the wrong branch.

## `git switch -c docs/aruba-cx`

```bash
git switch -c docs/aruba-cx
```

- **Purpose:** Creates and switches to a new branch.
- **Arguments:** -c: create new branch.
- **Use case:** Keep documentation edits isolated from main.

## `git add Networking/Aruba/`

```bash
git add Networking/Aruba/
```

- **Purpose:** Stages changes under the named directory.
- **Arguments:** Path: limit the staging scope.
- **Use case:** Include only Aruba documentation in the commit.

## `git commit -m "docs: add Aruba CX reference"`

```bash
git commit -m "docs: add Aruba CX reference"
```

- **Purpose:** Creates a commit from staged changes.
- **Arguments:** -m: commit message.
- **Use case:** Record a reviewed knowledge-base update.

## `git push -u origin docs/aruba-cx`

```bash
git push -u origin docs/aruba-cx
```

- **Purpose:** Pushes a branch and sets upstream tracking.
- **Arguments:** -u: remember upstream; origin: remote.
- **Use case:** Open a pull request from the branch.

## `git fetch --prune origin`

```bash
git fetch --prune origin
```

- **Purpose:** Downloads remote refs and prunes stale tracking refs.
- **Arguments:** --prune: delete stale remote-tracking refs.
- **Use case:** Check remote changes without merging them.


## `git add README.md`

```bash
git add README.md
```

- **Purpose:** Stage changes in a single file.
- **Arguments:** README.md: specific path; use `git add .` only when all changes are intended.
- **Use case:** Stage only the documentation you reviewed.

## `git checkout -b docs/docker`

```bash
git checkout -b docs/docker
```

- **Purpose:** Create a branch and switch to it.
- **Arguments:** -b: create and check out the new branch.
- **Use case:** Edit Docker commands separately from main.

## `git checkout main`

```bash
git checkout main
```

- **Purpose:** Switch to an existing local branch.
- **Arguments:** main: target branch; local changes must not conflict.
- **Use case:** Return to main before merging reviewed work.

## `git checkout -d HEAD~1`

```bash
git checkout -d HEAD~1
```

- **Purpose:** Inspect the previous commit in detached HEAD mode; it does not delete a branch.
- **Arguments:** -d / --detach: detach HEAD; HEAD~1: previous commit.
- **Use case:** Temporarily investigate a prior revision, then run `git switch main`.
- **Caution:** Do not start long-lived work without creating a branch.

## `git branch`

```bash
git branch
```

- **Purpose:** List local branches, marking the current branch.
- **Arguments:** Without arguments: list local branches.
- **Use case:** Verify that docs/docker exists.

## `git branch -d docs/docker`

```bash
git branch -d docs/docker
```

- **Purpose:** Delete a local branch that is fully merged.
- **Arguments:** -d: safe delete; docs/docker: branch to remove.
- **Use case:** Clean up a completed documentation branch.
- **Caution:** Switch to another branch first and confirm the merge.

## `git merge --no-ff docs/docker`

```bash
git merge --no-ff docs/docker
```

- **Purpose:** Merge the reviewed branch into the current branch.
- **Arguments:** --no-ff: create a merge commit; docs/docker: source branch.
- **Use case:** From main, merge the approved Docker changes.
- **Caution:** Resolve conflicts and run tests before pushing.

## `git push`

```bash
git push
```

- **Purpose:** Push the current branch to its configured upstream.
- **Arguments:** No flags: requires an upstream or matching push configuration.
- **Use case:** Publish later commits after `git push -u origin docs/docker`.

## `gh auth login --web`

```bash
gh auth login --web
```

- **Purpose:** Sign in to GitHub through the GitHub CLI browser flow; Git has no native `git login` command.
- **Arguments:** gh: separately installed GitHub CLI; --web: browser authentication.
- **Use case:** Authenticate on a new workstation before your first GitHub push.
- **Caution:** Choose HTTPS Git integration when prompted; never paste secrets into repository files.

## `gh auth status`

```bash
gh auth status
```

- **Purpose:** Check which GitHub account is authenticated.
- **Arguments:** status: display the current GitHub CLI authentication state.
- **Use case:** Confirm login worked before pushing.

## `gh auth setup-git`

```bash
gh auth setup-git
```

- **Purpose:** Configure Git to use GitHub CLI's credential helper.
- **Arguments:** setup-git: register gh as a Git authentication helper.
- **Use case:** Fix HTTPS Git prompts after `gh auth login` if integration is not set.
- **Caution:** Run only on a trusted workstation; requires GitHub CLI installed.

> **Git login:** there is no `git login` command; use `gh auth login --web` (GitHub CLI), SSH or a credential manager. `git checkout -d` detaches HEAD; `git branch -d` deletes a merged local branch.

> Git uses native flags; pipes are optional, not mandatory. Avoid destructive operations before reviewing status.

[Git reference](https://git-scm.com/docs)
