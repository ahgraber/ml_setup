# R Setup
updated 19 Jan 2019

1. Decide whether to use vanilla R or an optimized version:  
If you are doing a lot of ML work, it may be worth using linear algebra libraries that have been [optimized for the instruction set supported by your processor(s)](optimized.md).  In this case, you may have to edit your Python/R installations as well as update evironmental variables on your OS to point to the optimized libraries .  
In fact, while you can hack it yourself by downloading some optimized BLAS packages and enabling multithreaded performance, [Microsoft(!)](https://mran.microsoft.com/documents/rro/multithread) has done all of the hard lifting for you!  

2. Download R (pick a version)  
   * [Vanilla R](https://cran.rstudio.com/banner.shtml) and install (current R version R-3.5.2)
      * On macOS, you can [use the veclib from the Accelerate framework](https://gist.github.com/nicebread/6920c8287d7bffb03007)
      ```
      # use faster vecLib library
      cd /Library/Frameworks/R.framework/Resources/lib
      ln -sf  /System/Library/Frameworks/Accelerate.framework/Frameworks/vecLib.framework/Versions/Current/libBLAS.dylib libRblas.dylib
      ```
   * [Microsoft Optimized R](https://mran.microsoft.com/download) and install(current R version R-3.5.1)  
      * If running an Intel CPU, [download Intel's MKL (Math Kernel Library)](https://software.intel.com/en-us/mkl) - especially if on Windows (the Microsoft R will use Apple's math libraries if MLK is not present)

2. If mac, [download xQuartz](https://www.xquartz.org/) and install
3. [Download RStudio](https://www.rstudio.com/products/rstudio/download/#download) and install (current RStudio version 1.1.463)
4. Install Packages in RStudio:
```
# see also: https://awesome-r.com/

# standard
install.packages('tidyverse')   # standard package for data wrangling and manipulation
install.packages('glue')        # evaluates variables and R expressions within {var or expression}
install.packages('ggplot2')     # for visualizations
install.packages('data.table')  # for fast dataframes
install.packages('e1071')       # misc statistical functions
install.packages('beepr')       # audio notifications

# machine learning models
install.packages('Matrix')      # matrix/sparse matrix
install.packages('slam')        # matrix/sparse matrix
install.packages('glmnet')      # regularized nonlinear regressions
install.packages('car')         # supporting functions for regression
install.packages('caret')       # kfold crossvalidation & ml design tools
install.packages('xgboost')     # eXtreme Gradient Boosting Tree model
install.packages('ROCR')        # visualizing classifier performance
install.packages('PROc')        # visualizing classifier performance

# for forecasting
install.packages('lubridate')   # supporting time-series data
install.packages('zoo')         # supporting time-series data
install.packages('forecast')    # broad forecasting package
install.packages('prophet')     # forecasting with multiple seasonality

# for nlp
install.packages('tidytext')    # text wrangling
install.packages('tm')          # text mining framework
install.packages('topicmodels') # topic models
install.packages('quanteda')    # quantitative analysis of text data
install.packages('text2vec')    # text vectorization

# for parallelization
install.packages('foreach')     # parallelized for loops
install.packages('doparallel')  # parallelization
install.packages('parallel')    # parallelization

# for tensorflow / keras (install in python first)
install.packages('reticulate')  # python in R
install.packages('feather')     # binary data structure that can be ready by both python and R
install.packages('tensorflow')  # frontend for tensorflow
install.packages('keras')       # frontend for keras

# for package development
install.packages('devtools')    # tools for packaging
install.packages('roxygen2')    # function documentation
install.packages('packman')     # checks for package installation/load

# extending R
install.packages('rJava')       # java + R
```

## References
* http://blog.nguyenvq.com/blog/2014/11/10/optimized-r-and-python-standard-blas-vs-atlas-vs-openblas-vs-mkl/
* https://software.intel.com/en-us/articles/quick-linking-intel-mkl-blas-lapack-to-r
* https://software.intel.com/en-us/mkl
* https://cran.r-project.org/doc/manuals/r-release/R-admin.html#MKL
* https://www.r-bloggers.com/an-openblas-based-rblas-for-windows-64/
* https://brettklamer.com/diversions/statistical/faster-blas-in-r/
* https://gist.github.com/nicebread/6920c8287d7bffb03007
