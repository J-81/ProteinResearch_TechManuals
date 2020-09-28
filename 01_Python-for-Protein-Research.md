# Goals of this Manual
- Direct new programmers to resources for getting starting with Python
- Describe useful packages for protein research
- Describe some tips related to managing Python code
## Getting Started

Software carpentry is an excellent source of hands-on tutorials for a variety of useful skills.
This includes a great beginner python tutorial.

Link to Hands-on Tutorial: https://swcarpentry.github.io/python-novice-inflammation/

**Note**: I highly suggest following the setup instructions using Anaconda and Jupyter notebook.  While you may already have Python installed on your system,  these tools simplify a lot of common processes in the research lab.

After completing this tutorial, you should be able to do the following:
1. Read and write basic python scripts
1. Understand approaches for debugging
1. Use Anaconda to install software using the Navigator Graphical User Interface (GUI)
1. Perform interactive programming in a Jupyter notebook
## Useful Packages
- It is always better to use a well-documented library.  While writing things from scratch is sometimes necessary, leveraging existing libraries will cut down on debugging time and documentation time (as someone reading your code can refer to the library documentation for how the libraries work and you can focus on documenting what you are using the libraries for).


- Biopython
    - http://biopython.org/DIST/docs/tutorial/Tutorial.html
    - Invaluable large set of tools
    - Often used examples include sequence alignment, downloading data from common databases, parsing common proteins related file formats
    - **Before you attempt to write something from scratch, see if it already exists in Biopython**
    - The tutorial is also well-written (I tend to use this document as a manual which works well if you know the phrasing for what you are tyring to perform).

- scikit-learn
    - https://scikit-learn.org/stable/
    - Library including machine-learning training, model assessment, clustering and classification
    - Very straighforward in my experience, most documentation includes easy to modify examples

- pandas
    - https://pandas.pydata.org/
    - Excellent library for working with tabular data (i.e. csv files)
    - *You used numpy in the software carpentry tutorial, pandas uses alot of numpy under-the-hood and tends to be a lot nicer to use compared to numpy directly*
    - The dataframe and series objects tend to be directly compatible with many other very useful packages including scikit-learn and seaborn

- seaborn
    - https://seaborn.pydata.org/
    - Great for visualizing data faster and more elegantly than matplotlib
