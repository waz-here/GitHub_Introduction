---
title: How to Import an Existing Repository into GitHub
description: Step-by-step guide to import a repository using both the GitHub web interface (GUI) and the command line (CLI). Example used: https://github.com/waz-here/GitHub_Introduction.git
---

# 🔄 Importing an Existing Repository into GitHub

If you already have a repository hosted elsewhere (or want to copy someone else’s public repo into your own account), you can **import** it using either the **web interface (GUI)** or the **command line (CLI)**.

This guide uses the example repository:  
<https://github.com/waz-here/GitHub_Introduction.git>

---

## 🧭 Option 1 — Import Using the GitHub Web Interface (GUI)

This is the easiest option for beginners and requires no terminal commands.

### Step 1 — Go to the Import Page
1. Log in to your GitHub account.  
2. Click the **“+”** icon in the top-right corner and choose **“Import repository”**.  
   Or visit: <https://github.com/new/import>

### Step 2 — Enter Repository Details
1. In **“Your old repository’s clone URL”**, paste:

   ```text
   https://github.com/waz-here/GitHub_Introduction.git
   ```

2. Under **Owner**, choose your GitHub username (or organisation).  
3. Under **Repository name**, enter something like:

   ```text
   GitHub_Introduction_Imported
   ```

4. (Optional) Add a description, e.g.:
   > A personal copy of the GitHub Introduction repository for learning purposes.

### Step 3 — Choose Visibility
Select one of the following:
- 🔓 **Public** — anyone can see it.
- 🔒 **Private** — only you and invited collaborators can view it.

### Step 4 — Begin the Import
Click **“Begin import”**. GitHub will:
- Clone the existing repository,
- Preserve the full commit history,
- Create a new copy under your account.

_This usually takes less than a minute._

### Step 5 — Verify the Import
When it completes, you’ll be redirected to your new repository, e.g.:

```
https://github.com/<your-username>/GitHub_Introduction_Imported
```

You can now edit files in the browser, open a **Codespace**, create **Issues**, and manage **Projects**.

---

## 💻 Option 2 — Import Using the Command Line (CLI)

This method gives you more control and is ideal if you already have `git` installed locally.

### Step 1 — Clone the Source Repository
Make a local copy of the existing repository:

```bash
git clone https://github.com/waz-here/GitHub_Introduction.git
```

This creates a folder named `GitHub_Introduction`.

### Step 2 — Change Directory
Move into the repository folder:

```bash
cd GitHub_Introduction
```

### Step 3 — Create a New (Empty) Repository on GitHub
1. Go to <https://github.com/new>.  
2. Name it, e.g.:

   ```text
   GitHub_Introduction_Imported
   ```

3. Leave it **empty** — do **not** add a README, licence, or .gitignore yet.

### Step 4 — Point Your Local Repo to the New GitHub Repo
Replace the current `origin` with your new remote URL:

```bash
# Optional: see the current branch name
git symbolic-ref --short HEAD

# Reset the origin remote to the new repository
git remote remove origin
git remote add origin https://github.com/<your-username>/GitHub_Introduction_Imported.git
```

> Replace `<your-username>` with your actual GitHub username.

### Step 5 — Push Your Code to GitHub
Push the current branch to the new remote. If your branch is **main**:

```bash
git push -u origin main
```

If your branch is **master** (older repos sometimes use this):

```bash
git push -u origin master
```

### Step 6 — Verify Your New Repository
Visit:

```
https://github.com/<your-username>/GitHub_Introduction_Imported
```

You should see all files and the full commit history from the original project.

---

## 🧩 Comparison (GUI vs CLI)

| Method | Best for | Requirements | Typical Use |
|---|---|---|---|
| **Web (GUI)** | Beginners or quick imports | Web browser only | Copying public repositories |
| **Command Line (CLI)** | Developers or advanced users | `git` installed locally | Private repos, custom remotes, bulk changes |

---

## 🧠 What Happens Behind the Scenes

When you import or clone a repository:
- Git preserves the **entire commit history** (who changed what, and when).  
- Branches, tags, and commit logs are retained.  
- You get your **own copy** — changes you make do *not* affect the original project.

---

## 🧩 Troubleshooting Tips

| Problem | Likely Cause | Fix |
|---|---|---|
| ❌ “Repository not found” | Source repo is private or requires credentials | Ensure you have permission and are logged in to the source host |
| ⚠️ Import stuck | Large repository or slow network | Wait and refresh — GitHub resumes automatically |
| 🔁 Duplicate name | You already have a repo with that name | Choose a different name (e.g., `_v2`, `_copy`) |

---

## 🚀 Next Steps

After importing:
- ✏️ Update **README.md** to describe your version.  
- 🧩 Create **Issues** and a **Project** board to manage tasks.  
- 💻 Try a **Codespace** for browser-based development.  
- 🔄 Use **git pull/push** to sync local and remote changes.

---

