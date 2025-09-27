# Multi-Device Development Setup Guide

## Overview

This guide will help you set up Git and GitHub on your home desktop, laptop, and work computer so you can seamlessly work across all three devices.

## Device Setup Checklist

### For Each New Device (Laptop, Work Computer)

#### 1. Install Git
**macOS:**
```bash
# Check if already installed
git --version

# If not installed, install via Homebrew:
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install git
```

**Windows:**
- Download from https://git-scm.com/download/win
- Run installer with default settings

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install git
```

#### 2. Configure Git Identity
```bash
git config --global user.name "Shane Battier"
git config --global user.email "scb011213@gmail.com"
git config --global init.defaultBranch main
git config --global core.autocrlf input    # macOS/Linux
git config --global core.autocrlf true     # Windows
git config --global pull.rebase false
```

#### 3. Generate SSH Keys for Each Device
```bash
# Generate key with device-specific name
ssh-keygen -t ed25519 -C "scb011213@gmail.com" -f ~/.ssh/id_ed25519_[device]

# Example device names:
# id_ed25519_home_desktop
# id_ed25519_laptop
# id_ed25519_work
```

#### 4. Add SSH Key to SSH Agent
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519_[device]
```

#### 5. Add SSH Key to GitHub
```bash
# Display the public key
cat ~/.ssh/id_ed25519_[device].pub

# Copy the output and add to GitHub:
# 1. Go to https://github.com/settings/keys
# 2. Click "New SSH key"
# 3. Title: "Shane's [Device Name]" (e.g., "Shane's Laptop")
# 4. Paste the key
# 5. Click "Add SSH key"
```

#### 6. Test SSH Connection
```bash
ssh -T git@github.com
# Should see: "Hi scb3155! You've successfully authenticated..."
```

#### 7. Create Development Directory Structure
```bash
mkdir -p ~/Development/{learning/{python,javascript,react},personal,work,templates}
```

#### 8. Set Up Git Aliases (Optional but Recommended)
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
```

## Multi-Device Workflow Rules

### The Golden Rules

1. **Always `git pull` before starting work**
2. **Always `git push` when finishing work**
3. **Commit frequently with descriptive messages**
4. **Never leave uncommitted changes when switching devices**

### Daily Workflow by Device

#### Starting Work on Any Device:
```bash
cd ~/Development/[project-type]/[project-name]
git pull                    # Get latest changes
git status                  # Check current state
# Start coding...
```

#### Finishing Work on Any Device:
```bash
git status                  # See what changed
git add .                   # Stage all changes
git commit -m "Work completed on [device]: [description]"
git push                    # Send to GitHub
```

#### Example Commit Messages by Device:
- "Work completed on laptop: Add user authentication module"
- "Work completed on home desktop: Fix CSS styling issues"
- "Work completed on work computer: Update documentation"

### Handling Multiple Devices

#### Check What's Different:
```bash
git fetch                   # Get latest info from GitHub
git status                  # See local vs remote status
git log origin/main..HEAD   # See local commits not on GitHub
git log HEAD..origin/main   # See GitHub commits not local
```

#### Sync Before Major Changes:
```bash
git fetch
git pull
# Resolve any conflicts if they exist
# Then continue with your work
```

## File Synchronization Strategy

### What Gets Synchronized:
✅ **Always sync:**
- Source code files
- Configuration files (package.json, requirements.txt, etc.)
- Documentation files
- README files
- .gitignore files

❌ **Never sync (add to .gitignore):**
- IDE-specific files (.vscode/, .idea/)
- OS-specific files (.DS_Store, Thumbs.db)
- Dependencies (node_modules/, venv/)
- Build artifacts (dist/, build/)
- Log files (*.log)
- Environment files (.env)

### Managing Device-Specific Settings

#### Create a `local.config` pattern:
```bash
# In your project root, create files like:
local.config.example        # Template file (commit this)
local.config                # Actual config (add to .gitignore)
```

#### Example .gitignore additions:
```
# Device-specific configurations
local.config
config.local.*
*.local
.env.local
```

## Troubleshooting Common Multi-Device Issues

### Issue: "Repository not found" on new device
**Solution:**
```bash
# Make sure you're using SSH, not HTTPS
git remote -v
# Should show: git@github.com:scb3155/repo.git
# If it shows https://, change it:
git remote set-url origin git@github.com:scb3155/repo.git
```

### Issue: Merge conflicts between devices
**Solution:**
```bash
git pull                    # This will show conflict
git status                  # See which files have conflicts
# Edit conflicted files manually, look for <<<< and >>>>
git add .                   # Mark conflicts as resolved
git commit                  # Complete the merge
git push                    # Send resolution to GitHub
```

### Issue: Forgot to push from previous device
**Solution:**
```bash
# On current device, before starting work:
git fetch
git status
# If behind, pull the changes:
git pull
# Now you can start working
```

### Issue: SSH key not working on new device
**Solution:**
```bash
# Test connection:
ssh -T git@github.com

# If it fails, check if key is loaded:
ssh-add -l

# If no keys listed, add your key:
ssh-add ~/.ssh/id_ed25519_[device]

# Make sure the public key is added to GitHub
cat ~/.ssh/id_ed25519_[device].pub
```

## Project Cloning Strategy

### When setting up a new device, clone all your active repositories:

```bash
cd ~/Development/learning/python/
git clone git@github.com:scb3155/learning-python.git

cd ~/Development/personal/
git clone git@github.com:scb3155/budget-tracker.git
git clone git@github.com:scb3155/portfolio-website.git

cd ~/Development/work/
git clone git@github.com:scb3155/work-project.git
```

### Use a script to clone multiple repos:

Create `~/Development/setup-repos.sh`:
```bash
#!/bin/bash

# Learning projects
cd ~/Development/learning/python/
git clone git@github.com:scb3155/learning-python.git
git clone git@github.com:scb3155/practice-algorithms.git

# Personal projects
cd ~/Development/personal/
git clone git@github.com:scb3155/budget-tracker.git
git clone git@github.com:scb3155/portfolio-website.git

echo "All repositories cloned successfully!"
```

Make it executable and run:
```bash
chmod +x ~/Development/setup-repos.sh
./setup-repos.sh
```

## Best Practices Summary

1. **Use descriptive commit messages** that include which device you worked on
2. **Commit small, logical changes** frequently
3. **Always pull before starting**, push when finishing
4. **Test on each device** after major changes
5. **Keep device-specific configurations in ignored files**
6. **Use the same directory structure** on all devices
7. **Name your SSH keys** by device for easy identification
8. **Document device-specific setup** in your project READMEs if needed

Following these practices will ensure smooth development across all your devices!