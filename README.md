# Frequent Commands
1. [Homebrew](#anchor_Homebrew)<br/>
2. [Python(local)](#anchor_Python)<br/>
3. [virtual environment](#anchor_venv)<br/>
4. [Jupyter Lab](#anchor_Jupyter)<br/>
5. [Version Control](#anchor_VersionControl)<br/>
6. [Shell](#anchor_Shell)<br/>
7. [MySQl(local)](#anchor_MySQl)<br/>
  -------------------------------------------------------------------
### Homebrew<a name="anchor_Homebrew"></a>
- list homebrew applications```brew list```

### Python(local)<a name="anchor_Python"></a>
mac default python path```/usr/bin/python2.7```
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
  - activate your virtual environment```source ~/venv/bin/activate```
  - then install Turi Create within your virtual environment:```(venv) pip install -U turicreate```
  - refer to https://github.com/apple/turicreate#installation

### virtual environment<a name="anchor_venv"></a>
- find venv pathway```cd ~```
- change Python version in venv, this only works if you have python2.7 installed at the system level (e.g. /usr/bin/python2.7)
  - change default python version in virtual environment```virtualenv -p python2.7 venv```
  - change python version temporarily```virtualenv venv --python=python2.7```
- quit environment```deactivate```
- delete virtual environment```rm -rf venv```

### Jupyter Lab<a name="anchor_Jupyter"></a>
- find pip installed application```pip list```
- open Jupyter```jupyter lab```
###### uninstall all jupyterlab and its dependencies
  - install ```pip3 install python3-pip-autoremove```
  - then```pip3-autoremove jupyterlab```

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

### Shell<a name="anchor_Shell"></a>
after executing ```source ~/.bash_profile```, your all commands are invalid.
  - maybe u write wrong PATH, so try```PATH=/bin:/usr/bin:/usr/local/bin:＄{PATH}```
 
### MySQL<a name="anchor_MySQL"></a>
