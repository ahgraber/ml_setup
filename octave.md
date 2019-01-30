---
layout: page
title: Installing Octave+GUI - Optional
tagline: Documenting initial setup/installs for DataSci/ML projects
description:
---
updated 19 Jan 2019

If you've taken (or plan to take) [Andrew Ng's Machine Learning course on Coursera](https://www.coursera.org/learn/machine-learning/), you will need Octave to complete the assignments.

Fortunately, the good folks at Octave and the community have updated the project so installation is (relatively speaking) easier than it used to be.

### Easy Install
1. Ensure all requirements are fulfilled
   * Java requirements:
     The Java 1.8 you have installed must be exactly jdk1.8.0_181.jdk, due to how the Octave build and Java detection system works. (This was the latest release of JDK 1.8 at the time Octave.app 4.4.0 was built.) You can download it [here](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).
2. [Download Octave](https://github.com/octave-app/octave-app/releases/download/v4.4.0/Octave-4.4.0.dmg) and install
     
### Homebrew Install
1. Ensure all requirements are fulfilled
   * X11: Ensure you have [downloaded and installed xQuartz](https://www.xquartz.org/)
   * xcode command line tools are installed
   ```
   xcode-select --install.
   ```
   * [Homebrew is installed](https://brew.sh/)
   ```
   /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
   ```
   ```
   brew install gcc
   brew install qt
   brew install octave --with-qt
   ```
2. Follow the same process used for Jupyter or Spyder to create an app launcher
   1. Open Applescript Editor
   2. Write script as follows, and save as type Application in your Applications folder
   ```
   tell application "Terminal"
    do shell script "/usr/local/bin/octave --force-gui"
   end tell
   ```


### Post-Install
Once Octave in installed, you may want to install packages a la Python or R:
```
pkg install -forge optim
pkg install -forge struct
pkg install -forge statistics
pkg install -forge optim
pkg install -forge general
pkg install -forge io
pkg install -forge linear-algebra
```

## References
https://wiki.octave.org/Octave_for_macOS (see troubleshooting tips at bottom)  
https://octave-app.org/Download.html  
https://github.com/octave-app
