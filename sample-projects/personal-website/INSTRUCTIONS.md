# Personal Website Git Exercises

**Prerequisites:** Complete [Tutorials 1-4](../../tutorials/)

**Time:** 1-2 hours

**Goal:** Practice fundamental Git concepts by building and improving a personal website

## 🎯 What You'll Practice

- Initializing a Git repository
- Making meaningful commits
- Working with the staging area
- Viewing project history
- Creating and merging branches
- Writing good commit messages

## 🚀 Getting Started

### Option 1: Copy Files to Your Practice Area
```bash
# Navigate to your practice directory
cd ~/git-practice

# Copy the personal website project
cp -r /path/to/github_ds1001/sample-projects/personal-website ./my-website
cd my-website

# Remove any existing .git folder to start fresh
rm -rf .git
```

### Option 2: Work Directly in the Repository
```bash
# Navigate to the project
cd sample-projects/personal-website

# Remove .git to start fresh (if it exists)
rm -rf .git
```

## Exercise 1: Repository Setup 📁

### Step 1: Initialize the Repository
```bash
# Initialize Git in your project directory
git init

# Check the status
git status
```

**Expected Output:**
```
On branch main
No commits yet
Untracked files:
  (multiple files listed)
```

### Step 2: Examine the Project Files
```bash
# List all files
ls -la

# Look at the main HTML file
cat index.html

# Check the CSS file
cat styles.css
```

**What you should see:**
- HTML files for different pages
- A CSS file for styling
- This instruction file

### Step 3: Stage All Files
```bash
# Add all files to staging area
git add .

# Check status
git status
```

### Step 4: Make Your First Commit
```bash
git commit -m "Initial commit: Add basic website structure"

# Verify the commit
git log --oneline
```

**✅ Success Check:** You should see one commit in your log.

## Exercise 2: Personalizing Content 🎨

### Step 1: Update the Homepage
Open `index.html` in your text editor and make these changes:

1. Replace "Your Name" with your actual name
2. Update the hero section with information about yourself  
3. Modify the "About Me" section to reflect your interests
4. Add items to the "What I'm Working On" list

### Step 2: Check What Changed
```bash
# See which files were modified
git status

# See exactly what changed
git diff index.html
```

### Step 3: Stage and Commit Your Changes
```bash
# Stage the file
git add index.html

# Commit with a descriptive message
git commit -m "Personalize homepage with my information"
```

### Step 4: Update the About Page
Open `about.html` and customize:

1. Add your background information
2. Update your goals and skills
3. Modify the fun facts section

```bash
# Check changes
git diff about.html

# Stage and commit
git add about.html
git commit -m "Update about page with personal background"
```

**✅ Success Check:** You should now have 3 commits in your history.

## Exercise 3: Working with CSS 🎨

### Step 1: Customize Colors
Open `styles.css` and make these changes:

1. Change the header background color (line ~20):
   ```css
   background-color: #34495e; /* Try a different color! */
   ```

2. Modify the hero gradient (around line ~50):
   ```css
   background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
   /* Try different colors! */
   ```

### Step 2: See Your Changes
```bash
# Check what changed
git diff styles.css

# Stage just this change
git add styles.css

# Make a focused commit
git commit -m "Update color scheme for better visual appeal"
```

### Step 3: Add More Styling
Add this new CSS rule at the end of `styles.css`:

```css
/* New styling for better readability */
.intro p {
    font-size: 1.1rem;
    line-height: 1.8;
    margin-bottom: 1.5rem;
}
```

```bash
# Stage and commit the new styling
git add styles.css
git commit -m "Improve typography for better readability"
```

**✅ Success Check:** Check `git log --oneline` - you should have 5 commits now.

## Exercise 4: Understanding Git History 📖

### Step 1: Explore Your History
```bash
# See all commits with details
git log

# Compact view
git log --oneline

# See what files changed in each commit
git log --stat

# Visual representation
git log --graph --oneline
```

### Step 2: Compare Versions
```bash
# See what changed in the last commit
git show HEAD

# See changes between commits
git diff HEAD~2 HEAD~1

# Compare current version to initial commit
git diff HEAD~4 HEAD
```

### Step 3: View Specific Commit
```bash
# Get commit hash from git log --oneline
git show <commit-hash>

# Or use relative references
git show HEAD~2
```

**✅ Success Check:** You can navigate your project's history and understand what changed when.

## Exercise 5: Creating a Feature Branch 🌿

### Step 1: Create a Projects Page Branch
```bash
# Create and switch to new branch
git checkout -b add-projects-page

# Verify you're on the new branch
git branch
```

### Step 2: Add a Projects Page
Create a new file called `projects.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Projects - Your Name</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="about.html">About</a></li>
                <li><a href="projects.html">Projects</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="projects-content">
            <h1>My Projects</h1>
            
            <div class="project">
                <h2>Personal Website</h2>
                <p>This website! Built while learning Git and GitHub.</p>
                <p><strong>Technologies:</strong> HTML, CSS, Git</p>
            </div>

            <div class="project">
                <h2>Learning Git Repository</h2>
                <p>A comprehensive tutorial repository for learning version control.</p>
                <p><strong>Technologies:</strong> Git, GitHub, Markdown</p>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Your Name. Learning Git one commit at a time!</p>
    </footer>
</body>
</html>
```

