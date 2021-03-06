[Descriptive Stats and Visuals](https://htmlpreview.github.io/?https://github.com/dinicholson/data-scientist-exercise01/blob/master/exploration/Exporatory%20Reporting%20Utility/Descriptive%20Stats%20and%20Visuals.html)
(html version of the python notebook for a quick look at the most relevant visuals that informed the modeling) 



###Notes on the Exploratory Reporting Utility

This open source data exploration utility is borrowed from Microsoft's TDSP Team. Truly an awesome tool--I'm currently using it for our IAA practicum project. The Jupyter notebook `Exploratory Reporting Utility/Exploration.ipynb` will build interative visuals that explore that explore simple stats, relationships between predictors, and relationships between predictors and the target. For detailed documentation see here: https://github.com/Azure/Azure-TDSP-Utilities. (In order to use the visuals interactively, you'll have to fork and clone this repository and run the notebook).

Partitioning was completed before exploration, as some of the interactive visualizations explore relationships to the target variable. To avoid introducing bias, only the training set was used for exploration. 


###If you fork and clone this repo to run the interactive visuals locally...

Be sure to change file paths in the global settings in the `Exploration.ipynb` file.  
The `specs.yaml` file points to the training data. It specifies delimiters of the input data, variable types, the target, etc. It looks like this:

```yaml
DataFilePath:
    ..\\partition\\train.csv
HasHeader:
    Yes
Separator:
    ','
CategoricalColumns:
    - workclass
    - education_level
    - marital_status
    - occupation
    - race
    - sex
    - country
    - over_50k
NumericalColumns:
    - age 
    - education_num
    - capital_gain
    - capital_loss
    - hours_week
Target:
    over_50K

```

