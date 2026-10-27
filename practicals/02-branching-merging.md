# Practical 02: Branching and Merging

## Objective
Create a feature branch, make a change, and merge it into the main branch.

## Commands

```bash
git switch -c feature/update-notes
git branch
```

Create or edit a file, then commit it:

```bash
git add .
git commit -m "feat: add feature notes"
git switch main
git merge feature/update-notes
git log --oneline --graph --all
```

If your default branch is named `master`, use `master` instead of `main`.

## Verify
- [ ] Feature branch created
- [ ] Feature commit created
- [ ] Feature branch merged
- [ ] Graph shows branch history

