# Practical 04: Undo and Recovery

## Objective
Understand safe ways to discard working-tree changes, unstage files, and undo commits.

> Practice only in a disposable test repository. Some commands can permanently discard work.

## Try `git restore`
Edit a tracked file without staging it, then inspect:

```bash
git status
git diff
```

To discard those uncommitted edits (only if you are sure):

```bash
git restore filename.txt
```

## Try `git restore --staged`
Stage a file, then unstage it while keeping the edits:

```bash
git add filename.txt
git restore --staged filename.txt
git status
```

## Try `git revert`
Create a commit in a practice branch, then revert that commit using its hash:

```bash
git log --oneline
git revert COMMIT_HASH
```

Replace `COMMIT_HASH` with the actual commit hash. Revert creates a new commit that undoes another commit.

## Optional: `git reset`
Learn the differences between `--soft`, `--mixed` (the default), and `--hard` in a disposable repo first. `git reset --hard` can discard uncommitted work.

## Verify
- [ ] Explain the difference between restore, revert, and reset
- [ ] Demonstrate unstaging without losing edits
- [ ] Revert a test commit

