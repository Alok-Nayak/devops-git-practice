# git commands

## Setup & Config

` git init `    :Iniitialize git.
` git config --global user.name Alok-Nayak ` :Set global Username.
` git config --global user.email "aloknayak.contact@gmail.com" ` : Set global email addr.

- **To unset global config. user and email.**
```bash
git config --global --unset user.name  
git config --global --unset user.email
```

---

## 1. Basic Workflow

- `git status` — Check the status of working directory and staging area.
- `git add <file>` — Add a specific file to the staging area.
- `git add .` — Add all new, modified, and deleted files to the staging area.
- `git commit -m "message"` — Record staged changes to the repository history.
- `git push origin <branch-name>` — Upload local branch commits to remote repository (e.g., GitHub).
- `git pull` — Fetch and merge changes from remote repository to local branch.

---

## 2. Viewing Changes & History

- `git log` — Show complete commit history.
- `git log --oneline` — Display compact, single-line commit history.
- `git log --oneline --graph --all` — Display visual ASCII graph of all branches and commits.
- `git diff` — Show unstaged changes (working directory vs. staging area).
- `git diff --staged` — Show staged changes (staging area vs. last commit).
- `git diff <branch> -- <filepath>` — Compare local file with its version on another branch.
- `git show <commit-id>` — Display detailed changes made in a specific commit.
- `git show <branch>:<filepath>` — View content of a file on another branch without switching.

---

## 3. Branching & Switching

### Legacy Commands
- `git branch` — List all local branches (`*` indicates active branch).
- `git branch -r` — List all remote-tracking branches.
- `git branch -a` — List all local and remote branches.
- `git branch <branch-name>` — Create a new branch.
- `git checkout <branch-name>` — Switch to an existing branch.
- `git checkout -b <branch-name>` — Create and switch to a new branch in one command.

---

### Recommended Modern Commands
- `git switch <branch-name>` — Switch to an existing branch.
- `git switch -c <branch-name>` — Create and switch to a new branch.
- `git branch -M main` — Rename current branch to `main`.

---

### Branch Deletion
- `git branch -d <branch-name>` — Delete a local branch safely (prevents deletion if unmerged).
- `git branch -D <branch-name>` — Force delete a local branch regardless of merge status.
- `git push origin --delete <branch-name>` — Delete a branch from remote repository.

---

## 4. Merging & Rebasing

- `git merge <branch-name>` — Perform regular 3-way merge (preserves full commit history).
- `git merge --squash <branch-name>` — Combine all branch commits into staged changes on target branch (requires `git commit` after).
- `git rebase <branch-name>` — Replay current branch commits on top of another branch (linear history).
- `git pull --rebase` — Fetch remote changes and rebase local commits on top instead of merging.
- `git cherry-pick <commit-id>` — Apply a single, specific commit from another branch onto current branch.
- `git rebase --continue` — Resume rebase process after resolving merge conflicts.
- `git rebase --abort` — Cancel rebase and restore branch to original state.

---

## 5. Stash (Temporary Uncommitted Work)

- `git stash` — Save modified, tracked changes to stash stack and clear working directory.
- `git stash push -m "message"` — Save stash with a custom descriptive note.
- `git stash -u` — Stash tracked AND untracked files.
- `git stash list` — List all stored stashes (`stash@{0}`, `stash@{1}`, etc.).
- `git stash pop` — Apply most recent stash and delete it from stash list.
- `git stash apply stash@{N}` — Apply a specific stash index while keeping it in stash list.
- `git stash drop stash@{N}` — Remove a specific stash entry from stash list.
- `git stash clear` — Danger: Delete all stashes permanently.

---

## 6. Inspection, Cleanup & Recovery

- `git reflog` — Show history of all HEAD reference movements (useful for recovering lost commits or branches).
- `git clean -fd` — Force removal of all untracked files (`-f`) and directories (`-d`).
- `git blame <file>` — Display line-by-line file history showing author and commit details.
- `git restore <file>` — Discard local uncommitted changes in working directory.
- `git restore --staged <file>` — Unstage a file while preserving changes in working directory.

---
