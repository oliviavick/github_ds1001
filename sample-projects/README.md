# Sample Projects for Git Practice

This directory contains sample projects that you can use to practice Git and GitHub skills. Each project is designed to teach specific concepts while working with realistic scenarios.

## Available Projects 🚀

### 1. [Personal Website](personal-website/)
**Concepts:** Basic Git workflow, HTML/CSS changes, commit messages
**Difficulty:** Beginner
**What you'll learn:**
- Making your first commits
- Tracking changes to files
- Writing good commit messages
- Basic branching

### 2. [Recipe Collection](recipe-collection/)
**Concepts:** Collaboration, merge conflicts, branching strategies
**Difficulty:** Intermediate  
**What you'll learn:**
- Working with multiple contributors
- Resolving merge conflicts
- Feature branch workflow
- Pull requests

### 3. [Todo App](todo-app/)
**Concepts:** Advanced workflows, releases, GitHub Actions
**Difficulty:** Advanced
**What you'll learn:**
- Gitflow workflow
- Tagging and releases
- GitHub Actions basics
- Code reviews

## How to Use These Projects 📚

### For Individual Practice:
1. **Choose a project** based on your skill level
2. **Copy the project** to your practice directory
3. **Initialize Git** in the project directory
4. **Follow the project instructions** to practice specific Git skills

### For Group Practice:
1. **Fork this repository** to your GitHub account
2. **Each team member clones** the fork
3. **Work on different features** simultaneously
4. **Practice collaboration** through pull requests

## Project Structure 🗂️

Each project includes:
- `README.md` - Project overview and Git exercises
- `INSTRUCTIONS.md` - Step-by-step Git practice instructions
- Project files - Actual code/content to work with
- `SOLUTIONS.md` - Solutions to common problems (spoiler alert!)

## Getting Started 🏃‍♀️

### Option 1: Copy to Practice Directory
```bash
# Navigate to your Git practice area
cd ~/git-practice

# Copy a sample project
cp -r /path/to/github_ds1001/sample-projects/personal-website ./my-website
cd my-website

# Initialize Git and start practicing
git init
git add .
git commit -m "Initial commit"
```

### Option 2: Fork and Clone
1. Fork this repository on GitHub
2. Clone your fork:
   ```bash
   git clone https://github.com/yourusername/github_ds1001.git
   cd github_ds1001/sample-projects
   ```
3. Choose a project and start the exercises

## Practice Scenarios 🎭

### Scenario 1: Solo Developer
Practice the basics:
- Initialize repositories
- Make commits
- View history
- Create branches
- Merge changes

### Scenario 2: Team Collaboration
Simulate team work:
- Multiple people working on same project
- Feature branches
- Pull requests
- Code reviews
- Merge conflicts

### Scenario 3: Open Source Contribution
Learn open source workflows:
- Fork repositories
- Create feature branches
- Submit pull requests
- Respond to feedback

## Tips for Success 💡

1. **Start Simple:** Begin with the personal website project
2. **Read Instructions Carefully:** Each project has specific learning goals
3. **Don't Rush:** Take time to understand each Git command
4. **Experiment:** Try variations of the suggested commands
5. **Use Git Status:** Check `git status` frequently to understand what's happening
6. **Make Mistakes:** It's okay! Git makes it hard to lose data permanently

## Common Practice Patterns 🔄

### The Basic Cycle:
```bash
# Make changes to files
# Check what changed
git status
git diff

# Stage changes
git add filename
# or git add .

# Commit changes
git commit -m "Descriptive message"

# Repeat!
```

### The Branch Cycle:
```bash
# Create and switch to new branch
git checkout -b feature-name

# Make changes and commits
# ... work work work ...

# Switch back to main
git checkout main

# Merge your feature
git merge feature-name
```

## Project Difficulty Guide 📊

| Project | Git Concepts | Time | Prerequisites |
|---------|--------------|------|---------------|
| **Personal Website** | init, add, commit, log | 1-2 hours | Tutorial 1-4 |
| **Recipe Collection** | branches, merge, conflicts | 2-3 hours | Tutorial 1-8 |
| **Todo App** | workflows, releases, actions | 3-4 hours | Tutorial 1-12 |

## What You'll Build 🛠️

### Personal Website
A simple HTML/CSS website where you'll practice:
- Adding new pages
- Updating content
- Fixing bugs
- Creating feature branches

### Recipe Collection
A markdown-based recipe collection where you'll practice:
- Collaborative editing
- Merge conflict resolution
- Organizing with branches
- Pull request workflow

### Todo App
A JavaScript todo application where you'll practice:
- Advanced Git workflows
- Release management
- Automated testing
- Deployment strategies

## Need Help? 🆘

- **Stuck on a project?** Check the `SOLUTIONS.md` file in each project
- **Git command not working?** Review the corresponding tutorial
- **Want to reset?** Each project includes reset instructions
- **Found a bug?** [Create an issue](https://github.com/NovaVolunteer/github_ds1001/issues)

---

**Ready to start practicing? Choose your first project below!**

- 🌟 [Personal Website](personal-website/) (Beginner)
- 🍳 [Recipe Collection](recipe-collection/) (Intermediate)  
- ✅ [Todo App](todo-app/) (Advanced)