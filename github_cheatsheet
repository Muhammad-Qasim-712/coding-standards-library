# Git & GitHub Complete Beginner's Cheat Sheet

## 📋 Prerequisites
Before you start, make sure you have:
- Git installed on your computer ([git-scm.com](https://git-scm.com/))
- A GitHub account ([github.com](https://github.com))
- Created a repository on GitHub (can be empty or with README)

---

## 🚀 Initial Setup

### Step 1: Configure Git (One-time setup)
```bash
git config --global user.name "Your Name"
# Sets your name for all Git commits

git config --global user.email "your.email@example.com"
# Sets your email for all Git commits
```

### Step 2: Initialize Local Repository
```bash
cd /path/to/your/project
# Navigate to your project folder

git init
# Creates a new Git repository in current folder
```

### Step 3: Connect to Remote GitHub Repository
```bash
git remote add origin https://github.com/username/repository-name.git
# Links your local repo to the GitHub repository

git remote -v
# Verify the remote connection (should show fetch and push URLs)
```

### Step 4: Pull Existing Content (if GitHub repo has files)
```bash
git pull origin main
# Downloads any existing files from GitHub to your local folder
```

---

## 🔄 Basic Daily Workflow

### Step 1: Check Status
```bash
git status
# Shows which files are changed, staged, or untracked
```

### Step 2: Add Files
```bash
git add filename.txt
# Adds a specific file to staging area

git add .
# Adds ALL changed files to staging area (most common)

git add *.py
# Adds all Python files to staging area
```

### Step 3: Commit Changes
```bash
git commit -m "Add weather API functionality"
# Saves your changes with a descriptive message

git commit -m "Fix bug in temperature calculation"
# Always use clear, descriptive messages
```

### Step 4: Push to GitHub
```bash
git push origin main
# Uploads your commits to GitHub repository

git push -u origin main
# First time push (sets upstream, then just use 'git push')
```

---

## 🛠️ Essential Commands

### Checking Repository Status
```bash
git status
# Shows current status of your working directory

git log
# Shows commit history with full details

git log --oneline
# Shows commit history in compact format

git diff
# Shows changes in files that aren't staged yet

git diff --staged
# Shows changes in files that are staged for commit
```

### Working with Remote Repository
```bash
git pull origin main
# Downloads and merges changes from GitHub to your local repo

git fetch origin
# Downloads changes from GitHub but doesn't merge them

git push origin main
# Uploads your local commits to GitHub

git clone https://github.com/username/repo-name.git
# Downloads a complete copy of a GitHub repository
```

### Branch Management (Optional for beginners)
```bash
git branch
# Shows all local branches (main branch is usually called 'main')

git checkout -b new-feature
# Creates and switches to a new branch called 'new-feature'

git checkout main
# Switches back to main branch

git merge new-feature
# Merges 'new-feature' branch into current branch
```

### Undoing Changes
```bash
git checkout -- filename.txt
# Discards changes in a specific file (reverts to last commit)

git reset HEAD filename.txt
# Unstages a file (removes from staging area)

git reset --soft HEAD~1
# Undoes last commit but keeps changes staged

git reset --hard HEAD~1
# Undoes last commit and discards all changes (DANGEROUS!)
```

---

## 🚨 Troubleshooting & Tips

### Common Issues & Solutions

**Problem: "fatal: remote origin already exists"**
```bash
git remote remove origin
git remote add origin https://github.com/username/repo-name.git
# Removes old remote and adds new one
```

**Problem: "Updates were rejected because the remote contains work"**
```bash
git pull origin main --allow-unrelated-histories
# Merges remote changes with your local changes
```

**Problem: Forgot to add files before committing**
```bash
git add forgotten-file.txt
git commit --amend --no-edit
# Adds file to the last commit without changing commit message
```

**Problem: Wrong commit message**
```bash
git commit --amend -m "Correct commit message"
# Changes the last commit message
```

### Best Practices

✅ **DO:**
- Commit often with small, logical changes
- Use clear, descriptive commit messages
- Always `git status` before committing
- Pull before pushing to avoid conflicts
- Use `.gitignore` for files you don't want to track

❌ **DON'T:**
- Commit sensitive data (passwords, API keys)
- Use `git add .` without checking what files you're adding
- Force push (`git push --force`) unless you know what you're doing
- Commit broken code to main branch

### Useful Shortcuts
```bash
git add . && git commit -m "Your message" && git push
# Adds all files, commits, and pushes in one line

git commit -am "Your message"
# Adds all modified files and commits (doesn't work for new files)

git log --graph --oneline --all
# Shows a visual representation of your commit history
```

### Emergency Commands
```bash
git stash
# Temporarily saves your changes without committing

git stash pop
# Restores your stashed changes

git reflog
# Shows a log of all Git actions (useful for recovering lost commits)
```

---

## 📝 Quick Reference Card

| Command | What it does |
|---------|--------------|
| `git status` | Check current status |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save changes with message |
| `git push` | Upload to GitHub |
| `git pull` | Download from GitHub |
| `git log` | View commit history |
| `git clone <url>` | Download repository |

---

## 🎯 Typical Workflow Summary

1. **Make changes** to your files
2. **Check status**: `git status`
3. **Add files**: `git add .`
4. **Commit**: `git commit -m "descriptive message"`
5. **Push**: `git push origin main`
6. **Repeat** for next set of changes

**Remember**: Git is about saving snapshots of your project over time. Each commit is like a save point in a video game - you can always go back to it later!
