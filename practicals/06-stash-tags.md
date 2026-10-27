# Practical 06: Stash and Tags

## Objective
Temporarily save uncommitted work and label a commit with a Git tag.

## Stash workflow
Edit a tracked file without committing:

```bash
git status
git stash push -m "WIP: temporary notes"
git stash list
git stash pop
git status
```

If there are conflicts during `stash pop`, resolve them before continuing.

## Tag workflow
Create a commit first, then create and inspect a tag:

```bash
git tag
git tag -a v1.0.0 -m "First practice release"
git show v1.0.0
```

Push the tag to GitHub:

```bash
git push origin v1.0.0
```

## Verify
- [ ] Stash listed and restored
- [ ] Annotated tag created
- [ ] Tag visible on GitHub
