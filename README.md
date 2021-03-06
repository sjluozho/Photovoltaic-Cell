<img src="./docs/image/PV_Cell_Logo.png" width="350" class="center">

# PVC
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://travis-ci.org/sjluozho/PV_Cell.svg?branch=master)](https://travis-ci.org/sjluozho/PV_Cell)
[![Coverage Status](https://coveralls.io/repos/github/sjluozho/PV_Cell/badge.svg?branch=master)](https://coveralls.io/github/sjluozho/PV_Cell?branch=master)

PVC is a group of four who dream of contributing to the clean energy technology. We developed a python package that can predict **Power Conversion Efficiency(PCE)** of an organic material in PV-Cell based on user's input molecular structure. The predicted model is built based on correlations between *PCE* and molecular features (bond type, functional group, heteroatom and etc.). All data is retrieved from The Harvard Clean Energy Project Database (HCEPDB). As our slogan said "STRONG!", we aimed at developing a powerful tool that provides practical information towards synthesizing new organic materials for OPVC.

## Use Cases
1. Extract molecular features (functional groups, chemical bonding and etc.) from given ``SMILE_str``.
2. Use various regression models to screen siginificant predictors from molecular features above that contribute to *PCE*.
3. Build up Artificial Neural Network(ANN) to connect selected molecular featrues and *PCE*.
4. (Future Work)Predict optimal structure that gives high PCE based on Terminal-Spacer-Core fragmented structures.

## Package Requirements
This package needs **RDkit** for molecular conversion and **Mordred** for descriptor calculation, **Pandas** for data management, **Scikit-learn** for standardisation and data set splitting, and **Keras** for the neural network building and training.

* rdkit
* keras
* scikit-learn
* mordred

All required software can be installed at the command line
 * `pip install -r requirements.txt`
 * `python setup.py install`
`pip` does not provide installation for rdkit. In the same environment, users need to install rdkit by,
 * `conda install -q -c rdkit rdkit`
after rdkit is ready, install mordred by,
 * `pip install mordred` 
 
## Organization of the  project

The project has the following structure:

    PV_Cell/
      |- README.md
      |- pvcell/
         |- __init__.py
         |- pvcell.py
         |- test/
            |- ...
      |- docs/
         |- Makefile
         |- conf.py
         |- image/
            |- ...
         |- tech_review.ppt/
         |- poster.pdf/
      |- examples/
         |-pvcell.ipynb/
      |- Reference/
         |- README.md
         |- literature.pdf/
      |- .gitignore
      |- setup.py
      |- .travis.yml
      |- .mailmap
      |- appveyor.yml
      |- requirements.txt
      |- environment.yml
      |- LICENSE
      |- Makefile


## Work Flow
<img src="./docs/image/WORKFLOW.png" width="350" class="center">


## Module code

We place all the module codes in the directory called `pvcell`. It contains modules
required for every step in the project, including: extracting chemical infomation, 
vaious regression model, ANN model and visualization module. Please see README file in 
the directory for more details. 


## Project Data

All the data used in this project are placed in the directory `database/`
(https://github.com/sjluozho/PV_Cell/tree/master/Database)recorded in csv
files. Users can call the data by this code:
    *data = pd.read_csv('../Database/HCEPD_100K.csv')*
In addition to the original data (*HCEPD_100K.csv*), we place some csv files that
contains raw chemical features extracted from this 100K data, and also the ready-to-use one
in `No_Missing_Value` folder.    


## Examples

This directory contains several Ipython Notebook that reads in some data, and run the modules in
this project as an demonstration. Users may find useful instruction and illustration of the codes
and procedures of our work.


## Style
Being checked by `pycodestyle` (formally named `pep8`), the whole package (`pvcell`) is `PEP8` compliant.


## Installation
A `PV_Cell/version.py` contains all of the information needed for the
installation and package dependencies.

## Licensing

For more details on the licensing document, please read:
[MIT](https://github.com/sjluozho/PV_Cell/blob/master/LICENSE)
