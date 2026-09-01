# Git Workflow & Pull Request Process

This document explains the version control workflow used to submit the Goal Icons feature for the Commonwealth Bank simulation.

## Overview

The feature was developed across two separate repositories:
- **commbank-server** - Backend (.NET/C# API)
- **commbank-web** - Frontend (React/Redux)

Both repositories followed the same Git workflow for consistency.

---

## Workflow Steps

### 1. Create Feature Branch

Created a dedicated feature branch for the icon implementation:

```bash
git checkout -b feature/goal-icons
```

**Why a feature branch?**
- Keeps main branch stable
- Allows isolated development
- Enables team review before merging
- Facilitates rollback if needed

### 2. Stage Changes

Staged only the files modified for this feature (no build artifacts, dependencies, or IDE files):

**Server Repository:**
```bash
git add CommBank-Server/Models/Goal.cs
git add CommBank.Tests/GoalControllerTests.cs
```

**Web Repository:**
```bash
git add src/api/types.ts
git add src/ui/features/goalmanager/GoalManager.tsx
git add src/ui/pages/Main/goals/GoalCard.tsx
```

### 3. Commit Changes

Created descriptive commits following conventional commit format:

```bash
git commit -m "feat: add goal icons support"
```

**Commit Message Format:**
- `feat:` - New feature
- `fix:` - Bug fix
- `test:` - Adding tests
- `docs:` - Documentation changes

### 4. Push to Remote

Pushed the feature branch to the remote repository:

```bash
git push -u origin feature/goal-icons
```

The `-u` flag sets up tracking between local and remote branches.

### 5. Create Pull Request

Used GitHub's web interface to create Pull Requests with:

**PR Title:**
```
Add goal icon support
```

**PR Description:**
- Summary of changes
- List of modifications
- Testing performed
- Related issues (if any)

---

## Pull Request Best Practices

### What Makes a Good PR?

✅ **Clear Title** - Summarizes the change in one line  
✅ **Detailed Description** - Explains what, why, and how  
✅ **Small & Focused** - Changes one thing well  
✅ **Tests Included** - Demonstrates the feature works  
✅ **Clean Commits** - Logical, atomic changes  

### PR Review Process

1. **Code Review** - Team reviews the changes
2. **Automated Tests** - CI/CD runs test suite
3. **Feedback** - Reviewers suggest improvements
4. **Updates** - Developer addresses feedback
5. **Approval** - Team approves the changes
6. **Merge** - Changes integrated into main branch

---

## Common Git Commands

### Checking Status
```bash
git status              # View modified files
git diff                # See changes
git log --oneline -10   # View recent commits
```

### Branch Management
```bash
git branch              # List branches
git branch -a           # List all branches (including remote)
git checkout main       # Switch to main branch
git branch -d branch    # Delete local branch
```

### Syncing with Remote
```bash
git fetch origin        # Download remote changes
git pull origin main    # Update local main branch
git push origin branch  # Push local branch
```

### Undoing Changes
```bash
git restore file        # Discard local changes
git reset HEAD~1        # Undo last commit (keep changes)
git revert commit       # Create new commit that undoes another
```

---

## Repository Structure

### Server Repository (commbank-server)
```
commbank-server/
├── CommBank-Server/
│   ├── Controllers/      # API endpoints
│   ├── Models/          # Data models (Goal.cs modified)
│   └── Services/        # Business logic
└── CommBank.Tests/      # Unit tests
    └── GoalControllerTests.cs (GetForUser test added)
```

### Web Repository (commbank-web)
```
commbank-web/
└── src/
    ├── api/
    │   └── types.ts                    # TypeScript interfaces
    └── ui/
        ├── features/goalmanager/
        │   └── GoalManager.tsx          # Emoji picker
        └── pages/Main/goals/
            └── GoalCard.tsx             # Icon display
```

---

## Key Learnings

### Version Control Principles

1. **Commit Often** - Small, frequent commits are easier to review and revert
2. **Write Clear Messages** - Future you will thank present you
3. **Branch for Features** - Never commit directly to main
4. **Review Before Push** - Double-check what you're pushing
5. **Pull Before Push** - Sync with remote to avoid conflicts

### Collaboration Best Practices

- **Communicate** - Let the team know what you're working on
- **Test Locally** - Ensure tests pass before pushing
- **Respect Reviews** - Feedback makes code better
- **Document Changes** - Update README and docs as needed
- **Stay Organized** - Keep branches clean and up-to-date

---

## Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Writing Good Commit Messages](https://chris.beams.io/posts/git-commit/)

---

## Task 5 Completion Checklist

- [x] Created feature branch (`feature/goal-icons`)
- [x] Staged only relevant files
- [x] Committed with descriptive message
- [x] Pushed to remote repository
- [x] Created Pull Requests on GitHub
- [x] Submitted PR links to Forage

**Status:** ✅ Complete
