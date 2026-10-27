# Git & GitHub 

A hands-on Git and GitHub repository.

> **Learning rule:** Run the commands yourself, capture your own terminal/GitHub screenshots, and write what you learned. Do not upload passwords, access tokens, private keys, or other secrets.

## Repository Structure

```text
git-devops-practicals/
├── README.md
├── .gitignore
├── practicals/
│   ├── 01-git-basics.md
│   ├── 02-branching-merging.md
│   ├── 03-remote-repository.md
│   ├── 04-undo-recovery.md
│   ├── 05-merge-conflicts.md
│   ├── 06-stash-tags.md
│   ├── 07-github-collaboration.md
│   └── 08-advanced-git.md
└── screenshots/
    └── README.md
```

## Practicals

| # | Topic | Main commands / concepts |
|---|---|---|
| 01 | Git Basics | `git init`, `status`, `add`, `commit`, `log` |
| 02 | Branching and Merging | `branch`, `switch`, `merge` |
| 03 | Remote Repository | `clone`, `remote`, `push`, `pull`, `fetch` |
| 04 | Undo and Recovery | `restore`, `reset`, `revert` |
| 05 | Merge Conflicts | conflict creation, resolution, commit |
| 06 | Stash and Tags | `stash`, `tag`, release tags |
| 07 | GitHub Collaboration | issues, pull requests, reviews |
| 08 | Advanced Git | `cherry-pick`, `rebase`, `reflog`, `.gitignore` |

## Getting Started

1. Install Git and create a GitHub account.
2. Create a new public repository named `git-devops-practicals`.
3. Add these files to the repository, or upload the ZIP contents.
4. Start with `practicals/01-git-basics.md`.
5. Complete each practical on your computer.
6. Save screenshots in `screenshots/` and link them from the relevant practical.
7. Commit your progress with clear commit messages.

## Suggested Workflow

```bash
git status
git add .
git commit -m "docs: complete Git basics practical"
git push
```

Run `git status` before staging, and review what you are committing. Use only commands you understand, especially commands that rewrite history such as `git reset` and `git rebase`.

## Progress Checklist

- [ ] 01 Git Basics
- [ ] 02 Branching and Merging
- [ ] 03 Remote Repository
- [ ] 04 Undo and Recovery
- [ ] 05 Merge Conflicts
- [ ] 06 Stash and Tags
- [ ] 07 GitHub Collaboration
- [ ] 08 Advanced Git

## Notes

For every practical, include:
- Objective
- Commands executed
- Screenshot of the result
- What you learned
- Any error and how you fixed it

