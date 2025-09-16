# Git Command Cheat Sheet

Quick reference for the most commonly used Git commands. Bookmark this page for easy access!

## 🚀 Getting Started

### Setup Commands
```bash
# Configure your identity
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check your configuration
git config --list

# Get help
git help <command>
```

### Initialize Repository
```bash
# Create new repository
git init

# Clone existing repository
git clone <url>
git clone <url> <directory-name>
```

## 📁 Basic Workflow

### Check Status and Changes
```bash
# See repository status
git status

# See changes in files
git diff                    # Changes not staged
git diff --staged          # Changes staged for commit
git diff HEAD              # All changes since last commit
```

### Staging and Committing
```bash
# Add files to staging area
git add <filename>         # Add specific file
git add .                  # Add all files in current directory
git add -A                 # Add all changes (including deletions)

# Remove from staging area
git reset <filename>       # Unstage specific file
git reset                  # Unstage all files

# Commit changes
git commit -m "Your message"
git commit -am "Add and commit in one step"
```

## 📊 Viewing History

### Log Commands
```bash
# View commit history
git log                    # Full log
git log --oneline         # Compact log
git log --graph           # Show branching graph
git log --author="Name"   # Filter by author
git log -n 5              # Show last 5 commits

# Show specific commit
git show <commit-hash>
```

## 🌿 Branching

### Branch Operations
```bash
# List branches
git branch                 # Local branches
git branch -a             # All branches (local + remote)

# Create branch
git branch <branch-name>

# Switch branches
git checkout <branch-name>
git switch <branch-name>   # Newer command

# Create and switch in one step
git checkout -b <branch-name>
git switch -c <branch-name>

# Delete branch
git branch -d <branch-name>        # Safe delete
git branch -D <branch-name>        # Force delete
```

### Merging
```bash
# Merge branch into current branch
git merge <branch-name>

# Merge without fast-forward
git merge --no-ff <branch-name>

# Abort merge
git merge --abort
```

## 🌐 Remote Repositories

### Remote Operations
```bash
# Add remote
git remote add origin <url>

# List remotes
git remote -v

# Change remote URL
git remote set-url origin <new-url>

# Remove remote
git remote remove <remote-name>
```

### Push and Pull
```bash
# Push to remote
git push origin <branch-name>
git push origin main              # Push main branch
git push -u origin <branch-name>  # Set upstream

# Pull from remote
git pull origin <branch-name>
git pull                          # Pull current branch

# Fetch (download without merging)
git fetch origin
```

## 🔄 Undoing Changes

### Working Directory
```bash
# Discard changes in working directory
git checkout -- <filename>
git restore <filename>            # Newer command

# Discard all changes
git checkout -- .
git restore .
```

### Staging Area
```bash
# Unstage files
git reset <filename>
git restore --staged <filename>   # Newer command
```

### Commits
```bash
# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Create new commit that undoes previous one
git revert <commit-hash>

# Modify last commit
git commit --amend -m "New message"
```

## 🏷️ Tags

### Tag Operations
```bash
# Create tag
git tag <tag-name>
git tag -a <tag-name> -m "Tag message"

# List tags
git tag

# Push tags
git push origin <tag-name>
git push origin --tags           # Push all tags

# Delete tag
git tag -d <tag-name>            # Local
git push origin --delete <tag-name> # Remote
```

## 🔍 Searching and Finding

### Search Commands
```bash
# Search in files
git grep "search-term"

# Find when line was changed
git blame <filename>

# Find commits that contain string
git log --grep="search-term"

# Show files in commit
git diff-tree --no-commit-id --name-only -r <commit-hash>
```

## ⚙️ Configuration

### Useful Configurations
```bash
# Set default branch name
git config --global init.defaultBranch main

# Set default editor
git config --global core.editor "code --wait"

# Useful aliases
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual '!gitk'
```

## 🔧 Advanced Commands

### Stashing
```bash
# Save current work temporarily
git stash
git stash push -m "Work in progress"

# List stashes
git stash list

# Apply stash
git stash apply                   # Keep stash
git stash pop                     # Apply and remove

# Drop stash
git stash drop
```

### Cherry-picking
```bash
# Apply commit from another branch
git cherry-pick <commit-hash>
```

### Rebasing
```bash
# Rebase current branch onto another
git rebase <branch-name>

# Interactive rebase (edit history)
git rebase -i HEAD~3

# Continue/abort rebase
git rebase --continue
git rebase --abort
```

## 📋 Quick Reference Tables

### File States
| Command | Working Dir | Staging Area | Repository |
|---------|------------|--------------|------------|
| `git add` | ← | → | |
| `git commit` | | ← | → |
| `git checkout` | → | | ← |
| `git reset --soft` | | → | ← |
| `git reset --mixed` | → | ← | ← |
| `git reset --hard` | ← | ← | ← |

### Common Workflows
| Scenario | Commands |
|----------|----------|
| **Start new feature** | `git checkout -b feature-name` |
| **Save progress** | `git add .` → `git commit -m "message"` |
| **Switch context** | `git stash` → `git checkout other-branch` |
| **Finish feature** | `git checkout main` → `git merge feature-name` |
| **Get latest changes** | `git pull origin main` |
| **Share your work** | `git push origin branch-name` |

## 🆘 Emergency Commands

### When Things Go Wrong
```bash
# "I messed up the working directory"
git checkout -- .

# "I staged the wrong files"
git reset

# "I committed the wrong thing"
git reset --soft HEAD~1

# "I pushed broken code"
git revert HEAD
git push origin main

# "Everything is broken"
git reflog                        # Find where to go back to
git reset --hard <commit-hash>    # Go back to working state
```

## 💡 Pro Tips

1. **Use `git status` frequently** - It tells you exactly what to do next
2. **Read Git's output** - It usually tells you how to fix problems  
3. **Commit early and often** - Small commits are easier to understand
4. **Write good commit messages** - Your future self will thank you
5. **Use branches for features** - Keep main branch stable
6. **Pull before you push** - Avoid conflicts
7. **Don't force push to shared branches** - You'll make teammates sad

## 📱 Quick Commands for Mobile/Small Screens

Essential commands when space is limited:
```bash
git status
git add .
git commit -m "msg"
git push
git pull
git log --oneline
git checkout -b branch
git merge branch
```

---

**Save this cheat sheet!** Print it out or bookmark it for quick reference while learning Git.

*For more detailed explanations, refer back to the [tutorials](../tutorials/) in this repository.*