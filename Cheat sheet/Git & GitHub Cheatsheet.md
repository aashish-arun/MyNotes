## Git Basics

### Check git version
```sh
git --version
```

### Configure git username
```sh
git config --global user.name "username"
```

### Check global username
```sh
git config user.name
```

### Configure git email
```sh
git config --global user.email "email@gmail.com"
```

### Check global email
```sh
git config user.email
```

### View contents  in the current directory (Windows Command Prompt)
```sh
dir
```

### View contents  in the current directory (Linux and macOS)
```sh
ls
```

### Change directory
```sh
cd directory-name
```

### Go Up One Directory Level / Move Back to the parent directory
```sh
cd ..
```

### Create a Directory
```sh
mkdir directory-name
```

### Initialize a Git Repository
```bash
git init
```

### Check Git Status
```bash
git status
```

### View Commit History
```bash
git log
```

### Remove a Directory and Its Contents
```sh
rm <directory-name> -rf
```
---

## Working with Git

### Stage Changes
```bash
git add <file>      # Add a specific file
git add .           # Add all changes
```

### Commit Changes
```bash
git commit -m "Your commit message"
```

### Check Differences
```bash
git diff
```

### View Staged Changes
```bash
git diff --staged
```
---

### Undo Last Commit (but keep changes)
```bash
git reset --soft HEAD~1
```

### Undo Last Commit (and delete its changes)
```bash
git reset --soft HEAD~1
```
---
## Git Branching
### Create a New Branch
```bash
git branch <branch-name>
```

### Switch Branches
```bash
git checkout <branch-name>
```

### Create and Switch to a New Branch
```bash
git checkout -b <branch-name>
```

### Merge a Branch
```bash
git checkout main      # Switch to main branch
git merge <branch-name> # Merge another branch
```

### Delete a Branch
```bash
git branch -d <branch-name>
```

---
## Remote Repositories

### Add a Remote Repository
```bash
git remote add origin <repository-url>
```

### View Remote Repositories
```bash
git remote -v
```

### Fetch Changes from Remote
```bash
git fetch
```

### Pull Changes from Remote
```bash
git pull origin <branch-name>
```

### Push Changes to Remote
```bash
git push origin <branch-name>
```

### Clone a Repository
```bash
git clone <repository-url>
```

