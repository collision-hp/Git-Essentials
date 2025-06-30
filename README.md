# 🚀 Git Essentials

A concise and practical collection of essential Git commands and usage instructions for beginners and intermediate developers. Perfect for quick reference, learning, and mastering version control with Git.


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# 📂 General Git Commands

### Create a new folder
 ``` mkdir project ```
### Initialize Git repo (.git)
```git init ```                       
### Show all files including hidden (.git)
```  ls -a  ```                          
### Create a new file
```  touch new.java```                   
### Check the status of files and branch
```  git status ```                      
### Add all files to the staging area
```git add .```                        
### Commit with a message
```  git commit -m "new file upload" ``` 
### Unstage a file after adding
```  git restore --staged new.java```    
### View all commits
```  git log```                          
### Exit from git log or merge editor
```  :q or wq```                         
<br>

# 🗑️ Permanently Delete a File (from local + Git)
  ```
  git rm -r names.txt
  git add .
  git commit -m "Deleted names.txt"
  ```

# 🔄 Restore or Revert Changes
 1- Unstage file<br>
 2-Restore file from last commit
 ``` 
 git restore --staged names.txt   
 git checkout -- names.txt        
```

# 🧹 Remove from Git Only (Keep Locally)
```  
git rm -r --cached Tribute-Page
```
# 🌐 Connect to GitHub Remote
```
git remote add origin https://github.com/your-username/your-repo.git
```
# 🔗Clone to Local Device
```git clone https://github.com/your-username/your-repo.git```
# 📤 Push Mechanisms
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
