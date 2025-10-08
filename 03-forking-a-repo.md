# Understanding and Using Forks in GitHub

This guide explains the difference between *importing* and *forking* a repository, then walks through how to fork, keep it in sync, and contribute back to the original project.

---

## Import vs Fork — What’s the Difference?

| Action | What it does | Link/“Upstream” relationship | Typical use cases | Docs |
|---|---|---|---|---|
| **Fork a repo** | Creates **your own copy** of an existing GitHub repository under your account/org. | **Linked** to the original (“upstream”). You can fetch updates and submit pull requests back. | Contributing to open-source projects, experimenting safely while keeping a path to merge upstream. | <https://docs.github.com/en/get-started/quickstart/fork-a-repo> |
| **Import a repo** | Creates a **new repository** on GitHub by copying another repo’s contents (from GitHub or elsewhere). | **Not linked** to the source. It’s a clean, independent repo. | Migrating code to GitHub, starting a fresh project using existing code, or when you don’t intend to contribute back. | <https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/importing-a-repository-with-github-importer> |

### Rule of thumb
- **Fork** → when you want to **contribute back**.  
- **Import** → when you want an **independent copy**.

---

# How to Fork a Repository (and Keep It in Sync)

Forks are the standard GitHub workflow for contributing to someone else’s project while keeping your own version under control.

---

## Prerequisites
- A GitHub account.
- Git installed (`git --version`).
- Access to the repository (public or you have permission).

---

## 1. Fork the repository (Web UI)
1. Go to the repository you want to fork.  
2. Click **Fork** (top-right) → choose your account/org.  
3. Optionally rename or describe it → **Create fork**.

Docs → <https://docs.github.com/en/get-started/quickstart/fork-a-repo>

---

## 2. Clone your fork locally
```bash
# HTTPS
git clone https://github.com/YOUR-USER/REPO.git
cd REPO

# or SSH
git clone git@github.com:YOUR-USER/REPO.git
```

---

## 3. Add the original repo as an “upstream” remote
```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/REPO.git
git remote -v
```
You should see:
- `origin` → your fork  
- `upstream` → the original project  

Docs → <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork>

---

## 4. Keep your fork up to date
```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```
If the project uses `master`, substitute accordingly.  
Docs → <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork>

---

## 5. Create a feature branch for your work
```bash
git checkout -b feature/add-awesome-thing
# make your changes
git add .
git commit -m "Add awesome thing"
git push -u origin feature/add-awesome-thing
```

---

## 6. Open a Pull Request (PR)
1. Go to your fork on GitHub → **Compare & pull request**.  
2. Write a clear title and description.  
3. Confirm the **base repo** (original) and **base branch** (usually `main`).  
4. Submit and respond to reviews.

Docs → <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests>

---

## Common Tasks & Troubleshooting

### Rename `master` to `main`
```bash
git branch -m master main
git push -u origin main
```

### Update your branch
```bash
git fetch origin
git checkout feature/add-awesome-thing
git merge origin/main
```

### Fix a mistaken remote URL
```bash
git remote set-url origin https://github.com/YOUR-USER/REPO.git
git remote set-url upstream https://github.com/ORIGINAL-OWNER/REPO.git
```


## References
- GitHub Docs – Forking a repository: <https://docs.github.com/en/get-started/quickstart/fork-a-repo>  
- Configuring a remote for a fork: <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork>  
- Syncing a fork: <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork>  
- About pull requests: <https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests>
