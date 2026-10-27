# Practical 07: GitHub Collaboration

## Objective
Practice the basic collaboration flow using an Issue and Pull Request.

## Steps
1. Open your repository on GitHub.
2. Create an Issue describing a small documentation improvement.
3. Create a branch locally:

```bash
git switch -c docs/improve-readme
```

4. Make the change, then commit and push:

```bash
git add README.md
git commit -m "docs: improve project instructions"
git push -u origin docs/improve-readme
```

5. On GitHub, open a Pull Request from `docs/improve-readme` into `main`.
6. Review the diff, add a clear description, and merge when satisfied.
7. Delete the feature branch if it is no longer needed.

## Pull Request checklist
- [ ] Clear title and description
- [ ] Diff reviewed before merge
- [ ] No secrets or unrelated files included
- [ ] Issue linked when appropriate

