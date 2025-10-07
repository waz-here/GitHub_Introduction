# Git & GitHub for New IT Professionals


This quick primer gets you from zero to contributing confidently.


## 1. Core concepts (60‑second summary)
- **Git** = version control on your machine (tracks changes)
- **GitHub** = remote hosting + collaboration (issues, pull requests)
- **Repository (repo)** = a project folder tracked by Git
- **Commit** = a snapshot with a message
- **Branch** = an isolated line of work (e.g., `feature/lab-docs`)
- **Pull Request (PR)** = propose merging your branch into `main`


## 2. One-time setup
```bash
# install git (example: Ubuntu)
sudo apt update && sudo apt install -y git


# identify yourself
git config --global user.name "Your Name"
git config --global user.email "you@example.com"


# optional: default to main
git config --global init.defaultBranch main

## 3. Create a repo on GitHub

- Sign in to GitHub and click New repository.
- Name it containerlab-ixp-labs and Add a README.
- Copy the HTTPS clone URL.

## 4. Clone & first commit
git clone https://github.com/<you>/containerlab-ixp-labs.git
cd containerlab-ixp-labs


# create or edit files
mkdir -p labs/ixp docs topologies scripts

# stage and commit
git add .
git commit -m "feat: repo scaffold and initial lab guides"

# push to GitHub
git push origin main

## 5. Safe collaboration with branches
# create a feature branch
git checkout -b feature/add-troubleshooting

# make edits, then
git add labs/ixp/06_troubleshooting.md
git commit -m "docs(ixp): add troubleshooting guide"

git push -u origin feature/add-troubleshooting

Open a Pull Request on GitHub → request review → Merge when approved.

## 6. Everyday commands cheat‑sheet
```
git status # what changed?
git add <file> # stage changes
git commit -m "message" # save a snapshot
git pull # update local from GitHub
git push # upload your commits to GitHub
```

## 7. Typical workflow

1. git pull (stay up‑to‑date)
2. Create/checkout a branch
3. Edit → git add → git commit
4. git push and open a PR
5. Review, fixups, merge

8. Fixing common hiccups

* Forgot to create a branch? Create one now and push: git checkout -b feature/xyz && git push -u origin HEAD
* Merge conflicts? Git shows conflict markers <<<<<<< → edit file → git add → git commit
* Accidentally committed secrets? Rotate the secret immediately. Use git filter-repo later to rewrite history (advanced).

9. Good practices

* Write clear commit messages: type(scope): short summary
* Small PRs are faster to review
* Keep main protected; use PRs
* Use .gitignore to avoid committing build artefacts, large images, secrets
