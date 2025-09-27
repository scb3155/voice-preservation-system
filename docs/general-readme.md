# Shane's Development Environment

Complete GitHub-based development setup for working across multiple devices.

## Quick Start

### Daily Workflow
```bash
# Before starting work:
cd ~/Development/[project-type]/[project-name]
git pull

# After finishing work:
git add .
git commit -m "Descriptive message"
git push
```

## Documentation

- **[Git Workflow Guide](git-workflow-guide.md)** - Daily Git commands and workflows
- **[Git Commands Reference](git-commands-reference.md)** - Complete command reference
- **[Multi-Device Setup](multi-device-setup-guide.md)** - Setting up laptop and work computer
- **[Repository Structure](github-repository-structure.md)** - How repositories are organized

## Directory Structure

```
~/Development/
├── learning/               # Learning and tutorial projects
│   ├── python/
│   ├── javascript/
│   └── react/
├── personal/              # Personal projects
├── work/                  # Work-related projects
├── templates/            # Project templates
│   ├── python-project-template/
│   ├── javascript-project-template/
│   └── general-project-template/
└── [documentation files]
```

## Templates Available

- **Python Project**: Complete Python project structure with .gitignore
- **JavaScript Project**: Node.js project with package.json
- **General Project**: Universal template for any project type

## GitHub Account

- **Username**: scb3155
- **Email**: scb011213@gmail.com
- **SSH**: Configured for secure access

## Essential Commands

| Command | Purpose |
|---------|---------|
| `git status` | Check current state |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save changes |
| `git push` | Upload to GitHub |
| `git pull` | Download from GitHub |
| `git clone git@github.com:scb3155/repo.git` | Download repository |

## Creating a New Project

### Method 1: Start on GitHub (Recommended)
1. Go to https://github.com/scb3155
2. Click "New" repository
3. Name it following conventions (see repository structure guide)
4. Add README and .gitignore
5. Clone locally: `git clone git@github.com:scb3155/repo-name.git`

### Method 2: Start Locally
1. Copy appropriate template from `~/Development/templates/`
2. Initialize: `git init`
3. Add files: `git add .`
4. First commit: `git commit -m "Initial commit"`
5. Create repo on GitHub and push

## Next Steps for Other Devices

1. Follow **[Multi-Device Setup Guide](multi-device-setup-guide.md)**
2. Generate device-specific SSH keys
3. Clone your repositories
4. Start the daily workflow

## Troubleshooting

- SSH issues: `ssh -T git@github.com`
- See what changed: `git status` and `git diff`
- View commit history: `git log --oneline`
- Emergency help: Check the commands reference guide

---

*This development environment is set up for Shane Battier (scb3155) with secure SSH authentication and multi-device synchronization.*