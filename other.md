# macOS

* Install [xQuartz](https://www.xquartz.org/) for X11 support 
* Install xcode command line tools
```
xcode-select --install.
```
* Install [Homebrew](https://brew.sh/)
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
   * Recommended homebrew casks:
   ```
   brew install wget
   brew install ruby
   brew install gcc
   brew install cairo
   brew install ghostscript  
   ```
* [Symbolic links](http://osxdaily.com/2015/08/06/make-symbolic-links-command-line-mac-os-x/)
```
# to create
ln -s /path/to/original/ /path/to/link

# to remove
rm /path/to/symlink
# or
unlink /path/to/symlink
```

# Windows (note: macOS is my primary OS, so these instructions will be somewhat less detailed)
You might consider:
* install [Microsoft Visual Studio IDE, Code](https://visualstudio.microsoft.com/)
  * Code is a fast coding environment (a la Sublime Text)
  * IDE is an IDE - choose the dev environments it supports (my 'defaults' include .NET, C++, Python, R, and SQL bringing it to ~30GB) 
* optional:  install an x windows server - this allows you to run graphical applications from the Linux environment
  * [VcXsrv Windows X Server](https://sourceforge.net/projects/vcxsrv/)
    * To limit access, open Windows Firewall, go to Advanced Settings, find VcXsrv, and edit properties for both TCP and UDP:
      * Advanced > Edge Traversal > Defer to Application
      * Scope > Local/Remote IP Address > 127.0.0.1
    * Start the X Server with `"C:\Program Files\VcXsrv\vcxsrv.exe" :0 -ac -terminate -lesspointer -multiwindow -clipboard -wgl -dpi auto`
* Install [Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/en-us/windows/wsl/about): 
  * Open PowerShell as Administrator, then run:
  ```
  Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
  ```
  * Download Linux subsystem through PowerShell, then install & launch once installed:
  ```
  Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1804 -OutFile Ubuntu.appx -UseBasicParsing
  Ubuntu.appx
  ```
  * Set up your Linux-side user and password (this has no bearing on Windows side)
  * Note: To access Windows-side folders & documents, go to `/mnt/c/` on WSL
  * Install supporting packages:
  ```
  sudo apt update && sudo apt upgrade
  sudo apt-get install -y build-essential gfortran
  sudo apt-get install -y zlib1g-dev liblapack-dev libatlas-base-dev libopenblas-dev libhdf5-dev libedit-dev
  sudo apt-get install -y git
  sudo apt-get install -y jupyter
  ```
  * If you're not happy with the vanilla Linux terminal, you can try installing a [Linux terminal emulator](https://blog.ropnop.com/configuring-a-pretty-and-usable-terminal-emulator-for-wsl/).  See link for config hints
  ```
  sudo apt-get install -y terminator
  ```
* install [Strawberry Perl](http://strawberryperl.com/)
* install [puTTYgen](https://www.puttygen.com/) and [WinSCP](https://winscp.net/eng/index.php) - SSH and telnet
* install [Chocolaty](https://chocolatey.org/) and/or [Scoop](http://scoop.sh/) - package manager for Windows
