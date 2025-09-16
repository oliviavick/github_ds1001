# Git & GitHub Troubleshooting Guide

Don't panic! Git problems are usually easy to fix once you know what to look for. This guide covers the most common issues students encounter.

## 🚨 Before You Start

**The Golden Rule:** Git makes it very hard to lose data permanently. Most "disasters" can be fixed!

**Always check these first:**
1. Run `git status` to see what Git thinks is happening
2. Make sure you're in the right directory (`pwd`)
3. Check if you're in a Git repository (`ls -la` should show `.git` folder)

## Common Problems & Solutions 🔧

### 1. "git: command not found"

**Problem:** Git isn't installed or not in your PATH.

**Solutions:**
```bash
# Check if Git is installed
git --version

# If not installed, reinstall Git:
# Windows: Download from git-scm.com
# Mac: brew install git
# Linux: sudo apt install git (Ubuntu) or sudo yum install git (CentOS)
```

**On Windows:** Make sure you're using Git Bash, not Command Prompt.

### 2. "fatal: not a git repository"

**Problem:** You're trying to run Git commands outside a Git repository.

**Solutions:**
```bash
# Check if you're in a Git repo
ls -la
# Look for .git folder

# If no .git folder, either:
# Initialize a new repo:
git init

# Or navigate to an existing repo:
cd path/to/your/git/repo
```

### 3. "Please tell me who you are"

**Problem:** Git doesn't know your name and email.

**Solution:**
```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"

# Verify it worked:
git config user.name
git config user.email
```

### 4. "nothing to commit, working tree clean"

**Problem:** You haven't made any changes, or changes aren't staged.

**Solutions:**
```bash
# Check what's happening:
git status

# If you made changes but they're not showing:
# 1. Make sure you saved your files
# 2. Check if you're in the right directory
# 3. Add files to staging area:
git add filename
# or
git add .
```

### 5. "fatal: refusing to merge unrelated histories"

**Problem:** Trying to merge or pull from a repository with different history.

**Solution:**
```bash
# Allow the merge:
git pull origin main --allow-unrelated-histories

# Or when merging:
git merge branch-name --allow-unrelated-histories
```

### 6. Merge Conflicts

**Problem:** Git can't automatically merge changes.

**Solution:**
1. **Don't panic!** Conflicts are normal in collaboration.
2. Open the conflicted files in your text editor.
3. Look for conflict markers:
   ```
   <<<<<<< HEAD
   Your changes
   =======
   Their changes
   >>>>>>> branch-name
   ```
4. Edit the file to keep what you want.
5. Remove the conflict markers.
6. Save the file.
7. Add and commit:
   ```bash
   git add filename
   git commit -m "Resolve merge conflict in filename"
   ```

### 7. "detached HEAD state"

**Problem:** You're not on a branch.

**Solutions:**
```bash
# Check where you are:
git status

# Create a new branch from current position:
git checkout -b new-branch-name

# Or go back to main branch:
git checkout main
```

### 8. "Permission denied (publickey)"

**Problem:** SSH key authentication failing with GitHub.

**Solutions:**
```bash
# Check if SSH key exists:
ls ~/.ssh

# Generate new SSH key if needed:
ssh-keygen -t ed25519 -C "your.email@example.com"

# Add key to SSH agent:
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Copy public key and add to GitHub:
cat ~/.ssh/id_ed25519.pub
# Copy the output and add to GitHub Settings > SSH Keys

# Test connection:
ssh -T git@github.com
```

**Alternative:** Use HTTPS instead of SSH:
```bash
git remote set-url origin https://github.com/username/repo.git
```

### 9. "fatal: remote origin already exists"

**Problem:** Trying to add a remote that already exists.

**Solutions:**
```bash
# Check existing remotes:
git remote -v

# Update existing remote:
git remote set-url origin https://github.com/username/repo.git

# Or remove and re-add:
git remote remove origin
git remote add origin https://github.com/username/repo.git
```

### 10. "Updates were rejected"

**Problem:** Your local branch is behind the remote branch.

**Solution:**
```bash
# Pull the latest changes first:
git pull origin main

# Then push:
git push origin main

# If that doesn't work, you might need to force push (be careful!):
git push origin main --force-with-lease
```

## Emergency Fixes 🚑

### "I committed to the wrong branch!"

```bash
# Copy the commit hash from git log
git log --oneline

# Switch to correct branch
git checkout correct-branch

# Cherry-pick the commit
git cherry-pick commit-hash

# Go back to wrong branch and reset
git checkout wrong-branch
git reset --hard HEAD~1
```

### "I need to undo my last commit!"

```bash
# Undo commit but keep changes:
git reset --soft HEAD~1

# Undo commit and lose changes:
git reset --hard HEAD~1

# Already pushed? Create a new commit that undoes it:
git revert HEAD
```

### "I accidentally deleted important files!"

```bash
# If you haven't committed yet:
git checkout -- filename

# If it was committed before:
git log --oneline
git checkout commit-hash -- filename
```

### "My repository is completely messed up!"

```bash
# Nuclear option - start fresh but keep your files:
# 1. Backup your important files
cp -r important-files /tmp/backup

# 2. Remove .git folder
rm -rf .git

# 3. Start over
git init
git add .
git commit -m "Fresh start"

# 4. Restore any backed up files if needed
```

## Prevention Tips 🛡️

### Before Making Changes:
- [ ] Run `git status` to see current state
- [ ] Make sure you're on the right branch
- [ ] Pull latest changes: `git pull origin main`

### Good Practices:
- [ ] Commit often with small, logical changes
- [ ] Write descriptive commit messages
- [ ] Test your changes before committing
- [ ] Use branches for new features
- [ ] Don't force push to shared branches

### Safety Commands:
```bash
# Always check status first
git status

# See what will be committed
git diff --staged

# See commit history
git log --oneline

# Check which branch you're on
git branch
```

## Getting More Help 🆘

### Built-in Help:
```bash
git help <command>    # Detailed help for specific command
git <command> --help  # Same as above
git help             # List all commands
```

### Useful Commands for Debugging:
```bash
git status           # Current repository state
git log --oneline    # Commit history
git remote -v        # List remote repositories
git branch -a        # List all branches
git config --list    # Show all configuration
```

### Online Resources:
- [Official Git Documentation](https://git-scm.com/doc)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [GitHub Help](https://help.github.com/)
- [Stack Overflow Git Questions](https://stackoverflow.com/questions/tagged/git)

### When to Ask for Help:
- You've tried the solutions above
- You're not sure what a command will do
- You're worried about losing important work
- The error message doesn't match anything here

## Common Error Messages Dictionary 📖

| Error Message | What It Means | Quick Fix |
|---------------|---------------|-----------|
| `fatal: not a git repository` | Not in a Git repo | `cd` to repo or `git init` |
| `nothing to commit` | No changes to save | Make changes or `git add` files |
| `Please tell me who you are` | Name/email not set | `git config` commands |
| `Permission denied` | Authentication issue | Check SSH keys or use HTTPS |
| `merge conflict` | Files conflict | Edit files, remove markers, commit |
| `detached HEAD` | Not on a branch | `git checkout main` |
| `Updates were rejected` | Local behind remote | `git pull` then `git push` |

---

**Remember:** The Git community is very helpful! Don't hesitate to ask questions on forums, Stack Overflow, or create an issue in this repository.

**Most importantly:** Git is designed to be safe. You can experiment and learn without fear of losing your work permanently.