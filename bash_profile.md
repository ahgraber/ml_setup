# macOS 

### setting PATH 
```
nano ~/.bash_profile
```
```
## PATH
  # Adds all these paths to the PATH variable. The colon (:) is the path separa$
  # When you need to "add something to path" you're supposed to add the path
  # to its executable file to this list of paths, separated by a colon.
  # BKUP: export PATH="/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/$

# Setting PATH for X11
PATH="/usr/X11/bin"
export PATH

# Setting PATH for clang6
PATH="/usr/local/clang6/bin:${PATH}"
export PATH


# Setting PATH for Python 2.7
# The original version is saved in .bash_profile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/2.7/bin:${PATH}"
export PATH

# Setting PATH for Python 3.7
# The original version is saved in .bash_profile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/3.7/bin:${PATH}"
export PATH
QT_API=pyqt5

# Set unix path last for precedence:
PATH="/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:${PATH}"
export PATH
```

### setting up aliases for terminal
```
nano ~/.bash_profile
```
```
## ALIAS
alias ls="ls -aG"

# to run tensorflow in virtualenv
alias tensorflow="cd ~/tensorflow ;  source ./bin/activate"

# to run jupyter notebook
alias jupyter="ulimit -n 4096 && jupyter notebook"

# to run ipopt solver
alias ipopt="/Users/mithras/Ipopt/build/bin/ipopt"
```
