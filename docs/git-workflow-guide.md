# Daily Git Workflow Guide

## The Essential Git Workflow

This is the workflow you'll use every day as a developer. Master these commands and you'll be productive with Git.

### 1. Starting a New Project

#### Option A: Create a new repository on GitHub first (Recommended)
1. Go to https://github.com/scb3155
2. Click "New" repository
3. Name your repository (e.g., `learning-python`)
4. Add description
5. Make it public or private
6. ✅ Check "Add a README file"
7. Choose a .gitignore template if available
8. Click "Create repository"

#### Option B: Start locally and push to GitHub
```bash
# Navigate to your project directory
cd ~/Development/learning/python/my-project

# Initialize a Git repository
git init

# Add all files to staging
git add .

# Make your first commit
git commit -m "Initial commit"

# Create repository on GitHub (via web interface)
# Then connect local repo to GitHub:
git remote add origin git@github.com:scb3155/repository-name.git
git branch -M main
git push -u origin main
```

### 2. Daily Development Workflow

#### A. Clone a repository (first time only)
```bash
# Navigate to where you want the project
cd ~/Development/learning/python/

# Clone the repository
git clone git@github.com:scb3155/learning-python.git

# Navigate into the project
cd learning-python
```

#### B. Start working (every day)
```bash
# Make sure you have the latest changes
git pull

# Check what's changed
git status

# Start coding...
```

#### C. Save your work (regularly throughout the day)
```bash
# See what you've changed
git status
git diff

# Add specific files to staging
git add filename.py
git add another-file.js

# Or add all changed files
git add .

# Commit your changes with a descriptive message
git commit -m "Add user authentication feature"

# Push to GitHub
git push
```

### 3. Essential Commands Explained

#### `git status`
Shows you:
- Which files are modified
- Which files are staged for commit
- Which files are untracked (new files)

```bash
git status
```

#### `git add`
Stages files for commit (prepares them to be saved):
```bash
git add file.py          # Add specific file
git add .                # Add all changes
git add *.py             # Add all Python files
```

#### `git commit`
Saves your staged changes with a message:
```bash
git commit -m "Your descriptive message here"
```

#### `git push`
Uploads your commits to GitHub:
```bash
git push                 # Push to current branch
git push origin main     # Push main branch to origin remote
```

#### `git pull`
Downloads and merges changes from GitHub:
```bash
git pull                 # Get latest changes from GitHub
```

#### `git clone`
Downloads a repository for the first time:
```bash
git clone git@github.com:scb3155/repository-name.git
```

### 4. Good Commit Messages

#### Bad Examples:
- "fix"
- "update"
- "stuff"
- "changes"

#### Good Examples:
- "Add user login functionality"
- "Fix calculation bug in budget tracker"
- "Update README with installation instructions"
- "Remove unused CSS styles"

### 5. When Things Go Wrong

#### Undo unstaged changes (haven't added yet):
```bash
git checkout -- filename.py    # Undo changes to specific file
git checkout -- .              # Undo all unstaged changes
```

#### Undo staged changes (added but not committed):
```bash
git reset filename.py           # Unstage specific file
git reset                       # Unstage all files
```

#### Fix the last commit message:
```bash
git commit --amend -m "Better commit message"
```

#### See commit history:
```bash
git log                         # Full history
git log --oneline              # Compact history
git log -5                     # Last 5 commits
```

## Multi-Device Workflow

### Setting Up on Additional Devices

1. **Install Git** on the new device
2. **Configure Git** with your name and email:
   ```bash
   git config --global user.name "Shane Battier"
   git config --global user.email "scb011213@gmail.com"
   ```
3. **Generate SSH keys** for the new device:
   ```bash
   ssh-keygen -t ed25519 -C "scb011213@gmail.com"
   ```
4. **Add the new SSH key to GitHub** (Settings → SSH and GPG keys)
5. **Clone your repositories**:
   ```bash
   cd ~/Development/learning/python/
   git clone git@github.com:scb3155/repository-name.git
   ```

### Daily Multi-Device Workflow

#### Before starting work (every time):
```bash
git pull    # Get latest changes from other devices
```

#### After finishing work (every time):
```bash
git add .
git commit -m "Descriptive message"
git push    # Send changes to other devices
```

### Important Rules for Multi-Device Development:
1. **Always `git pull` before starting work**
2. **Always `git push` when you finish working**
3. **Commit frequently** - don't let changes pile up
4. **Use descriptive commit messages** to track what you did on each device

This workflow ensures your code stays synchronized across all your devices!