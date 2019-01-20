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
