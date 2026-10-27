<div align="center">

# Git & GitHub Knowledge Base

### Concepts · Commands · Workflows · Practical Examples

A structured learning reference for Git and GitHub, built during my DevOps learning journey.

![Git](https://img.shields.io/badge/Git-Version_Control-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Collaboration-181717?style=for-the-badge&logo=github&logoColor=white)
![Learning](https://img.shields.io/badge/Learning-Hand--On-2EA44F?style=for-the-badge)

</div>

---

## 📌 About This Guide

This document brings together essential Git and GitHub concepts, clear explanations, command examples, and common development workflows. It is intended for learning, revision, and hands-on practice.

> **Practice tip:** Try commands in a test repository first. Add your own notes and screenshots as you learn. Never commit passwords, access tokens, private keys, or other secrets.

## 🧭 Contents

- [1. Git Fundamentals](#1--git-fundamentals)
- [2. Repository and File States](#2--repository-and-file-states)
- [3. Commits and History](#3--commits-and-history)
- [4. Branching and Merging](#4--branching-and-merging)
- [5. Remote Repositories](#5--remote-repositories)
- [6. Undoing and Recovering Changes](#6--undoing-and-recovering-changes)
- [7. Stash, Tags, and Ignore Rules](#7--stash-tags-and-ignore-rules)
- [8. Advanced Git Workflows](#8--advanced-git-workflows)
- [9. GitHub Collaboration](#9--github-collaboration)
- [10. Troubleshooting Scenarios](#10--troubleshooting-scenarios)
- [11. Quick Command Reference](#11--quick-command-reference)

---

## 1 · Git Fundamentals

<details>
<summary><strong>1. What is Git?</strong></summary>

Git is a distributed version control system that tracks changes to files over time. It helps developers review history, work on separate branches, and collaborate without relying on a single central copy.

**Example:**
```bash
git init
git status
```
</details>

<details>
<summary><strong>2. What is GitHub?</strong></summary>

GitHub is an online platform for hosting Git repositories. It adds collaboration features such as pull requests, issues, code reviews, project discussions, and automation workflows.
</details>

<details>
<summary><strong>3. What is the difference between Git and GitHub?</strong></summary>

| Git | GitHub |
|---|---|
| Version control software | Online hosting and collaboration platform |
| Can work locally without internet | Usually accessed online |
| Tracks changes and branches | Hosts repositories and supports reviews, issues, and collaboration |

**In short:** Git manages version history; GitHub helps people share and collaborate on Git repositories.
</details>

<details>
<summary><strong>4. What is version control?</strong></summary>

Version control records changes to files so you can inspect history, compare versions, restore earlier work, and coordinate changes with other contributors.
</details>

<details>
<summary><strong>5. What is a repository?</strong></summary>

A repository (repo) is a project directory whose files and history are tracked by Git. The hidden `.git` directory stores repository metadata and history.
</details>

<details>
<summary><strong>6. What is the difference between a local and remote repository?</strong></summary>

A local repository is on your computer. A remote repository is another repository, commonly hosted on GitHub, that you can fetch from and push to.
</details>

## 2 · Repository and File States

<details>
<summary><strong>7. What does git init do?</strong></summary>

`git init` creates a new Git repository in the current directory.

```bash
mkdir demo-project
cd demo-project
git init
```
</details>

<details>
<summary><strong>8. What does git status show?</strong></summary>

`git status` shows the current branch and the state of tracked, modified, staged, and untracked files.

```bash
git status
```
</details>

<details>
<summary><strong>9. What is the staging area?</strong></summary>

The staging area (index) is where you select the changes to include in the next commit. It lets you commit some changes without committing every modified file.

```bash
git add README.md
git status
```
</details>

<details>
<summary><strong>10. What is the difference between a tracked and untracked file?</strong></summary>

A tracked file is already known to Git. An untracked file exists in the working directory but has not yet been added to Git's index or committed.
</details>

<details>
<summary><strong>11. What does git add do?</strong></summary>

`git add` stages file content for the next commit.

```bash
git add README.md
git add .
```

Review `git status` before committing, especially when using `git add .`.
</details>

<details>
<summary><strong>12. What is .gitignore?</strong></summary>

`.gitignore` tells Git which untracked files or paths to ignore, such as build output, logs, or local environment files.

Example:
```gitignore
.env
*.log
node_modules/
```

It does not automatically stop tracking files that were already committed. Remove those from the index with care if needed.
</details>

## 3 · Commits and History

<details>
<summary><strong>13. What is a commit?</strong></summary>

A commit is a recorded snapshot of the staged project content, with metadata such as author, timestamp, parent commit, and message.

```bash
git add .
git commit -m "docs: add project overview"
```
</details>

<details>
<summary><strong>14. What makes a good commit message?</strong></summary>

A good commit message is short, specific, and describes the change. For example:

- `docs: add Git basics notes`
- `feat: add login validation`
- `fix: handle empty input`

Use a consistent convention across the repository.
</details>

<details>
<summary><strong>15. How do you view commit history?</strong></summary>

```bash
git log
git log --oneline
git log --oneline --graph --all
```

The graph view is useful for understanding branch and merge history.
</details>

<details>
<summary><strong>16. What is HEAD in Git?</strong></summary>

`HEAD` usually points to the currently checked-out commit or to the current branch reference. When you switch branches, `HEAD` normally moves to the tip of that branch.
</details>

<details>
<summary><strong>17. What is the difference between git diff and git log?</strong></summary>

`git diff` compares changes between versions of files. `git log` displays commit history.

```bash
git diff
git diff --staged
git log --oneline
```
</details>

## 4 · Branching and Merging

<details>
<summary><strong>18. What is a branch?</strong></summary>

A branch is a movable reference to a line of development. Branches let you work on a feature or fix without making every change directly on the main development branch.
</details>

<details>
<summary><strong>19. How do you create and switch to a branch?</strong></summary>

```bash
git branch
git switch -c feature/update-readme
git switch main
```

`git switch -c` creates the branch and switches to it.
</details>

<details>
<summary><strong>20. What is merging?</strong></summary>

Merging integrates changes from one branch into the branch you currently have checked out.

```bash
git switch main
git merge feature/update-readme
```
</details>

<details>
<summary><strong>21. What is a fast-forward merge?</strong></summary>

A fast-forward merge happens when the target branch has no new divergent commits. Git can move the branch pointer forward without creating a separate merge commit.
</details>

<details>
<summary><strong>22. What is a merge conflict?</strong></summary>

A merge conflict occurs when Git cannot automatically combine changes, often because different branches changed the same lines.

**Typical resolution:**
1. Run `git status` to identify conflicted files.
2. Open each file and choose the intended final content.
3. Remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
4. Stage the resolved files.
5. Complete the merge with a commit if Git requires one.

```bash
git add conflicted-file.txt
git status
git commit
```
</details>

<details>
<summary><strong>23. How do you delete a branch?</strong></summary>

```bash
git branch -d feature/update-readme
git push origin --delete feature/update-readme
```

The first command deletes a local branch that Git considers safely merged. The second deletes a remote branch. Be sure the branch is no longer needed.
</details>

## 5 · Remote Repositories

<details>
<summary><strong>24. What does git clone do?</strong></summary>

`git clone` creates a local copy of a remote repository, including its history.

```bash
git clone https://github.com/OWNER/REPOSITORY.git
```
</details>

<details>
<summary><strong>25. What does git remote -v show?</strong></summary>

It lists configured remote names and their fetch/push URLs.

```bash
git remote -v
```
</details>

<details>
<summary><strong>26. What is the difference between git fetch and git pull?</strong></summary>

`git fetch` downloads remote updates without integrating them into the current branch. `git pull` fetches and then integrates the updates, commonly through merge or rebase depending on configuration and options.
</details>

<details>
<summary><strong>27. What does git push do?</strong></summary>

`git push` sends local commits to a remote repository, provided the remote and branch allow the update.

```bash
git push -u origin main
git push
```

The `-u` option sets the upstream branch for convenient future pushes.
</details>

<details>
<summary><strong>28. How do you connect a local repository to GitHub?</strong></summary>

Create an empty repository on GitHub, then add its URL as a remote. Replace the example URL with your own.

```bash
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git branch -M main
git push -u origin main
```

If the remote already contains commits, such as an initial README, you may need to fetch and integrate that history first.
</details>

<details>
<summary><strong>29. What is origin?</strong></summary>

`origin` is the conventional default name given to the remote repository when cloning. It is just a name and can be changed or replaced.
</details>

## 6 · Undoing and Recovering Changes

<details>
<summary><strong>30. What does git restore do?</strong></summary>

`git restore` restores file content in the working tree or, with `--staged`, removes changes from the staging area.

```bash
git restore README.md
git restore --staged README.md
```

Be careful: restoring a file can discard uncommitted edits.
</details>

<details>
<summary><strong>31. What is the difference between git reset and git revert?</strong></summary>

| `git reset` | `git revert` |
|---|---|
| Moves the current branch reference | Creates a new commit that reverses an earlier commit |
| Can change the index and working tree depending on options | Preserves existing history and adds a reversing commit |
| Can be risky on shared history | Often suitable for undoing published changes |

Use a test repository to learn reset options before using them on important work.
</details>

<details>
<summary><strong>32. What do --soft, --mixed, and --hard mean in git reset?</strong></summary>

- `--soft`: moves `HEAD`; staged and working-tree changes remain.
- `--mixed` (default): moves `HEAD` and resets the index; working-tree changes remain.
- `--hard`: moves `HEAD` and resets the index and working tree, potentially discarding work.

**Warning:** Do not use `git reset --hard` unless you are certain you can lose the affected uncommitted changes.
</details>

<details>
<summary><strong>33. How do you undo a commit that has already been shared?</strong></summary>

For many shared branches, `git revert COMMIT_HASH` is the safer option because it adds a new commit that reverses the change instead of rewriting published history. Coordinate with your team before changing shared branches.
</details>

<details>
<summary><strong>34. What is git reflog?</strong></summary>

`git reflog` records recent local movements of references such as `HEAD`. It can help locate commits after some branch or reset mistakes.

```bash
git reflog
```

Reflog entries are local and expire; they are not a substitute for backups.
</details>

## 7 · Stash, Tags, and Ignore Rules

<details>
<summary><strong>35. What is git stash?</strong></summary>

`git stash` temporarily stores eligible uncommitted changes so you can switch tasks and return to them later.

```bash
git stash push -m "WIP: documentation"
git stash list
git stash pop
```
</details>

<details>
<summary><strong>36. What is the difference between git stash pop and git stash apply?</strong></summary>

Both attempt to reapply stashed changes. `git stash pop` also removes the stash entry if it applies successfully; `git stash apply` keeps the stash entry.
</details>

<details>
<summary><strong>37. What is a Git tag?</strong></summary>

A tag names a specific point in history, often used to mark a release.

```bash
git tag -a v1.0.0 -m "First release"
git show v1.0.0
git push origin v1.0.0
```
</details>

<details>
<summary><strong>38. What is the difference between lightweight and annotated tags?</strong></summary>

A lightweight tag is a simple reference to a commit. An annotated tag stores additional metadata such as tagger, date, and message. Annotated tags are often preferred for releases.
</details>

## 8 · Advanced Git Workflows

<details>
<summary><strong>39. What is git rebase?</strong></summary>

`git rebase` reapplies commits onto a new base commit, creating new commit IDs. It can create a more linear history, but it rewrites history.

```bash
git switch feature/my-work
git rebase main
```

Avoid rebasing commits that others rely on unless the team has agreed on the workflow.
</details>

<details>
<summary><strong>40. What is the difference between merge and rebase?</strong></summary>

Merge integrates branch histories and may create a merge commit. Rebase replays commits on a new base and produces new commit IDs. Merge preserves the branch topology; rebase can produce a more linear history.
</details>

<details>
<summary><strong>41. What is git cherry-pick?</strong></summary>

`git cherry-pick` applies the change introduced by a chosen commit onto the current branch, creating a new commit.

```bash
git cherry-pick COMMIT_HASH
```

Use the actual hash from your own practice repository.
</details>

<details>
<summary><strong>42. What is a detached HEAD?</strong></summary>

A detached HEAD state means `HEAD` points directly to a commit rather than a local branch. You can inspect or experiment with commits in this state. If you create work you want to keep, create a branch before switching away.
</details>

<details>
<summary><strong>43. What is a bare repository?</strong></summary>

A bare repository stores Git data without a checked-out working tree. It is commonly used as a shared remote repository.
</details>

## 9 · GitHub Collaboration

<details>
<summary><strong>44. What is a Pull Request?</strong></summary>

A pull request proposes a set of changes for review and discussion before they are merged into a target branch. It lets collaborators inspect the diff, comment, and run checks.
</details>

<details>
<summary><strong>45. What is the difference between an Issue and a Pull Request?</strong></summary>

An Issue tracks a task, bug, question, or idea. A Pull Request proposes code or documentation changes and supports review before integration.
</details>

<details>
<summary><strong>46. What is a code review?</strong></summary>

A code review is a structured examination of proposed changes for correctness, readability, security, maintainability, and alignment with project requirements.
</details>

<details>
<summary><strong>47. What is a fork?</strong></summary>

A fork is a separate copy of a repository under another account or organization. It is commonly used when contributing to a project where you do not have direct write access.
</details>

<details>
<summary><strong>48. What is the fork-and-pull workflow?</strong></summary>

1. Fork the project.
2. Clone your fork.
3. Create a feature branch.
4. Make and commit changes.
5. Push the branch to your fork.
6. Open a pull request against the original repository.
</details>

<details>
<summary><strong>49. How can you protect sensitive information in a repository?</strong></summary>

Never commit credentials, tokens, private keys, or real secret environment files. Use appropriate secret storage, add local secret files to `.gitignore`, and rotate any credential that was exposed. Removing a secret in a later commit does not remove it from earlier history.
</details>

## 10 · Troubleshooting Scenarios

<details>
<summary><strong>50. You get “nothing to commit, working tree clean.” What does it mean?</strong></summary>

Git sees no staged or unstaged changes to commit. Check that you edited and saved the intended file, and run:

```bash
git status
git diff
```
</details>

<details>
<summary><strong>51. You get “fatal: not a git repository.” What should you check?</strong></summary>

You may be outside the repository directory. Move into the project folder and check:

```bash
pwd
ls -la
git status
```

On Windows Command Prompt, use `dir` to list files.
</details>

<details>
<summary><strong>52. You get a rejected push because the remote contains work you do not have. What should you do?</strong></summary>

Fetch and inspect the remote changes, then integrate them before pushing.

```bash
git fetch origin
git log --oneline --graph --all
git pull --rebase origin main
git push
```

Use the correct branch name and resolve any conflicts. Avoid force-pushing as a quick fix, especially to shared branches.
</details>

<details>
<summary><strong>53. You committed to the wrong branch. What can you do?</strong></summary>

Pause and inspect the state before changing history. If the commit is local and has not been shared, you may be able to create the intended branch at that commit and then reset the original branch appropriately. If it has been pushed, coordinate with collaborators before rewriting history. Practise this scenario in a disposable repository.
</details>

<details>
<summary><strong>54. A file is in .gitignore but still appears in Git. Why?</strong></summary>

`.gitignore` only affects untracked files. If the file was already tracked, remove it from the index while keeping the local file:

```bash
git rm --cached path/to/file
git commit -m "chore: stop tracking local file"
```

Check carefully before committing, especially if the file contains secrets.
</details>

<details>
<summary><strong>55. How do you resolve a push or pull conflict safely?</strong></summary>

Read the full error message, run `git status`, inspect the affected files, and understand whether Git is performing a merge or rebase. Resolve the conflicts, stage the resolved files, and continue the operation using the command Git indicates. Do not delete files or abort the operation unless you understand the consequences.
</details>

## 11 · Quick Command Reference

| Task | Command |
|---|---|
| Initialize repository | `git init` |
| Check working tree | `git status` |
| Stage a file | `git add FILE` |
| Commit staged changes | `git commit -m "message"` |
| Show short history | `git log --oneline` |
| Create and switch branch | `git switch -c BRANCH` |
| Switch branch | `git switch BRANCH` |
| Merge a branch | `git merge BRANCH` |
| Show remotes | `git remote -v` |
| Download remote updates | `git fetch` |
| Fetch and integrate updates | `git pull` |
| Push commits | `git push` |
| Unstage a file | `git restore --staged FILE` |
| Revert a commit | `git revert HASH` |
| List stashes | `git stash list` |
| Show reference history | `git reflog` |
| Show changes | `git diff` |

---

## ✅ Learning Checklist

- [ ] Explain Git and GitHub in my own words
- [ ] Create a repository and make commits
- [ ] Create branches and merge changes
- [ ] Connect a local repository to GitHub
- [ ] Resolve a merge conflict
- [ ] Use stash and tags
- [ ] Practise restore, reset, and revert safely
- [ ] Understand merge, rebase, and cherry-pick
- [ ] Create an Issue and Pull Request
- [ ] Add screenshots from my own practice sessions


<div align="center">

**Learn it · Practise it · Document it**

</div>
