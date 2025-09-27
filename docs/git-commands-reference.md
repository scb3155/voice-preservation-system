# Git Commands Reference

## Configuration Commands

### Initial Setup (run once per machine)
```bash
git config --global user.name "Shane Battier"
git config --global user.email "scb011213@gmail.com"
git config --global init.defaultBranch main
git config --global pull.rebase false
```

### View Configuration
```bash
git config --global --list              # View all global settings
git config user.name                    # Check your name
git config user.email                   # Check your email
```

## Repository Commands

### Creating Repositories
```bash
git init                                 # Initialize new repository in current folder
git clone git@github.com:scb3155/repo.git    # Clone repository from GitHub
```

### Remote Repositories
```bash
git remote -v                           # Show remote repositories
git remote add origin git@github.com:scb3155/repo.git   # Add remote repository
git remote remove origin                # Remove remote repository
```

## Daily Workflow Commands

### Checking Status
```bash
git status                              # See current status of files
git status -s                           # Short status format
git diff                                # See unstaged changes
git diff --staged                       # See staged changes
git diff HEAD~1                         # Compare with previous commit
```

### Staging Files
```bash
git add filename.py                     # Stage specific file
git add .                               # Stage all changes in current directory
git add *.py                            # Stage all Python files
git add -A                              # Stage all changes in repository
git add -u                              # Stage only modified/deleted files (not new)
```

### Unstaging Files
```bash
git reset                               # Unstage all files
git reset filename.py                   # Unstage specific file
git reset --hard                        # Discard all changes (dangerous!)
```

### Committing Changes
```bash
git commit -m "Your message here"       # Commit staged changes
git commit -am "Your message"           # Stage all modified files and commit
git commit --amend -m "New message"     # Change last commit message
git commit --amend --no-edit            # Add more changes to last commit
```

### Synchronizing with GitHub
```bash
git push                                # Push current branch to GitHub
git push origin main                    # Push main branch to origin remote
git push -u origin main                 # Push and set upstream tracking
git pull                                # Fetch and merge changes from GitHub
git fetch                               # Download changes without merging
```

## Branch Commands

### Working with Branches
```bash
git branch                              # List all local branches
git branch -r                           # List remote branches
git branch -a                           # List all branches (local and remote)
git branch feature-name                 # Create new branch
git checkout feature-name               # Switch to branch
git checkout -b feature-name            # Create and switch to new branch
git branch -d feature-name              # Delete branch (safe)
git branch -D feature-name              # Force delete branch
```

### Merging
```bash
git merge feature-name                  # Merge feature-name into current branch
git merge --no-ff feature-name          # Merge without fast-forward
```

## History and Information

### Viewing History
```bash
git log                                 # Full commit history
git log --oneline                       # Compact one-line format
git log -5                              # Show last 5 commits
git log --graph                         # Show branch graph
git log --author="Shane"                # Show commits by author
git show                                # Show details of last commit
git show commit-hash                    # Show details of specific commit
```

### Searching
```bash
git grep "search term"                  # Search for text in tracked files
git log --grep="bug fix"                # Search commit messages
git log -S "function_name"              # Search for code changes
```

## Undoing Changes

### Undoing Unstaged Changes
```bash
git checkout -- filename.py            # Restore specific file to last commit
git checkout -- .                      # Restore all files to last commit
git restore filename.py                 # Newer way to restore file
git restore .                          # Restore all files
```

### Undoing Commits
```bash
git reset --soft HEAD~1                # Undo last commit, keep changes staged
git reset HEAD~1                       # Undo last commit, unstage changes
git reset --hard HEAD~1                # Undo last commit, discard changes
git revert commit-hash                  # Create new commit that undoes changes
```

## File Management

### Tracking Files
```bash
git add filename.py                     # Start tracking new file
git rm filename.py                      # Remove file from git and filesystem
git rm --cached filename.py             # Stop tracking file but keep on filesystem
git mv oldname.py newname.py            # Rename/move file
```

### Ignoring Files
```bash
# Create/edit .gitignore file
echo "*.log" >> .gitignore              # Ignore all .log files
echo "node_modules/" >> .gitignore      # Ignore directory
```

## Useful Shortcuts and Tips

### Aliases (add these to save time)
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
```

### After setting aliases, you can use:
```bash
git st          # instead of git status
git co main     # instead of git checkout main
git br          # instead of git branch
git ci -m "msg" # instead of git commit -m "msg"
```

## Emergency Commands (Use Carefully)

### When You're Really Stuck
```bash
git stash                              # Temporarily save changes
git stash pop                          # Restore stashed changes
git stash list                         # See all stashes
git stash drop                         # Delete most recent stash

git clean -fd                          # Remove untracked files and directories
git reset --hard HEAD                  # Discard all local changes
git reset --hard origin/main           # Reset to match GitHub exactly
```

## Multi-Device Commands

### Keeping Everything in Sync
```bash
# Before starting work:
git pull

# After finishing work:
git add .
git commit -m "Work done on [device name]"
git push

# Check what's on GitHub vs local:
git fetch
git status
git log origin/main..HEAD              # Show local commits not on GitHub
git log HEAD..origin/main              # Show GitHub commits not local
```

## Troubleshooting Common Issues

### Merge Conflicts
```bash
git status                             # See which files have conflicts
# Edit the conflicted files manually
git add resolved-file.py               # Mark conflicts as resolved
git commit                             # Complete the merge
```

### Authentication Issues
```bash
ssh -T git@github.com                  # Test SSH connection to GitHub
ssh-add -l                            # List SSH keys loaded
ssh-add ~/.ssh/id_ed25519             # Add SSH key to agent
```

### Checking SSH Keys
```bash
ls -la ~/.ssh/                        # List SSH keys
cat ~/.ssh/id_ed25519.pub             # Display public key
```