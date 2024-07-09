# AIBootcamp-Project2

Analyze historical NFL data.  We will classify teams into groups based on winning percentages and model the % chance of a particular team winning based on multiple factors (home/away, weather conditions, game location, typical location weather, record against opponent, etc.)

This project is presented in two stages and files.  
__Stage 1__ contains the data merging and clean up of our data sources for the full historical set of NFL data 2002-2023.  This full data set was used to classify the data to finding the teams with the higest winning percentage as well as show linear relationships between differnt attributes.  
__Stage__ 2 was created for predictive modeling.  This file mimics the merging and clean-up from stage 1, but removes the data associated with 2023 to provide an area for the team to test our model.


# Stage 1:  Data merging, Data Cleaning, and Data Classification
 

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
- Python installation
- Jupyter installation


## Install Libraries

pip install matplotlib scipy numpy

## Clone the repository

- Open a Terminal window and use `cd` commands to navigate to the directory where you would like to save your repository.

- Use the `git clone` command and the link you copied previously to clone the repository in the location you selected.

- Run all .ipynb files, except generation_prophet_compare_final.ipynb, using jupyter notebook, an anaconda dev setup may be preferable

- Run generation_prophet_compare_final.ipynb in a google colab workspace.  Upload the dfa-generation-levels-detail-cleanedup.csv found in the resources-jc folder when prompted.


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

- The highest score recorded by a team in our cleaned dataset was 63 points by the Raiders during a game in Dec 2023
- In actuality, the highest score by a single team from 2002-2023 was 70 by the Miami Dolphins 3 months previously in September of 2023.  However, some data points for that game were missing so it was removed. Underscoring the need to understand the data, and the impact of cleaning has on it.
- The chart shows the Patriots have the highest winning percentage, while the Browns have the least, by quite a margin
- A positive linear relationship exists between yards of offense and score
- This information could be helpful in estimating scores of each team in a game based on their average yards for last several games
- However, the r^2 value is only .398, meaning the two metrics have a moderate, but not strong relationship


# Stage 2:  Data merging, Data Cleaning, and Data Classification - Data only through 2022 to allow for prediction testing vs 2023 actuals


## Installation - A number of installations are needed to run the code necessary to complete this project 

import pandas as pd  
import numpy as np  
import matplotlib.pyplot as plt  
import seaborn as sns  
from sklearn.ensemble import RandomForestClassifier  
from sklearn.model_selection import train_test_split  
from sklearn.pipeline import Pipeline  
from sklearn.svm import SVC 

import warnings  
warnings.filterwarnings("ignore")  
pd.set_option('display.max_columns',None)

- [Python Documentation] (<https://docs.python.org/>)
- [Jupyter Notebook Documentation] (<https://jupyter-notebook.readthedocs.io/>)
- [Matplotlib Documentation] (<https://matplotlib.org/stable/index.html>)

### Prerequisites

- A computer running Windows, macOS, or Linux
- Administrator privileges on the computer
- Python installation
- Jupyter installation


## Install Libraries

pip install matplotlib scipy numpy

## Clone the repository

- Open a Terminal window and use `cd` commands to navigate to the directory where you would like to save your repository.

- Use the `git clone` command and the link you copied previously to clone the repository in the location you selected.

- Run all .ipynb files, except generation_prophet_compare_final.ipynb, using jupyter notebook, an anaconda dev setup may be preferable

- Run generation_prophet_compare_final.ipynb in a google colab workspace.  Upload the dfa-generation-levels-detail-cleanedup.csv found in the resources-jc folder when prompted.


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

- Given the extensive number of attributes in our data, only the more complex models were attempted
- Random Forest had the best model result, with test score of 81.1%
- The variable contributing the most to the outcome were Rushing attempts, time of possession, and passing attempts
- Given the extensive game details in the data set, there is definitely an X-factor in determining a win
- When applying Week 1 2023 game details (known items before the game started) the model predicted the correct winner 53.8% of the time
- 53.8% is less than the current prediction rate in Vegas which stands right around 65% accuracy
