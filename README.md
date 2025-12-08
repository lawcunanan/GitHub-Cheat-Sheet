# GitHub Cheat Sheet

A quick reference for common Git and GitHub commands.

---

## 1. Deploy (First Time Upload to GitHub)

```bash
git init
git add README.md
git commit -m "Add README"

git add .
git commit -m "Initial setup"

git branch -M main
git remote add origin <url>
git push -u origin main
```

---

## 2. Clone Existing Repo

```bash
git clone <repo-url>
cd <project-folder>
```

### Switch to main
```bash
git checkout main
```

### Pull latest
```bash
git pull origin main
```

---

## 3. Push to Main (Normal Updates)

```bash
git add .
git commit -m "Update"
git push origin main
```

---

## 4. Create New Branch (Local & Remote)

```bash
git branch                     # Show branches
git branch <branch-name>       # Create new local branch
git checkout <branch-name>     # Switch to that branch
```

### After doing work
```bash
git add .
git commit -m "Update"
git push -u origin <branch-name>
```

---

## 5. Merge Another Branch Into Your Branch

🔄 Example: Merge `develop` → `<your-branch>`

### 1. Switch to develop
```bash
git checkout develop
```

### 2. Pull latest develop
```bash
git pull origin develop
```

### 3. Switch back to your branch
```bash
git checkout <your-branch>
```

### 4. Merge develop into your branch (skip editor)
```bash
git merge develop --no-edit
```

---

### If conflicts appear

Fix the files manually, then run:

```bash
git add <file>
git commit
```

---

### Push merged branch
```bash
git push origin <your-branch>
```
