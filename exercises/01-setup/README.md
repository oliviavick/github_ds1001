# Exercise 1: Git Setup

**Prerequisites:** Complete [Tutorial 3: Setting Up Git](../../tutorials/03-git-setup.md)

**Time:** 15-20 minutes

**Goal:** Verify your Git installation and configuration

## Part A: Verify Installation ✅

### Step 1: Check Git Version
Open your terminal and run:

```bash
git --version
```

**Expected Output:** Something like `git version 2.40.0`

**If you see an error:**
- Git isn't installed - go back to [Tutorial 3](../../tutorials/03-git-setup.md)
- On Windows, make sure you're using Git Bash

### Step 2: Check Your Configuration
Run these commands and verify the output:

```bash
git config user.name
git config user.email
```

**Expected Output:**
- Your full name
- Your email address

**If these are empty or wrong:**
```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```

### Step 3: Check All Global Config
```bash
git config --list --global
```

Look through the output - you should see your name and email at minimum.

## Part B: Create a Practice Directory 📁

### Step 1: Navigate to Your Home Directory
```bash
# Windows
cd /c/Users/YourUsername

# Mac
cd ~

# Linux
cd ~
```

### Step 2: Create a Git Practice Directory
```bash
mkdir git-practice
cd git-practice
```

### Step 3: Verify You're in the Right Place
```bash
pwd
```

You should see a path ending in `git-practice`.

## Part C: Test Basic Git Commands 🧪

### Step 1: Try Git Status (Should Fail)
```bash
git status
```

**Expected Output:** 
```
fatal: not a git repository (or any of the parent directories): .git
```

This is correct! We haven't initialized a Git repository yet.

### Step 2: Get Help
```bash
git --help
```

This should show you a list of common Git commands. Press `q` to quit if it opens in a pager.

### Step 3: Get Help for a Specific Command
```bash
git help status
```

This opens documentation for the `git status` command. Look around, then close it.

## Part D: SSH Setup (Optional but Recommended) 🔑

Only do this if you plan to use GitHub.

### Step 1: Check if You Have SSH Keys
```bash
ls ~/.ssh
```

Look for files named `id_ed25519` and `id_ed25519.pub` (or `id_rsa` and `id_rsa.pub`).

### Step 2: Generate SSH Key (if needed)
If you don't have SSH keys:

```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```

Press Enter for all prompts to use defaults (or set a passphrase if you want).

### Step 3: Test SSH (if you've added the key to GitHub)
```bash
ssh -T git@github.com
```

**Expected Output (if set up):**
```
Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.
```

## Verification Checklist ✅

Before moving on, make sure you can complete all of these:

- [ ] `git --version` shows a version number
- [ ] `git config user.name` shows your name
- [ ] `git config user.email` shows your email
- [ ] You have a `git-practice` directory
- [ ] `pwd` shows you're in the `git-practice` directory
- [ ] `git status` gives you an error (because it's not a Git repo yet)

## Troubleshooting 🔧

### Problem: "git: command not found"
**Solution:** Git isn't installed or isn't in your PATH
- Reinstall Git
- Restart your terminal
- On Windows, use Git Bash

### Problem: Name/email not set
**Solution:** Run the configuration commands:
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### Problem: Can't create directory
**Solution:** Permission issues
- Make sure you're in your home directory
- Try a different location like Desktop

### Problem: SSH not working
**Solution:** This is optional for now
- You can use HTTPS instead
- We'll cover SSH more later

## Extra Credit 🌟

Try these additional tasks:

1. **Explore Git Help:**
   ```bash
   git help log
   git help commit
   git help push
   ```

2. **Set Up Aliases:**
   ```bash
   git config --global alias.st status
   git config --global alias.co checkout
   git config --global alias.br branch
   ```

3. **Check Your Configuration:**
   ```bash
   git config --list --global
   ```

## What You Learned 🎓

- How to verify Git is installed and configured
- Basic terminal navigation
- How to get help with Git commands
- How to set up a practice directory
- (Optional) SSH key setup basics

## What's Next? ➡️

Great job! Your Git setup is complete. Now let's create your first Git repository!

**[Continue to Exercise 2: Basic Commands](../02-basic-commands/)**

---

**Need Help?** 
- Check the [troubleshooting guide](../../troubleshooting/)
- [Create an issue](https://github.com/NovaVolunteer/github_ds1001/issues) if you're stuck