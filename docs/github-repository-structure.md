# GitHub Repository Structure Plan

## Repository Naming Conventions

### Learning Projects
- `learning-[technology]` - e.g., `learning-python`, `learning-react`
- `tutorial-[name]` - e.g., `tutorial-flask-blog`, `tutorial-node-api`
- `practice-[concept]` - e.g., `practice-algorithms`, `practice-design-patterns`

### Personal Projects
- `[project-name]` - descriptive names like `budget-tracker`, `recipe-manager`
- `tools-[purpose]` - e.g., `tools-automation`, `tools-productivity`
- `portfolio-[type]` - e.g., `portfolio-website`, `portfolio-projects`

### Work Projects (if applicable)
- `work-[project-name]` - e.g., `work-dashboard`, `work-api-integration`
- Use your company's naming conventions if they have them

## Repository Organization Strategy

### Option 1: Individual Repositories (Recommended)
Each project gets its own repository:
- `scb3155/learning-python`
- `scb3155/budget-tracker`
- `scb3155/portfolio-website`

**Pros**:
- Clean separation of concerns
- Individual version history
- Easy to share specific projects
- Better for collaboration

### Option 2: Monorepo by Category
Group related projects in single repositories:
- `scb3155/learning-projects` (contains multiple learning folders)
- `scb3155/personal-projects` (contains multiple personal project folders)

**Pros**:
- Fewer repositories to manage
- Easier to sync everything at once

## Recommended Structure (Individual Repos)

```
GitHub Account: scb3155
├── learning-python          # Python learning exercises
├── learning-javascript       # JavaScript tutorials and practice
├── learning-react           # React learning projects
├── practice-algorithms      # Coding challenges and algorithms
├── budget-tracker          # Personal finance app
├── portfolio-website       # Your professional portfolio
├── tools-scripts          # Useful automation scripts
└── dotfiles               # Configuration files for development environment
```

## Local Directory Structure

On each of your devices, create this folder structure:

```
~/Development/
├── learning/               # Learning and tutorial projects
│   ├── python/
│   ├── javascript/
│   └── react/
├── personal/              # Personal projects
│   ├── budget-tracker/
│   ├── portfolio-website/
│   └── tools-scripts/
├── work/                  # Work-related projects (if applicable)
└── templates/            # Project templates and starter files
```

This structure mirrors your GitHub repositories and makes it easy to find projects locally.