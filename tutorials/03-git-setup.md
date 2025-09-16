# Part 3: Setting Up Git

Time to get Git installed and configured on your computer! Don't worry—this is easier than it looks.

## Installing Git 💻

### Windows 🪟

**Option 1: Official Git for Windows**
1. Go to [git-scm.com](https://git-scm.com/)
2. Click "Download for Windows"
3. Run the installer with default settings
4. This includes Git Bash (a terminal for Git commands)

**Option 2: GitHub Desktop (Beginner-Friendly)**
1. Go to [desktop.github.com](https://desktop.github.com/)
2. Download and install
3. Includes Git automatically + nice visual interface

### Mac 🍎

**Option 1: Homebrew (Recommended)**
```bash
# Install Homebrew first if you don't have it
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Git
brew install git
```

**Option 2: Xcode Command Line Tools**
```bash
xcode-select --install
```

**Option 3: Official Installer**
1. Go to [git-scm.com](https://git-scm.com/)
2. Download Mac version
3. Install normally

### Linux 🐧

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install git
```

**CentOS/RHEL/Fedora:**
```bash
# CentOS/RHEL
sudo yum install git

# Fedora
sudo dnf install git
```

## Verify Installation ✅

Open your terminal/command prompt and type:

```bash
git --version
```

You should see something like:
```
git version 2.40.0
```

If you see this, congratulations! Git is installed! 🎉

## Initial Configuration ⚙️

Git needs to know who you are before you can make commits. Let's set that up:

### Set Your Name and Email

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```

**Important:** Use the same email address you'll use for GitHub!

### Example:
```bash
git config --global user.name "Alex Smith"
git config --global user.email "alex.smith@email.com"
```

### Set Your Default Branch Name

Modern Git uses `main` instead of `master`:

```bash
git config --global init.defaultBranch main
```

### Set Your Text Editor (Optional)

Git sometimes opens a text editor. Set your preference:

```bash
# Visual Studio Code
git config --global core.editor "code --wait"

# Nano (simple, built-in)
git config --global core.editor "nano"

# Vim
git config --global core.editor "vim"
```

## Verify Your Configuration 🔍

Check that everything is set up correctly:

```bash
git config --list --global
```

You should see:
```
user.name=Your Full Name
user.email=your.email@example.com
init.defaultbranch=main
core.editor=code --wait
```

Or check individual settings:
```bash
git config user.name
git config user.email
```

## SSH Keys (For GitHub) 🔑

SSH keys let you connect to GitHub securely without typing your password every time.

### Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```

When prompted:
- **File location**: Press Enter (use default)
- **Passphrase**: Optional, but recommended for security

### Start SSH Agent

**Windows (Git Bash):**
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

**Mac/Linux:**
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Copy Your Public Key

**Windows:**
```bash
clip < ~/.ssh/id_ed25519.pub
```

**Mac:**
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

**Linux:**
```bash
cat ~/.ssh/id_ed25519.pub
# Then copy the output manually
```

### Add Key to GitHub

1. Go to [GitHub.com](https://github.com)
2. Click your profile picture → **Settings**
3. Click **SSH and GPG keys**
4. Click **New SSH key**
5. Paste your key and give it a title
6. Click **Add SSH key**

### Test SSH Connection

```bash
ssh -T git@github.com
```

You should see:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

## Useful Git Aliases 🎯

Make Git commands shorter and easier:

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual '!gitk'
```

Now you can type `git st` instead of `git status`!

## Command Line Tips 💡

### Windows Users
- Use **Git Bash** for Git commands (comes with Git for Windows)
- It provides a Linux-like terminal experience

### All Users
- Learn these terminal basics:
  - `pwd` - show current directory
  - `ls` (Mac/Linux) or `dir` (Windows) - list files
  - `cd folder_name` - change directory
  - `cd ..` - go up one directory
  - `mkdir folder_name` - create directory

## Troubleshooting 🔧

### "git: command not found"
- Git isn't installed or not in your PATH
- Restart your terminal after installation
- On Windows, use Git Bash

### "Permission denied (publickey)"
- SSH key isn't set up correctly
- Make sure you added the public key to GitHub
- Check that ssh-agent is running

### "fatal: unable to access..."
- Network/firewall issues
- Try HTTPS instead of SSH initially

## Text Editors for Git 📝

You'll need a text editor for commit messages and file editing:

### Beginner-Friendly:
- **Visual Studio Code**: Free, powerful, great Git integration
- **Sublime Text**: Fast and simple
- **Atom**: GitHub's editor (discontinued but still works)

### Terminal-Based:
- **Nano**: Simple, built into most systems
- **Vim**: Powerful but steep learning curve
- **Emacs**: Feature-rich, complex

## What's Next? ➡️

Great! Git is now installed and configured. Time to create your first repository!

**[Continue to Part 4: Your First Repository](04-first-repository.md)**

---

## Checklist ✅

Before moving on, make sure you can:

- [ ] Run `git --version` and see a version number
- [ ] Run `git config user.name` and see your name
- [ ] Run `git config user.email` and see your email
- [ ] (Optional) Connect to GitHub via SSH

**Previous:** [Part 2: Why Use Git?](02-why-git.md) | **Next:** [Part 4: Your First Repository](04-first-repository.md)