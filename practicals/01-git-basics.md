# Practical 01: Git Basics

## Objective
Create a local Git repository, track changes, make commits, and inspect history.

## Commands

```bash
mkdir git-basics-demo
cd git-basics-demo
git init
git status
```

Create a file named `notes.txt` and add a short line to it.

```bash
git status
git add notes.txt
git status
git commit -m "docs: add initial notes"
git log --oneline
```

Edit `notes.txt`, then inspect the changes:

```bash
git diff
git add notes.txt
git commit -m "docs: update notes"
git log --oneline
```

## Verify
- [ ] Repository initialized
- [ ] File staged and committed
- [ ] Two commits visible in `git log --oneline`


