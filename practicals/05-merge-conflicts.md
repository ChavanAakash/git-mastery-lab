# Practical 05: Merge Conflicts

## Objective
Intentionally create a merge conflict, resolve it, and complete the merge.

## Steps
Start with a committed file named `message.txt` on `main`.

```bash
git switch -c feature/change-message
```

Change the same line in `message.txt`, then commit:

```bash
git add message.txt
git commit -m "feat: change message on feature branch"
git switch main
```

On `main`, change that same line differently and commit:

```bash
git add message.txt
git commit -m "docs: change message on main"
git merge feature/change-message
```

Git should report a conflict if both branches changed the same line differently. Open the file and find markers such as `<<<<<<<`, `=======`, and `>>>>>>>`. Edit the file to keep the intended final content and remove the markers.

```bash
git add message.txt
git commit -m "fix: resolve merge conflict"
git status
```

## Verify
- [ ] Conflict reproduced
- [ ] Conflict markers removed
- [ ] Resolution committed and working tree clean
