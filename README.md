# Git-Essentials
A concise and practical collection of essential Git commands and usage instructions for beginners and intermediate developers. Perfect for quick reference, learning, and mastering version control with Git.

# 🚀 Git Essentials

A collection of essential Git commands and instructions for beginners and developers. This guide covers all the necessary Git operations with explanations and use-cases. Great for quick reference and learning Git workflows.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 📂 General Git Commands

  mkdir project                    # Create a new folder
  git init                         # Initialize Git repo (.git)
  ls -a                            # Show all files including hidden (.git)
  touch new.java                   # Create a new file
  git status                       # Check the status of files and branch
  git add .                        # Add all files to the staging area
  git commit -m "new file upload"  # Commit with a message
  git restore --staged new.java    # Unstage a file after adding
  git log                          # View all commits
  :q or wq                         # Exit from git log or merge editor

🗑️ Permanently Delete a File (from local + Git)
  git rm -r names.txt
  git add .
  git commit -m "Deleted names.txt"

🔄 Restore or Revert Changes
  git restore --staged names.txt   # Unstage file
  git checkout -- names.txt        # Restore file from last commit

🧹 Remove from Git Only (Keep Locally)
  git rm -r --cached Tribute-Page

🌐 Connect to GitHub Remote
  git remote add origin https://github.com/your-username/your-repo.git

📤 Push Mechanisms
  git push origin master           # Push to master branch
 ❗Common Errors: Push Rejected / Unrelated Histories
    # Problem: Push Rejected
    git push origin master
    # Solution
    git pull origin master
    # If you see: fatal: refusing to merge unrelated histories
    git pull origin master --allow-unrelated-histories
    # Now just run:
    git push
  📌Why does this happen?
    You created a local repo and a remote repo separately, then connected them. Their histories don't match.

📤 Set Upstream Branch (So that git push works directly)
  git push --set-upstream origin master
✅ Recommended: Use feature branches instead of pushing directly to main.

🌱 Why Use Branches?
  Scenario 1:
    A single project contains multiple tech stacks (Java, Spring Boot, HTML, CSS, JS, Docker). Keeping everything on main becomes messy. Use separate branches for each.
  Scenario 2:
    A team of 10 developers pushing directly to main causes chaos. Instead, each member should have their own branch. This keeps the workflow smooth and organized.

🌿 Create and Push a New Branch
  git branch pointer               # Create new branch
  git checkout pointer             # Switch to the new branch
  git add .
  git commit -m "message"
  git push origin pointer          # Push new branch
  
🔄 Switch Between Branches
  git checkout pointer
  git checkout master
  git checkout main
  
🔁 Merge Pull Requests (Manually)
  git checkout main                # Switch to main
  git merge pointer                # Merge branch 'pointer' into main
  # Then save & close the editor

✏️ Rename Branch
  git branch -m vault               # Rename current branch to 'vault'
  git push origin --delete project  # Delete old branch from remote
  git push origin vault             # Push renamed branch
  git push --set-upstream origin vault
