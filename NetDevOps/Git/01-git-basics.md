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

> Git uses native flags; pipes are optional, not mandatory. Avoid destructive operations before reviewing status.

[Git reference](https://git-scm.com/docs)
