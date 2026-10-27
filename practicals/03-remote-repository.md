# Practical 03: Remote Repository

## Objective
Connect a local repository to GitHub and push and pull changes.

## Steps
1. Create an empty GitHub repository. If you already have local commits, avoid initializing the remote with extra files to keep the first push simple.
2. Copy the repository's HTTPS URL from GitHub.
3. In your local project, run the commands below, replacing the example URL with your own.

```bash
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git remote -v
git branch -M main
git push -u origin main
```

After making and committing a new change:

```bash
git push
git fetch origin
git pull
```

To copy an existing repository to a new folder:

```bash
git clone https://github.com/OWNER/REPOSITORY.git
```

## Verify
- [ ] `git remote -v` shows the remote
- [ ] Local commits appear on GitHub
- [ ] Fetch/pull completed successfully

