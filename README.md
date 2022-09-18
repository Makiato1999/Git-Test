# Frequent Commands
1. [Homebrew](#anchor_Homebrew)<br/>
2. [Jupyter Lab](#anchor_Jupyter)<br/>
3. [Version Control](#anchor_VersionControl)<br/>
  -------------------------------------------------------------------
### Homebrew<a name="anchor_Homebrew"></a>
- list homebrew applications```brew list```

### Jupyter Lab<a name="anchor_Jupyter"></a>
- find pip installed application```pip list```
- open Jupyter```jupyter lab```

### Version Control<a name="anchor_VersionControl"></a>
simple git commands for 
1. open terminal and find the location of the clone repository 
2. ```git clone -b branch``` + urlLink
3. check if there is the file you need
4. ```git checkout -b newBranch```, create a new branch
5. ```git status```
6. ```git add helloWorld.java``` / ```git add *```
7. ```git commit -m "add helloWorld.java to main branch..."```
8. ```git push -u origin yourBranchName```

- login Github, ```gh auth login```
- if u want to clone repository, ```gh repo clone <YOUR USERNAME>/<REPOSITORY-NAME>```
- if repository is exist,
- open terminal and find the location of the clone repository 
- ```git clone -b branch``` + urlLink
- check if there is the file you need
- create a new branch, ```git checkout -b yourNewBranchName```, go back to main branch, ```git checkout main```
- check current branches, ```git status```
- change untracked file to tracked, add file in staging status, ```git add helloWorld.java``` / ```git add *```
- restore file from tracked to untracked, go back to last step, ```git restore --stage helloWorld.java```
- ```git commit -m "add helloWorld.java to main branch..."```
- ```git push -u origin yourBranchName```
- updated local content from remote repository, ```git pull```
