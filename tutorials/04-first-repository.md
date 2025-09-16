# Part 4: Your First Repository

**Prerequisites:** [Part 3: Setting Up Git](03-git-setup.md)

**Time:** 20-30 minutes

**Goal:** Create your first Git repository and make your first commits

## What is a Repository? 📁

A **repository** (or "repo") is a folder that Git is tracking. It contains:
- Your project files (code, documents, images, etc.)
- Git's hidden `.git` folder with all the version history
- Optional configuration files

Think of it as a "project folder with superpowers"!

## Creating Your First Repository 🚀

Let's create a simple repository to practice with.

### Step 1: Create a Project Directory

```bash
# Navigate to where you want to create your project
cd ~

# Create a new directory
mkdir my-first-repo
cd my-first-repo

# Verify you're in the right place
pwd
```

You should see a path ending in `my-first-repo`.

### Step 2: Initialize Git Repository

```bash
git init
```

**Expected Output:**
```
Initialized empty Git repository in /path/to/my-first-repo/.git/
```

🎉 Congratulations! You just created your first Git repository!

### Step 3: Explore What Happened

```bash
# Check the current status
git status
```

**Expected Output:**
```
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

```bash
# Look for hidden files (you should see .git folder)
ls -la
```

The `.git` folder is where Git stores all the version history. **Never delete this folder!**

## Adding Your First File 📝

### Step 1: Create a File

```bash
# Create a simple text file
echo "# My First Git Repository" > README.md
echo "This is my first project using Git!" >> README.md
```

Or create the file with your text editor:
```markdown
# My First Git Repository

This is my first project using Git!

## What I'm Learning
- How to initialize a Git repository
- How to add files to Git
- How to make commits
- The basics of version control

## Goals
- [ ] Make my first commit
- [ ] Understand the staging area
- [ ] Learn to write good commit messages
```

### Step 2: Check Repository Status

```bash
git status
```

**Expected Output:**
```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	README.md

nothing added to commit but untracked files present (use "git add" to track)
```

Git found your file but isn't tracking it yet!

## Understanding Git's Three Areas 🏗️

Git has three main areas:

```
Working Directory  →  Staging Area  →  Repository (.git)
     (your files)     (files ready     (committed files)
                       to commit)
```

1. **Working Directory**: Where you edit files
2. **Staging Area**: Files ready to be committed (like a "preparation area")
3. **Repository**: Permanently saved snapshots of your project

## Making Your First Commit 💾

### Step 1: Add File to Staging Area

```bash
git add README.md
```

### Step 2: Check Status Again

```bash
git status
```

**Expected Output:**
```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   README.md
```

The file is now "staged" and ready to commit!

### Step 3: Make Your First Commit

```bash
git commit -m "Add README file with project description"
```

**Expected Output:**
```
[main (root-commit) a1b2c3d] Add README file with project description
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

🎉 **You just made your first commit!** This is a permanent snapshot of your project.

### Step 4: Check Status Once More

```bash
git status
```

**Expected Output:**
```
On branch main
nothing to commit, working tree clean
```

Perfect! Everything is committed and saved.

## Writing Good Commit Messages ✍️

Your commit message should explain **what** you did and **why**:

### Good Examples:
```bash
git commit -m "Add user login functionality"
git commit -m "Fix typo in header navigation"
git commit -m "Update README with installation instructions"
git commit -m "Remove deprecated API calls"
```

### Bad Examples:
```bash
git commit -m "stuff"           # Too vague
git commit -m "fixed it"        # What did you fix?
git commit -m "asdf"           # Not descriptive
git commit -m "COMMIT"         # Useless
```

### Template for Good Messages:
```
[Action] [What you changed] [Why, if not obvious]

Examples:
Add contact form to homepage
Fix navigation menu on mobile devices
Update dependencies for security patch
Remove unused CSS classes
```

## Adding More Files 📚

Let's practice with more files:

### Step 1: Create Another File

```bash
echo "print('Hello, Git!')" > hello.py
```

### Step 2: Make Changes to README

Open `README.md` in your text editor and add:
```markdown

## Files in this project
- README.md - This description file
- hello.py - A simple Python script
```

### Step 3: Check What Changed

```bash
git status
```

You should see:
- `hello.py` as untracked (new file)
- `README.md` as modified

```bash
# See exactly what changed in README.md
git diff README.md
```

### Step 4: Stage All Changes

```bash
# Add specific files
git add README.md
git add hello.py

# Or add everything at once
git add .
```

### Step 5: Commit the Changes

```bash
git commit -m "Add Python script and update README"
```

## Viewing Your History 📖

```bash
# See all commits
git log
```

**Expected Output:**
```
commit b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f0a1b2c3
Author: Your Name <your.email@example.com>
Date:   Mon Jan 15 10:30:00 2024 -0500

    Add Python script and update README

commit a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0
Author: Your Name <your.email@example.com>
Date:   Mon Jan 15 10:15:00 2024 -0500

    Add README file with project description
```

### More Useful Log Views:

```bash
# Compact view
git log --oneline

# See what files changed
git log --stat

# Visual graph (useful with branches later)
git log --graph --oneline
```

## Quick Practice Exercise 🏃‍♂️

Try this on your own:

1. Create a file called `notes.txt`
2. Add some text about what you've learned
3. Stage the file with `git add`
4. Commit with a descriptive message
5. Check the log to see your new commit

**Solution:**
```bash
echo "I learned how to initialize a Git repository!" > notes.txt
git add notes.txt
git commit -m "Add learning notes file"
git log --oneline
```

## Common Commands Summary 📋

| Command | What it does |
|---------|-------------|
| `git init` | Initialize new repository |
| `git status` | Check repository status |
| `git add <file>` | Stage specific file |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Create commit with message |
| `git log` | View commit history |
| `git log --oneline` | Compact commit history |

## Troubleshooting 🔧

### "fatal: not a git repository"
- Make sure you ran `git init`
- Check you're in the right directory

### "nothing to commit"
- You haven't made any changes
- Or changes aren't staged (run `git add`)

### "Please tell me who you are"
- Set your name and email (review [Part 3](03-git-setup.md))

### Can't see .git folder
- It's hidden. Use `ls -la` to see hidden files
- On Windows, enable "Show hidden files"

## What You've Learned 🎓

- ✅ How to create a Git repository with `git init`
- ✅ The difference between working directory, staging area, and repository
- ✅ How to add files with `git add`
- ✅ How to make commits with `git commit`
- ✅ How to write good commit messages
- ✅ How to view project history with `git log`
- ✅ Basic Git workflow: edit → add → commit

## What's Next? ➡️

Great job! You now understand the fundamental Git workflow. Next, we'll dive deeper into Git commands and learn about viewing differences between versions.

**[Continue to Part 5: Basic Git Commands](05-basic-commands.md)**

---

## Practice Checklist ✅

Before moving on, make sure you can:

- [ ] Create a new Git repository from scratch
- [ ] Add files to the staging area
- [ ] Make commits with descriptive messages
- [ ] View your commit history
- [ ] Understand what `git status` is telling you

**Previous:** [Part 3: Setting Up Git](03-git-setup.md) | **Next:** [Part 5: Basic Git Commands](05-basic-commands.md)