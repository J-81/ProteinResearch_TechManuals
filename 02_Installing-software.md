# Goals of this Manual
- Refer researchers to best practices for installing software
- Learn to use Anaconda for managing software installation

### Quick Terminology
- **Dependencies** : extra software that is required for your intended software to work or install
- **Compile** : take source code (often what you download from a website) and convert it into the working software
- **Environment** : collection of software that is used to achieve your analysis, this includes your language installations

## Installing Software : Considerations
Installing software is a common task in this research.  Much like installing a new machine in a wet lab, new pieces of software should be installed with a goal of allowing reproducible research using well-validated tools.

Some things to consider before installing any software:
- Is this tool limited to a certain environment? OS?
- Is there an article that is the literature link for this tool (not always present but needs to be included if it does).
  - If there is not an article, is this a tool that is commonly used (fastQC is an example of a tool with no article but considered a standard and accepted tool for NGS analysis)
- How can I ensure another researcher on a new machine can reproduce my analysis?

## Manual Approaches
  - Found on webpages from the developer of the software
  - An example of software with an easy manual installation for Windows 10:
    - [ChimeraX](https://www.rbvi.ucsf.edu/chimerax/download.html)

### Pros and Cons

- **Pros**:
  - Installation process maintained by Developer (likely latest version available, common installation issues documented)
  - Can be very straightforward (especially if GUI guided)
- **Cons**:
  - May rely on pre-requisite skills, especially for software that must be *compiled*
    - examples: using the command line, make, cloning a github repo
  - Can often result in more manual documentation to describe installation process
  - Installation process may not work as advertised if certain dependencies are not on your computer (and this is not always easy to resolve)

### Important Considerations For Documenting Manual Installations

- These should all be documented
  - Location of software
    - URL and access date
  - Version of software
  - OS software was installed on
  - Dependencies that were used during installation (include version numbers for these too)

## Anaconda Approach
  - "Anaconda Individual Edition is a free, easy-to-install package manager, environment manager, and Python distribution with a collection of 1,500+ open source packages with free community support. Anaconda is platform-agnostic, so you can use it whether you are on Windows, macOS, or Linux." - Anaconda [Docs](https://docs.anaconda.com/)

### Getting Started:
  - Great developer tutorial for installation and usage [here](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html)

### Pros and Cons
  - **Pros**:
    - Very easy to install new tools
    - Separate software environments
      - note: this can be very helpful when different tools require different dependencies (e.g. python2 vs python3)
    - Resolves dependencies automatically
      - This will tend to work very well for most tools
    - Documenting software may be as simple as sharing the .yml file
    - Integration with Jupyter
  - **Cons**:
    - Requires learning to use Anaconda (easy learning curve to start, moderate learning curve to use useful more advanced features)

  - Suggestions based on my experience
    - Learn to use conda environment files
      - These serve the dual purpose of documenting the software used as well as allows others to easily reproduce your software environment
    - If the "solving" step is taking longer than 30 minutes, there is likely an issue with your requested environment

### Example Environment File

filename: biopython_pandas.yml
``` yml
channels:
        - bioconda
        - conda-forge
        - defaults
dependencies:
        - biopython=1.77
        - python=3.6
        - pandas=1.0.5
        - jupyter
```
- This file installs the following:
  - python version 3.6
  - biopython (a python library)
  - pandas (a python library)
  - Jupyter (since the version is unspecified, Anaconda will retrieve the most recent version that is compatible with the other requested software)
- Usage
  > conda env create -f biopython_pandas.yml -n myBiopythonEnv
