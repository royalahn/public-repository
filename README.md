## How to use Git  

### Download source codes  
- Download the latest source codes **at first**    
```
git clone https://github.com/royalahn/PublicRepository.git
```
- Download the latest source codes **not first time** (Force)  
```
git pull
```
- Download codes to **FETCH_HEAD** branch not master  
```
git fetch
git checkout FETCH_HEAD
```
(Refer to **[Merge the codes](#merge-the-codes)**)  

### Update source codes  
- Add to staging area  
```
git add <files>
git add *
git add *.java
```
- Except in staging area (Unstage)  
```
git reset HEAD <files>
```
- Remove in staging area  
```
git rm <files>
```
- Remove in stating area but not local storage  
```
git rm --cached <files>
```
- Discard changes in local storage (Same as revert on Perforce)  
```
git checkout -- <files>
```

### Update to local repository  
- Normal Case  
```
git commit -a -m "Your comments v1.0.0"
```
- Modification commit  
```
git commit --amend
```

### Show current branch  
```
git branch
```

### Show the status codes  
```
git status
```

### Show the history to commit  
```
git log
git log --all
git log --pretty=oneline
```

### Update the codes to remote repository  
- with **Gerrit**  
```
git push origin HEAD:refs/for/master
```
- without **Gerrit(Standalone)**  
```
git push origin HEAD:master
```
- check remote repository  
```
git remote -v
```

### Select branches  
- Select branch after creates the new branch  
```
git checkout -b newBranch
```
- Select branch  
```
git checkout master
```

### Remove branches  
```
git checkout oldBranch
git checkout -d oldBranch
```

### Merge the codes  
- one commit  
```
git checkout master
git merge FETCH_HEAD
```
- more two commits  
```
git merge --squash newBranches
```

### Rebase  
- Normal Case  
```
git checkout otherBranch
git rebase master
```
- Conflict Case  
```
git checkout otherBranch
git rebase --continue [master]
```

### Show git configuration  
```
git config --list
```

### Create remote repository (Make it Git Server)  
```
git init --bare NewGitProject.git
git clone NewGitProject.git
```

### Add alias for log  
```
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(cyan)%h%C(reset) - %C(green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)' --all"
git lg
```
