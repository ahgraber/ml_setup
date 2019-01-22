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
* install Linux subsystem for Windows
  * Open PowerShell as Administrator, then run: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`
* install [cygwin](https://www.cygwin.com/) - unix environment for Windows

* install [Strawberry Perl](http://strawberryperl.com/)

* install [puTTYgen](https://www.puttygen.com/) and [WinSCP](https://winscp.net/eng/index.php) - SSH and telnet
* install [Chocolaty](https://chocolatey.org/) and/or [Scoop](http://scoop.sh/) - package manager for Windows
