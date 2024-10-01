# Frequent Commands
1. [Windows Git](#anchor_windows)<br/>
2. [Homebrew](#anchor_homebrew)<br/>
3. [Python(local)](#anchor_python)<br/>
4. [virtual environment](#anchor_venv)<br/>
5. [Jupyter Lab](#anchor_jupyter)<br/>
6. [Version Control](#anchor_versioncontrol)<br/>
7. [Shell](#anchor_shell)<br/>
8. [MySQl(local)](#anchor_mysql)<br/>
9. [Java](#anchor_java)<br/>
  -------------------------------------------------------------------
### Windows Git<a name="anchor_windows"></a>
Clone the remote repository
  1. create folder in local disk
     ```
     mkdir C:/Dev/MyApp
     ```
  2. initialize empty Git repository in `C:/Dev/MyApp/.git/`
     ```
     cd C:/Dev/MyApp
     git init
     ```
  3. link a local Git repository to a remote repository
     ```
     git remote add origin Remote_Repository_URL
     ```
  4. retrieve updates from the remote repository named `origi`
     ```
     git fetch origin
     ```
  5. create a new local branch that tracks a remote branch
     ```
     git checkout -b Local_Branch_Name origin/Remote_Branch_Name
     ```
  6. check all local and remote branches
     ```
     git branch -a
     ```
  7. temporarily save changes in your working directory that you don't want to commit just yet
     ```
     git stash
     ```
Revert commit in Pull Request
  1. check recent commit history
     ```
     git log -1
     ```
  2. choose the commit hash id and revert
     ```
     git revert commit-hash-id
     ```
  3. clean unstagged and untracted files & directories
     ```
     git clean -fd
     ```
  4. check current status
     ```
     git status
     ```
  5. after modification, git add, commit, push and check your PR

### Homebrew<a name="anchor_homebrew"></a>
list homebrew applications```brew list```

### Python(local)<a name="anchor_python"></a>
mac default python path```/usr/bin/python2.7```<br>
other python path```/usr/local/opt/python@3.9```
###### Installing Python paths for MacOS
- first, check python version `python --version`
- By default, an Apple Mac has Python installed with version 2.7
  - If you want to change default version to 2.7 from any other version
    - open script```vim ~/.zshrc```
    - add```PATH="/Library/Python/2.7/bin:${PATH}```because this is python2.7 pathway
    - compile it with `source ~/.zshrc`
- so, check `python3 --version`
  - if it exists, then we will change the default path
    - first, check the PATH `brew info python`
    - then, find this line <br/>
      ``Unversioned symlinks `python`, `python-config`, `pip` etc. pointing to
      `python3`, `python3-config`, `pip3` etc., respectively, have been installed into
      /usr/local/opt/python@3.9/libexec/bin``
    - so far, we get the PATH, which is `/usr/local/opt/python@3.9/libexec/bin`, PATH could be different, it depends on your own mac.
    - now, we will update the default PATH
    - open `vim ~/.zshrc`, my shell is zsh
      - if your shell is bash, use `vim ~/.bashrc`
      - when you open zshrc, if there is `Found a swap file by the name...`, delete it.
    - then press `i`, switch to the insert mode, and add the following line `PATH="/usr/local/opt/python@3.9/libexec/bin:${PATH}"`
    - press `esc`, then press`:`, then input `wq` to exit zshrc.
    - compile it with `source ~/.zshrc`
    - then check `python --version`, look if the default version is updated.
- if it doesn't exist, we will install new version Python
  - install hom brew first, then `brew info python`
  - then, go back to if it exists
###### Install Turi Create within your virtual environment
  - first```cd ~```
  - create environment```virtualenv venv```/again
  - <b>activate your virtual environment</b>```source ~/venv/bin/activate```
  - then install Turi Create within your virtual environment:```(venv) pip install -U turicreate```
  - refer to https://github.com/apple/turicreate#installation

### virtual environment<a name="anchor_venv"></a>
active existed venv
- find venv pathway```cd ~```
- <b>activate your virtual environment</b>```source ~/venv/bin/activate```
- quit environment```deactivate```

create venv
- find venv pathway```cd ~```
- install virtual environment ```pip install virtualenv```
- change Python version in venv, this only works if you have python2.7 installed at the system level (e.g. /usr/bin/python2.7)
  - change default python version in virtual environment```virtualenv -p python2.7 venv```
  - change python version```virtualenv venv --python=python2.7```
- quit environment```deactivate```
- delete virtual environment```rm -rf venv```

### Jupyter Lab<a name="anchor_jupyter"></a>
- find pip installed application```pip list```
- open Jupyter```jupyter lab```
###### uninstall all jupyterlab and its dependencies
  - install ```pip3 install python3-pip-autoremove```
  - then```pip3-autoremove jupyterlab```

### Version Control<a name="anchor_versioncontrol"></a>
simple git commands for 
1. open terminal and find the location of the clone repository 
2. ```git clone -b branch``` + urlLink
3. check if there is the file you need
4. ```git checkout -b newBranch```, create a new branch
5. ```git status```
6. ```git add helloWorld.java``` / ```git add *```
7. ```git commit -m "add helloWorld.java to main branch..."```
8. ```git push -u origin yourBranchName```

update remote repository and branch
1. go to local branch which you wanna push
2. ```git pull HTTP yourBranchName```
3. ```git status```
4. ```git add *```
5. ```git commit -m "what u want..."```
6. ```git push -u origin yourBranchName```
  - ```origin``` stands for current cloned branch

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

### Shell<a name="anchor_shell"></a>
if after executing ```source ~/.zshrc```, your all commands are invalid.
  - maybe u write wrong PATH, so try```PATH=/bin:/usr/bin:/usr/local/bin:＄{PATH}```

ZSH, Oh My Zsh!
  - [10 minutes video](https://www.youtube.com/watch?v=9eJ0HHHNuls)
  - change theme```p10k configure```
 
### MySQL<a name="anchor_mysql"></a>
connect by ```mysql -h localhost -P 3306 -u root -p```<br>
```xxr990610```


### Java<a name="anchor_java"></a>
Java path
1. find java path```/usr/libexec/java_home -v19```<br>
   which is ```/Library/Java/JavaVirtualMachines/jdk-19.jdk/Contents/Home```
2. open bash change default java```vi .bash_profile```or```code .bash_profile```<br>
   then add ```export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-19.jdk/Contents/Home``` at end of the file
3. check updated path```echo $JAVA_HOME```<br>
   which should be ```/Library/Java/JavaVirtualMachines/jdk-19.jdk/Contents/Home```
4. refer to this [link](https://www.youtube.com/watch?v=pxi3iIy4F5A&list=PL_hEbhs9YfZir3irk75Knq1CVjxpAnrxy&index=22)
