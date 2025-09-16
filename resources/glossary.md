# Git & GitHub Glossary

A comprehensive list of Git and GitHub terms every student should know. Terms are organized by category and difficulty level.

## 🔤 Basic Terms (Start Here)

### Repository (Repo)
A folder that contains your project files and the complete history of all changes. Think of it as a "project folder with superpowers."

### Commit
A saved snapshot of your project at a specific point in time. Like taking a photo of your project that you can always go back to.

### Staging Area (Index)
A preparation area where files wait before being committed. Files here are ready to be saved to the repository.

### Working Directory
The folder on your computer where you edit files. This is where you make changes before staging and committing them.

### Git
The version control system that tracks changes to your files over time.

### GitHub
A website that hosts Git repositories online, making it easy to share code and collaborate with others.

## 📁 File and Change States

### Tracked
Files that Git knows about and is monitoring for changes.

### Untracked  
New files that Git doesn't know about yet. You need to `git add` them to start tracking.

### Modified
Files that have been changed since the last commit but aren't staged yet.

### Staged
Files that have been added to the staging area and are ready to be committed.

### Committed
Files that have been permanently saved to the repository with a commit.

### Clean Working Tree
When there are no changes to commit - everything is saved and up to date.

## 🌿 Branching Terms

### Branch
A parallel version of your project. Like creating a copy to work on features without affecting the main version.

### Main/Master Branch
The primary branch of your repository. Usually contains the stable, production-ready code.

### HEAD
A pointer that shows which commit you're currently on. Usually points to the latest commit on your current branch.

### Merge
Combining changes from one branch into another branch.

### Merge Conflict
When Git can't automatically combine changes from different branches because they modify the same parts of a file.

### Fast-Forward Merge
A merge where Git can simply move the branch pointer forward because there are no conflicting changes.

## 🌐 Remote Repository Terms

### Remote
A version of your repository that's stored somewhere else (like on GitHub).

### Origin
The default name for the main remote repository (usually where you cloned from).

### Clone
Making a complete copy of a repository from a remote source to your local computer.

### Fork
Creating your own copy of someone else's repository on GitHub.

### Push
Sending your local commits to a remote repository.

### Pull
Getting the latest changes from a remote repository and merging them into your local branch.

### Fetch
Downloading changes from a remote repository without merging them (like "check for updates").

## 🔄 Advanced Operations

### Rebase
Rewriting commit history by moving commits to a new base. Makes history cleaner but can be dangerous.

### Cherry-pick
Applying a specific commit from one branch to another branch.

### Stash
Temporarily saving your current changes without committing them.

### Reset
Moving your branch pointer to a different commit, potentially undoing changes.

### Revert
Creating a new commit that undoes the changes from a previous commit.

### Squash
Combining multiple commits into a single commit.

## 📊 GitHub-Specific Terms

### Pull Request (PR)
A request to merge your changes into another branch or repository. Includes discussion and code review.

### Issue
A way to track bugs, feature requests, or other tasks in a GitHub repository.

### Release
A packaged version of your software at a specific point in time, often with version numbers.

### GitHub Pages
Free web hosting for static websites directly from your GitHub repository.

### Actions
GitHub's automation platform for running code, tests, and deployments.

### Gist
A simple way to share code snippets or small files on GitHub.

## 🔧 Command Categories

### Setup Commands
Commands for configuring Git and initializing repositories:
- `git config` - Set up your identity and preferences
- `git init` - Create a new repository
- `git clone` - Copy a repository

### Basic Workflow Commands  
Daily commands for tracking changes:
- `git status` - Check what's happening
- `git add` - Stage files for commit
- `git commit` - Save changes permanently
- `git log` - View history

### Branching Commands
Commands for working with branches:
- `git branch` - List, create, or delete branches
- `git checkout` / `git switch` - Change branches
- `git merge` - Combine branches

### Remote Commands
Commands for working with remote repositories:
- `git remote` - Manage remote connections
- `git push` - Send changes to remote
- `git pull` - Get changes from remote
- `git fetch` - Download remote changes

## 🎯 Common Abbreviations

| Abbreviation | Full Term | Meaning |
|--------------|-----------|---------|
| **PR** | Pull Request | Request to merge changes |
| **Repo** | Repository | Project folder with Git |
| **Commit** | Commit | Save changes (also used as noun) |
| **Diff** | Difference | Changes between versions |
| **CLI** | Command Line Interface | Terminal/command prompt |
| **GUI** | Graphical User Interface | Visual Git tools |
| **SHA** | Secure Hash Algorithm | Unique commit identifier |
| **URL** | Uniform Resource Locator | Web address for repository |

## 📝 File Types in Git Context

### .gitignore
A file that tells Git which files to ignore (not track).

### README.md
A documentation file (usually Markdown) that describes your project.

### LICENSE
A file that specifies how others can use your code.

### .git/
Hidden folder containing all Git data and history. **Never delete this!**

## 🆘 Error Message Terms

### "fatal: not a git repository"
You're trying to use Git commands outside a Git repository.

### "nothing to commit, working tree clean"  
No changes have been made since the last commit.

### "merge conflict"
Git couldn't automatically combine changes and needs your help.

### "detached HEAD state"
You're not on a branch - you're looking at a specific commit.

### "up to date"
Your local repository has all the latest changes from the remote.

## 💡 Conceptual Terms

### Version Control
A system for tracking changes to files over time.

### Distributed Version Control
A system where every copy of the repository contains the complete history.

### Snapshot
A complete picture of your project at a specific point in time (what commits store).

### History
The complete record of all changes made to a repository over time.

### Workflow
A set of steps or processes for using Git effectively in a team or project.

### Collaboration
Working together with others on the same codebase using Git and GitHub.

## 🎓 Learning Progression

### Beginner Level
Start with these terms:
- Repository, Commit, Branch, Remote
- Add, Commit, Push, Pull
- Working Directory, Staging Area
- GitHub, Clone, Fork

### Intermediate Level
Learn these next:
- Merge, Conflict, Pull Request
- Reset, Revert, Stash
- Origin, Upstream, Tracking
- Issues, Releases, Actions

### Advanced Level
Master these concepts:
- Rebase, Cherry-pick, Squash
- HEAD, Detached HEAD, Reflog
- Hooks, Submodules, Worktrees
- Complex branching strategies

## 🔍 How to Use This Glossary

1. **While Reading Tutorials**: Look up unfamiliar terms as you encounter them
2. **Before Exercises**: Review relevant terms for what you're about to practice
3. **During Troubleshooting**: Understand error messages and their meanings
4. **For Reference**: Bookmark this page for quick lookups

## 📚 Related Resources

- [Git Cheat Sheet](git-cheat-sheet.md) - Quick command reference
- [Troubleshooting Guide](../troubleshooting/README.md) - Common problems and solutions
- [Official Git Glossary](https://git-scm.com/docs/gitglossary) - Comprehensive technical definitions

---

**💡 Pro Tip:** Don't try to memorize everything at once! Refer back to this glossary as you learn and practice. The terms will become natural with use.

*This glossary grows with the community. Suggest additions by [creating an issue](https://github.com/NovaVolunteer/github_ds1001/issues)!*