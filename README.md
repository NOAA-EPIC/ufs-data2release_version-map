<h1 align="center">
Mapping UFS Weather Model Repository Tag Versions to Datasets
</h1>

<p align="center">
    <img src="images/header2.png" width="500" height="200">
    <img src="images/header.png" width="490" height="625">
</p>

<h5 align="center">
    
[Prerequisites](#Prerequisites) • [Dataset](#Dataset) • [Quick Start](#Quick-Start) • [Environment Setup](#Environment-Setup) • [Status](#Status)
 • [What's Included](#What's-Included) • [Documentation](#Documentation) • [References](#Reference(s))

</h5>

# About

__Introduction:__

Each unique code release version of NOAA's Unified Forecast System (UFS) weather model repository points to the datasets for which its code release version utilizes. These datasets include the input data required by the UFS weather model and the baseline data required for performing the regression tests of various UFS applications. The names of the datasets are timestamped and hard-coded into each unique code release version framework (aka "Github Tags"). This script will provide users/developers of the UFS weather model repository and its associated repositories a more user friendly way of determining which input and baseline datasets should be utilized for a given code release version of the UFS weather model repository.

__Purpose:__

The purpose of this script is to extract the unique names of the timestamped input and baseline datasets (e.g. input_data_YYYYMMDD) for a given UFS weather model repository's code release version. To avoid users/developers from searching for the hard-coded timestamped names of the datasets within the code for a given UFS weather model repository release version, the extraction and mapping of the timestamped datasets to UFS weather model code release version will provide a more user friendly way for users/ developers to determine which dataset is being utilized for a given code release version.

__Capabilities:__

This script will be able to perform the following actions:

- As release versions of the UFS weather model repository are being pushed out onto Github, this script will be able to extract each UFS weather model repository release version's name and access the scripts pointing to their corresponding timestamped input and baseline datasets directly from Github.

- Provide an information regarding a given Github repository such as:

  - Repository's name
  - Repository's description
  - Repository's created date.
  - Repository's number of tags
  - Repository's list of release versions/tags
  - Repository's number of forks
  - Repository's programming language
  - Repository's number of stars
  
- Provide a map/dictionary/table of the most recent UFS code release versions/tags to their corresponding UFS timestamped input and baseline datasets.

__Future Capabilities:__

With additional features added to this script, the script can be utilized for mapping the release versions of the Short Range Weather (SRW) model and Mid-Range Weather (MRW) model repository to their respective timestamped datasets.
Prerequisites:

This script utilizes the Github API. The Github API will cap a user from making N number of requests from its Github server within a narrow window of 1-2 hours, thus it is advise that the user of this script logs in with thier Github credentials when using the Github API to maximize the number of requests they can make from the Github server.

# Table of Contents
* [Prerequisites](#Prerequisites)
* [Dataset](#Dataset)
* [Quick Start](#Quick-Start)
* [Environment Setup](#Environment-Setup)
* [Status](#Status)
* [What's Included](#What's-Included)
* [Documentation](#Documentation)
* [References](#Creator(s))

# Prerequisites
* Python 3.9

# Dataset
* N/A

# Quick Start
* For demonstration purposes, refer to 'Read_TagVersion_Datasets_V4_022322.ipynb'

# Environment Setup:

* Install miniconda on your machine. Note: Miniconda is a smaller version of Anaconda that only includes conda along with a small set of necessary and useful packages. With Miniconda, you can install only what you need, without all the extra packages that Anaconda comes packaged with:
Download latest Miniconda (e.g. 3.9 version):

    * wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.9.2-Linux-x86_64.sh

* Check integrity downloaded file with SHA-256:

    * sha256sum Miniconda3-py39_4.9.2-Linux-x86_64.sh

Reference SHA256 hash in following link: https://docs.conda.io/en/latest/miniconda.html

* Install Miniconda in Linux:

    * bash Miniconda3-py39_4.9.2-Linux-x86_64.sh

* Next, Miniconda installer will prompt where do you want to install Miniconda. Press ENTER to accept the default install location i.e. your $HOME directory. If you don't want to install in the default location, press CTRL+C to cancel the installation or mention an alternate installation directory. If you've chosen the default location, the installer will display “PREFIX=/var/home//miniconda3” and continue the installation.

* For installation to take into effect, run the following command:

source ~/.bashrc

* Next, you will see the prefix (base) in front of your terminal/shell prompt. Indicating the conda's base environment is activated.

* Once you have conda installed on your machine, perform the following to create a conda environment:

    * To create a new environment (if a YAML file is not provided)

        * conda create -n [Name of your conda environment you wish to create]

(OR)

    * To ensure you are running Python 3.9:

        * conda create -n myenv Python=3.9

(OR)

* To create a new environment from an existing YAML file (if a YAML file is provided):

    * conda env create -f environment.yml

*Note: A .yml file is a text file that contains a list of dependencies, which channels a list for installing dependencies for the given conda environment. For the code to utilize the dependencies, you will need to be in the directory where the environment.yml file lives.

### Activate the new environment via:

conda activate [Name of your conda environment you wish to activate]

* Verify that the new environment was installed correctly via:

    * conda info --env

*Note:

* From this point on, must activate conda environment prior to .py script(s) or jupyter notebooks execution using the following command: conda activate
    * To deactivate a conda environment:
        * conda deactivate

### Link Home Directory to Dataset Location on RDHPCS Platform

* Unfortunately, there is no way to navigate to the "/work/" filesystem from within the Jupyter interface when working on the remote server, Orion. The best way to workaround is to create a symbolic link in your home folder that will take you to the /work/ filesystem. Run the following command from a linux terminal on Orion to create the link:

    * ln -s /work /home/[Your user account name]/work

* Now, when you navigate to the /home/[Your user account name]/work directory in Jupyter, it will take you to the /work folder. Allowing you to obtain any data residing within the /work filesystem that you have permission to access from Jupyter. This same procedure will work for any filesystem available from the root directory.

*Note: On Orion, user must sym link from their home directory to the main directory containing the datasets of interest.

### Open & Run Data Analytics Tool on Jupyter Notebook

* Open OnDemand has a built-in file explorer and file transfer application available directly from its dashboard via ...

Login to https://orion-ood.hpc.msstate.edu/

* In the Open OnDemand Interface, select Interactive Apps > Jupyter Notbook

### Additonal Information

To create a .yml file, execute the following commands:

* Activate the environment to export:

    * conda activate myenv

* Export your active environment to a new file:

    * conda env export > [ENVIRONMENT FILENAME].yml


# Status
[![Version badge](https://img.shields.io/badge/Python-3.9-blue.svg)](https://shields.io/)
[![Build badge](https://img.shields.io/badge/Build--gray.svg)](https://shields.io/)

# What's Included
Within the download, you will find the following directories and files:

* Data Analytics Tool:
    > Read_TagVersion_Datasets_V4_022322.ipynb
* List of Dependencies: 
    > environment.yaml

# Documentation

# References
* N/A

# Version:
* Draft as of 02/23/22

