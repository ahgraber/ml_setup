# R Setup
updated 19 Jan 2019

1. [Download R](https://cran.rstudio.com/banner.shtml) and install (current R version R-3.5.2)
2. If mac, [download xQuartz](https://www.xquartz.org/) and install
3. [Download RStudio](https://www.rstudio.com/products/rstudio/download/#download) and install (current RStudio version 1.1.463)
4. Optional: if you have installed an optimized linear algebra implementation, ensure R knows about it
```
```
5. Install Packages in RStudio:
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
