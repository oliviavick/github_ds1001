# Git & GitHub Exercises

This directory contains hands-on exercises to reinforce the concepts learned in the tutorials.

## How to Use These Exercises 📚

1. **Follow the tutorials first** - Each exercise corresponds to specific tutorial sections
2. **Practice in order** - Exercises build upon each other
3. **Don't skip steps** - Each step teaches important concepts
4. **Experiment** - Try variations of the commands you learn
5. **Ask for help** - Use GitHub Issues if you get stuck

## Exercise Structure 🗂️

```
exercises/
├── 01-setup/                 # Getting Git configured
├── 02-basic-commands/        # Your first Git commands
├── 03-staging-and-commits/   # Understanding the staging area
├── 04-viewing-history/       # Exploring Git history
├── 05-remote-repos/          # Working with GitHub
├── 06-branching/             # Creating and using branches
├── 07-merging/               # Combining branches
├── 08-collaboration/         # Working with others
└── 09-advanced/              # Advanced Git techniques
```

## Getting Started 🚀

1. **Complete the Setup:** Start with [Setup Exercise](01-setup/)
2. **Have a text editor ready:** VS Code, Sublime Text, or any editor you like
3. **Open a terminal:** Command Prompt, Git Bash, or Terminal
4. **Navigate to this directory:**
   ```bash
   cd exercises
   ```

## Exercise Guidelines 📋

### Before Each Exercise:
- [ ] Read the corresponding tutorial
- [ ] Understand the concepts being taught
- [ ] Have your terminal and text editor ready

### During Each Exercise:
- [ ] Follow instructions step by step
- [ ] Read the output of each command
- [ ] Don't copy-paste blindly - type commands yourself
- [ ] Take notes of what each command does

### After Each Exercise:
- [ ] Review what you accomplished
- [ ] Try the "Extra Credit" challenges
- [ ] Move on to the next tutorial/exercise

## Common Commands Reference 🔧

You'll use these commands frequently:

```bash
# Navigation
pwd                    # Show current directory
ls                     # List files (Mac/Linux)
dir                    # List files (Windows)
cd folder_name         # Change directory
cd ..                  # Go up one directory

# Git Basics
git init               # Initialize a repository
git status             # Check repository status
git add filename       # Stage a file
git commit -m "message" # Commit staged changes
git log                # View commit history

# Working with Remotes
git remote add origin url  # Add a remote repository
git push origin main       # Push changes to remote
git pull origin main       # Pull changes from remote
git clone url             # Clone a repository
```

## Tips for Success 💡

1. **Read error messages carefully** - They often tell you exactly what's wrong
2. **Use `git status` frequently** - It shows you what's happening
3. **Start small** - Don't try to learn everything at once
4. **Practice regularly** - A little bit each day is better than cramming
5. **Don't be afraid to make mistakes** - Git makes it hard to lose data

## Getting Help 🆘

- **Stuck on an exercise?** Check the [troubleshooting guide](../troubleshooting/)
- **Command not working?** Make sure you're in the right directory
- **Want to start over?** Most exercises include reset instructions
- **Found a bug?** [Create an issue](https://github.com/NovaVolunteer/github_ds1001/issues)

## Extra Resources 📖

- [Git Cheat Sheet](../resources/git-cheat-sheet.md)
- [Common Git Mistakes](../troubleshooting/common-mistakes.md)
- [Git Glossary](../resources/glossary.md)

---

**Ready to start? Begin with [Exercise 1: Setup](01-setup/)**

Happy practicing! 🎉