# Practical 08: Advanced Git

## Objective
Explore `.gitignore`, `cherry-pick`, `rebase`, and `reflog` in a safe practice repository.

## `.gitignore`
Create a `.gitignore` file and add patterns for files that should not be tracked. Note that `.gitignore` does not stop tracking a file that is already committed.

## Cherry-pick
Create a commit on a practice branch, copy its hash, then apply it to another branch:

```bash
git log --oneline
git switch main
git cherry-pick COMMIT_HASH
```

Use a commit from your own test branch and replace `COMMIT_HASH`.

## Rebase
In a disposable repository, create a feature branch and a commit. Then rebase it onto the latest main branch:

```bash
git switch feature/my-work
git fetch origin
git rebase main
```

Resolve any conflicts as Git instructs. Do not rebase shared commits without understanding the consequences: rebase rewrites commit history.

## Reflog
Inspect recent movements of HEAD:

```bash
git reflog
```

Use this to learn how Git records recent local reference changes. Recovery can be possible, but do not rely on reflog as a substitute for backups.

## Verify
- [ ] Explain why `.gitignore` does not untrack committed files
- [ ] Cherry-pick a practice commit
- [ ] Rebase a local practice branch
- [ ] Inspect `git reflog`