### Step 3: Update Navigation in Other Pages
Add the projects link to the navigation in `index.html`, `about.html`, and `contact.html`:

```html
<li><a href="projects.html">Projects</a></li>
```

### Step 4: Stage and Commit the New Feature
```bash
# Add all the changes
git add .

# Commit the new feature
git commit -m "Add projects page with navigation updates"
```

### Step 5: Switch Back to Main and Merge
```bash
# Switch to main branch
git checkout main

# Merge the feature branch
git merge add-projects-page

# Clean up: delete the feature branch
git branch -d add-projects-page
```

**✅ Success Check:** Your website now has a projects page, and the feature branch is merged and deleted.

## Exercise 6: Fixing a Bug 🐛

### Step 1: Create a Bugfix Branch
```bash
# Notice the contact form doesn't have proper styling
git checkout -b fix-contact-form-styling
```

### Step 2: Add CSS for Better Form Styling
Add this CSS to the end of `styles.css`:

```css
/* Better contact form styling */
.contact-info {
    background-color: #f8f9fa;
    padding: 1.5rem;
    border-radius: 8px;
    margin-bottom: 2rem;
    border-left: 4px solid #3498db;
}

.contact-info a {
    color: #3498db;
    text-decoration: none;
}

.contact-info a:hover {
    text-decoration: underline;
}
```

### Step 3: Commit the Fix
```bash
git add styles.css
git commit -m "Fix contact page styling for better visual hierarchy"
```

### Step 4: Switch Back and Merge
```bash
git checkout main
git merge fix-contact-form-styling
git branch -d fix-contact-form-styling
```

**✅ Success Check:** Your contact page now has better styling.

## Exercise 7: Final History Review 📚

### Step 1: Review Your Complete History
```bash
# See all your commits
git log --oneline --graph

# Count your commits
git rev-list --count HEAD

# See your contribution stats
git shortlog -sn
```

### Step 2: Create a Summary Commit
Add a comment to your README.md or create a new file called `CHANGELOG.md`:

```markdown
# Website Changelog

## Version 1.0 - Initial Release
- ✅ Created basic website structure
- ✅ Added personalized content
- ✅ Implemented custom styling
- ✅ Added projects page
- ✅ Fixed contact page styling
- ✅ Practiced Git branching workflow

## Technologies Used
- HTML5 for structure
- CSS3 for styling  
- Git for version control
- Practiced on: [Date]

## Git Skills Practiced
- Repository initialization
- Staging and committing changes
- Branch creation and merging
- Writing descriptive commit messages
- History exploration
```

```bash
git add CHANGELOG.md
git commit -m "Add project changelog and summary"
```

**✅ Success Check:** You should have approximately 8-10 commits in your history.

## 🎓 What You've Accomplished

Congratulations! You've successfully:

- ✅ **Initialized a Git repository** from existing files
- ✅ **Made meaningful commits** with descriptive messages
- ✅ **Personalized a website** using Git workflow
- ✅ **Used the staging area** effectively
- ✅ **Explored Git history** with various commands
- ✅ **Created and merged branches** for features and bug fixes
- ✅ **Practiced real-world Git workflows** used by developers

## 🚀 Extension Challenges

Ready for more? Try these advanced exercises:

### Challenge 1: Multiple Feature Branches
- Create separate branches for different features
- Work on multiple features simultaneously
- Practice switching between branches

### Challenge 2: Intentional Merge Conflict
- Create the same file on two different branches
- Try to merge and resolve the conflict
- Learn conflict resolution skills

### Challenge 3: History Exploration
- Use `git blame` to see who changed what
- Use `git bisect` to find when something changed
- Practice advanced log filtering

### Challenge 4: Backup and Collaboration
- Push your repository to GitHub
- Clone it to a different directory
- Practice push/pull workflows

## 🔧 Troubleshooting

### "Nothing to commit"
- Make sure you've made changes to files
- Check that changes are staged with `git add`

### "Merge conflict"  
- Open the conflicted files
- Look for `<<<<<<<` and `>>>>>>>` markers
- Edit the file to keep what you want
- Stage and commit the resolved file

### "Branch already exists"
- Use `git branch -d branchname` to delete old branches
- Or use `git checkout` to switch to existing branch

### Lost or confused?
- Use `git status` to see current state
- Use `git log --oneline` to see where you are
- Start over by deleting `.git` and running `git init`

## 📝 Reflection Questions

After completing these exercises, think about:

1. **What was the most challenging part?**
2. **How do you think branching helps in real projects?**
3. **What commit message style works best for you?**
4. **How could you use Git for school projects?**
5. **What would you like to learn next about Git?**

## 🎯 Next Steps

You're now ready for more advanced Git topics:

- **Remote repositories**: Learn to push to GitHub
- **Collaboration**: Work with others on the same project
- **Advanced branching**: Learn Gitflow and other strategies
- **GitHub features**: Issues, pull requests, and actions

**Continue with:** [Tutorial 8: Creating a GitHub Account](../../tutorials/08-github-account.md)

---

**🎉 Congratulations on completing your first Git project!** You now have practical experience with the core Git workflow that developers use every day.