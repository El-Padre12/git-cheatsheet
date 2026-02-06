
# Git Quick Survival Cheatsheet

### Setup
```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@email.com"
git config --global init.defaultBranch main
```

### Start a Repo
```bash
git init
git status
```

### Stage & Commit
```bash
git add filename
git add .
git commit -m "Meaningful message"
```
**Staging = choosing what will be saved**      
**Commit = snapshot in time**

### View History
```bash
git log --oneline --graph --all --parents
```

### Branches
```bash
git branch
git switch -c feature-name  # checkout -b is oldschool
git switch main           # branch names should always be lowercase seperated with '-' or '_'
```

### Merge
```bash
git switch main     # always switch to main before merging - applies only to individual workflow
git merge feature-name
```

### Undo & Fix
```bash
git restore filename
git reset HEAD filename
```

### Push to GitHub
```bash
git remote add origin git@github.com:USER/REPO.git
git push -u origin main

# on feature branch locally push to feature-name to open a PR
# the output of the command below should give you a link to open a PR in Github
git push origin feature-name
```

### SSH Setup
```bash
ssh-keygen -t ed25519 -C "you@email.com"
cat ~/.ssh/id_ed25519.pub   # keep private safe and never share or push to github
ssh -T git@github.com   # verifies
```

---

## Git Workflow Diagram

Working Directory  
→ `git add`  
Staging Area  
→ `git commit`  
Local Repo  
→ `git push`  
GitHub (Remote)

**Feature Flow**
```
main
 → switch to feature-x branch
 → commit work
 → open pull request
 → approve and merge to main
```

---

## Top 10 Git Mistakes Students Make

1. Forgetting to commit changes  
2. Vague commit messages ("update")  
3. Working directly on `main`  
4. Forgetting to pull before pushing  
5. Committing secrets  
6. Not checking `git status`  
7. Making huge commits  
8. Fear of merge conflicts  
9. Not pushing to GitHub  
10. Treating Git like magic
