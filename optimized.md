---
layout: page
title: Optimized Linear Algebra libraries
tagline: Documenting initial setup/installs for DataSci/ML projects
description:
---
updated 19 Jan 2019

If you are doing a lot of ML work, it may be worth using linear algebra libraries that have been optimized for the instructionset supported by your processor(s).  In this case, you may have to edit your Python/R installations as well as update evironmental variables on your OS to point to the optimized libraries. 

[Download Intel MKL packages](https://software.intel.com/en-us/mkl) and install prior to installing Python or R.  Follow the instruction/user guide that pops up following the installation. Files (and setup scripts) are located here:
* Linux OS and macOS:
  * For super-users: `/opt/intel/compilers_and_libraries_<version>`
  * For ordinary users: `$HOME/intel/compilers_and_libraries_<version>`
* Windows OS:
  * `<Program Files>\IntelSWTools\compilers_and_libraries_<version>`

## References
* http://blog.nguyenvq.com/blog/2014/11/10/optimized-r-and-python-standard-blas-vs-atlas-vs-openblas-vs-mkl/


