---
layout: page
title: Python Setup
tagline: Documenting initial setup/installs for DataSci/ML projects
description:
---
updated 28 Sept 2019

1. On choosing between conda and pip:
      * [Understanding Conda and Pip](https://www.anaconda.com/understanding-conda-and-pip/)
      * [Anaconda vs Miniconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/download.html#anaconda-or-miniconda)
      * [Which Python package manager should you use?](https://towardsdatascience.com/which-python-package-manager-should-you-use-d0fd0789a250)
2. Windows note: Consider installing WSL (Windows Subsystem for Linux) and running your entire python environment through WSL. You can start a jupyter notebooks server on the WSL side and access in using browser from Windows using `http://localhost:8888/...` 
2. Ensure PATH is correct (see [.bash_profile](https://github.com/ahgraber/ml_setup/edit/master/bash_profile.md))  
3. Load python packages to support dev environment.  If using jupyter notebook or spyder3 on macOS, it may be a good idea to [download xQuartz](https://www.xquartz.org/) and install
```
# if Intel processor, look for intel-optimized packages first
conda config --add channels intel

# conda environments
conda install Cython         # good to have
conda install jupyter        # jupyter notebooks
```

```
# pip environments
pip3 install virtualenv     # virtual environments
pip3 install Cython         # good to have
pip3 install jupyter        # jupyter notebooks
```
   * #### See .bash_profile for aliases and paths for easy launching of jupyter notebooks, etc.

4. **BEFORE LOADING OTHER PACKAGES**, create a virtual environment for ML projects:  
**CONDA**
See [conda environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) for more
   1. Create a folder for your ml virtual environment (or, if you plan to do this on a per-project basis, create your project folder)
   2. In terminal, create your virtual environment
   ```
   # cd /path/to/directory
   # conda create --prefix /path/to/VIRTUALENV_NAME
   cd ~/dev/Python
   conda create --prefix /path/to/VIRTUALENV_NAME
   ```
   3. Activate your virtual environment
   ```
   # conda activate /path/to/VIRTUALENV_NAME
   conda activate /path/to/VIRTUALENV_NAME
   ```
   5. Prepare kernel for ipynotebooks (jupyter or spyder) . 
   (ref: https://anbasile.github.io/programming/2017/06/25/jupyter-venv/)
   ```
   conda install ipykernel
   ipython kernel install --user --name=VIRTUALENV_NAME
   ```
   **Jupyter**: Now you can start jupyter, create a new notebook and select the appropriate kernel from the drop-down.
   ![jupyter-dropdown](/assets/jupyter-dropdown.png)  
   ```
   # /path/to/VIRTUALENV_NAME
   /Users/USER_NAME/Python/VIRTUALENV_NAME/
   ```
   Then right-click on the console and restart the kernel
   6. To exit the virtual environment
   ```
   conda deactivate
   ```

**PIP**
See [venv](https://docs.python.org/3/library/venv.html) and [virtualenv](https://docs.python-guide.org/dev/virtualenvs/) for more
   1. Create a folder for your ml virtual environment (or, if you plan to do this on a per-project basis, create your project folder)
   2. In terminal, create your virtual environment
   ```
   # cd /path/to/directory
   # python3 -m venv VIRTUALENV_NAME
   cd ~/dev/Python
   python3 -m venv ml
   ```
   3. Activate your virtual environment
   ```
   # source /path/to/virtualenv_name/bin/activate
   source ./VIRTUALENV_NAME/bin/activate
   ```
   5. Prepare kernel for ipynotebooks (jupyter or spyder) . 
   (ref: https://anbasile.github.io/programming/2017/06/25/jupyter-venv/)
   ```
   pip3 install ipykernel
   ipython kernel install --user --name=VIRTUALENV_NAME
   ```
   **Jupyter**: Now you can start jupyter, create a new notebook and select the appropriate kernel from the drop-down.
   ![jupyter-dropdown](/assets/jupyter-dropdown.png)  
   ```
   # /path/to/virtualenv
   /Users/USER_NAME/Python/VIRTUALENV_NAME/bin/python
   ```
   Then right-click on the console and restart the kernel
   6. To exit the virtual environment
   ```
   deactivate
   ```

5. Install (applicable) packages 
**CONDA**
```
# Activate virtual environment
conda activate /path/to/VIRTUALENV_NAME

# if Intel processor, look for intel-optimized packages first
conda config --add channels intel

# standard packages
conda install numpy          # arrays/matrices
conda install pandas         # data frames
conda install scipy          # standard
conda install sympy          # symbolic math
conda install numba          # just-in-time compilation for numpy; parallelization
conda install matplotlib     # visualization
conda install seaborn        # visualization

# machine learning models
conda install scikit-learn        # machine learning
conda install statsmodels    # statistical modeling
conda install xgboost        # xgboost

# forecasting
conda install tslearn        # time series
conda install prophet        # forecasting with multiple seasonality

# web scraping
conda install beautifulsoup4 # for web scraping

# for nlp
conda install ntlk           # natural language toolkit
conda install textblob       # interface for ntlk
conda install spaCy          # fast nlp
conda install gensim         # topic modeling (may also want to install pattern https://www.clips.uantwerpen.be/pattern

# for tensorflow
conda install keras          # for prototyping tensorflow
conda install tensorflow     # tensorflow (needs to be v 1.10.0 for plaidml)
pip3 install plaidml-keras  # for non-Nvidia GPU acceleration
pip3 install plaidbench     # benchmarking plaidml
```  

**PIP**
Check for updated intel-optimized packages [here](https://software.intel.com/en-us/articles/installing-the-intel-distribution-for-python-and-intel-performance-libraries-with-pip-and)  

```
# Activate virtual environment
source /path/to/virtualenv_name/bin/activate

# standard packages
pip3 install intel-numpy    # arrays/matrices
pip3 install pandas         # data frames
pip3 install intel-scipy    # standard
pip3 install sympy          # symbolic math
pip3 install numba          # just-in-time compilation for numpy; parallelization
pip3 install matplotlib     # visualization
pip3 install seaborn        # visualization

# machine learning models
pip3 install statsmodels    # statistical modeling
pip3 install intel-scikit-learn   # machine learning
pip3 install sklearn        # machine learning
pip3 install xgboost        # xgboost

# forecasting
pip3 install tslearn        # time series
pip3 install prophet        # forecasting with multiple seasonality

# web scraping
pip3 install beautifulsoup  # for web scraping

# for nlp
pip3 install ntlk           # natural language toolkit
pip3 install textblob       # interface for ntlk
pip3 install spaCy          # fast nlp
pip3 install gensim         # topic modeling

# for tensorflow
pip3 install keras          # for prototyping tensorflow
pip3 install tensorflow     # tensorflow (needs to be v 1.10.0 for plaidml)
pip3 install plaidml-keras  # for non-Nvidia GPU acceleration
pip3 install plaidbench     # benchmarking plaidml
```

## Tensorflow Setup
6. When last checked (Jan 2019), the most recent tensorflow (1.12) does not work with the latest release of python (3.7).  Uncertain of current state (Sept 2019). 
Follow [this guide](https://github.com/plaidml/plaidml) for plaidml setup for Radeon GPU support.  Arranging versions between Keras, Tensorflow, and PlaidML will likely be a headache.

