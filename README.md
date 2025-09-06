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
 git restore --staged <folder name>   
 git checkout -- <folder name>      
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
```
git clone https://github.com/your-username/your-repo.git
```
# ↔️Switch to Main branch(Initially it is main)
```
git fetch origin
git checkout main
```
# 📤 Push Mechanisms
  ### Push to master branch
  ```git push origin master```           
  
  ## ❗Common Errors: Push Rejected / Unrelated Histories
   Problem: Push Rejected <br>
   Solution:
  ```
    git pull origin master
  ```
   If you see: fatal: refusing to merge unrelated histories then-
  ```
    git pull origin master --allow-unrelated-histories
    git push
   ```
  📌Why does this happen?<br>
    You created a local repo and a remote repo separately, then connected them. Their histories don't match.

# 📤 Set Upstream Branch (Git push works directly)
  ```
  git push --set-upstream origin master
  ```
✅ Recommended: Use feature branches instead of pushing directly to main.

## 🌱 Why Use Branches?
  Scenario 1:<br>
    A single project contains multiple tech stacks (Java, Spring Boot, HTML, CSS, JS, Docker). Keeping everything on main becomes messy. Use separate branches for each.
    <br><br>
  Scenario 2:<br>
    A team of 10 developers pushing directly to main causes chaos. Instead, each member should have their own branch. This keeps the workflow smooth and organized.

# 🌿 Create and Push a New Branch
  ### Create new branch
  ```git branch pointer  ```  
  ### Switch to the new branch           
  ```git checkout pointer ``` 
  ### Push to new branch           
  ```
  git add .
  git commit -m "message"
  git push origin pointer  
  ```       
  
# 🔄 Switch Between Branches
  ```
  git checkout pointer
  git checkout master
  git checkout main
  ```

# 🔁 Merge Pull Requests (Manually)
  1-Switch to main <br>
  2-Merge branch 'pointer' into main
  ```
  git checkout main                
  git merge pointer         
  ```

# ✏️ Rename Branch
1-Rename current branch to 'vault'
2-Delete old branch from remote
3-Push renamed branch
```
  git branch -m vault               
  git push origin --delete project  
  git push origin vault            
  git push --set-upstream origin vault
```
