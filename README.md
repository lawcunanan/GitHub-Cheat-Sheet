# GitHub Cheat Sheet

A quick reference for common Git and GitHub commands.

---

## 1. Deploy (First Time Upload to GitHub)

Use these commands to push your project to GitHub for the first time.

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

## 2. Clone (If Repository Already Exists on GitHub)

Clone an existing repository and switch to the main branch.

```bash
git clone <repo-url>
cd <project-folder>
git switch main

# Always pull latest changes before starting work
git pull origin main
```

---

## 3. Push Main (Normal Updates)

Use these commands to update your repository with new changes.

```bash
git add .            # Or specify files like page.html
git commit -m "Update"
git push origin main
```

---

## 4. New Branch (Create & Push)

Create a new branch, switch to it, and push changes.

```bash
git branch           # Check existing branches
git branch <branch-name>
git switch -c <branch-name>  # Create AND switch to new branch
git add .
git commit -m "Update"
git push -u origin <branch-name>
```

---

## 5. Switch Branch (Go Back to Main)

Switch back to the main branch and update it with latest changes.

```bash
git switch main
git pull origin main
git add .
git commit -m "Update"
git push origin main
```

---

## 6. Handling Conflicts

### Scenario

* Person A edits `footer.php` on line 10 and pushes. ✅ No conflict because it's the first push.
* Person B also edits `footer.php` on the **same line** but hasn’t pulled Person A’s changes yet.

**What happens when Person B tries to push?**
Git sees that the remote has changes that B doesn’t have locally. The push is blocked and Git shows:

```
Updates were rejected because the remote contains work that you do not have locally.
```

This is because pushing would overwrite remote changes → possible data loss.

---

### How to Resolve (for Person B)

1. **Pull first with rebase**

```bash
git pull origin main --rebase
```

2. **Fix conflicts (if any appear)**
   Git will show conflict markers if the same line was edited. Edit the file to combine or choose the correct version.

3. **Continue the rebase**

```bash
git add <file>
git rebase --continue
```

4. **Push again**

```bash
git push origin main
```

---

### Notes

* Replace `<url>` with your GitHub repository URL.
* Replace `<repo-url>` with the clone URL of your repository.
* Replace `<branch-name>` with the desired branch name.
* Always pull before starting work to avoid conflicts.
