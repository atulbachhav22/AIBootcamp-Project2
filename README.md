# AIBootcamp-Project2

Analyze historical NFL data.  We will classify teams into groups based on winning percentages and model the % chance of a particular team winning based on multiple factors (home/away, weather conditions, game location, typical location weather, record against opponent, etc.)

This project is presented in two stages and files.  
__Stage 1__ contains the data merging and clean up of our data sources for the full historical set of NFL data 2002-2023.  This full data set was used to classify the data to finding the teams with the higest winning percentage as well as show linear relationships between differnt attributes.  
__Stage__ 2 was created for predictive modeling.  This file mimics the merging and clean-up from stage 1, but removes the data associated with 2023 to provide an area for the team to test our model.


## Stage 1:  Data merging, Data Cleaning, and Data Classification

## Table of Contents

- [Installation](#installation)
  - [Prerequisites](#prerequisites)
  - [Install Python](#install-python)
  - [Install Jupyter Notebook](#install-jupyter-notebook)
  - [Install Libraries](#install-libraries)
- [Usage](#usage)
  - [Running Jupyter Notebook](#running-jupyter-notebook)
  

## Installation - A number of installations are needed to run the code necessary to complete this project 

import pandas as pd  
import numpy as np  
import matplotlib.pyplot as plt  
import seaborn as sns

import warnings  
warnings.filterwarnings("ignore")  
pd.set_option('display.max_columns',None)

- [Python Documentation] (<https://docs.python.org/>)
- [Jupyter Notebook Documentation] (<https://jupyter-notebook.readthedocs.io/>)
- [Matplotlib Documentation] (<https://matplotlib.org/stable/index.html>)

### Prerequisites

- A computer running Windows, macOS, or Linux
- Administrator privileges on the computer

### Install Python

1. Download the latest version of Python from the official [Python website](https://www.python.org/downloads/).
2. Run the installer and follow the instructions. Make sure to check the option to add Python to your PATH.

To verify the installation, open a terminal or command prompt and run:

python --version

## Install Jupyter Notebook

pip install notebook

## Install Libraries

pip install matplotlib scipy numpy

## Clone the repository

- Open a Terminal window and use `cd` commands to navigate to the directory where you would like to save your repository.

- Use the `git clone` command and the link you copied previously to clone the repository in the location you selected.

- Run all .ipynb files, except generation_prophet_compare_final.ipynb, using jupyter notebook, an anaconda dev setup may be preferable

- Run generation_prophet_compare_final.ipynb in a google colab workspace.  Upload the dfa-generation-levels-detail-cleanedup.csv found in the resources-jc folder when prompted.

## Running Jupyter Notebook

jupyter notebook

## Sources
- [NFL Game Stats](https://www.kaggle.com/datasets/cviaxmiwnptr/nfl-team-stats-20022019-espn?select=nfl_team_stats_2002-2023.csv)
- [NFL Stadium Data](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data?select=nfl_stadiums.csv)
- [NFL Team Data](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data?select=nfl_teams.csv)
- [charting tools](https://www.shanelynn.ie/bar-plots-in-python-using-pandas-dataframes/)
- [stacked to full bar chart](https://www.shanelynn.ie/bar-plots-in-python-using-pandas-dataframes/)
- [secondary axis](https://stackoverflow.com/questions/46063379/pandas-secondary-axis)
- [Percentage format](https://saturncloud.io/blog/how-to-format-certain-floating-dataframe-columns-into-percentage-in-pandas/)
- [README.md formatting](https://medium.com/analytics-vidhya/writing-github-readme-e593f278a796)  

## Findings

- XXXXXXXXX
