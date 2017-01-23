###Notes on the Exploratory Reporting

This open source data exploration utility is borrowed from Microsoft's TDSP Team. Truly an awesome tool--I'm currently using it for our IAA practicum project. The Jupyter notebook `Exploration.ipynb` will build interative visuals as described below. For detailed documentation see here: https://github.com/Azure/Azure-TDSP-Utilities.

Partitioning was completed before exploration, as some of the interactive visualizations explore relationships to the target variable. To avoid introducing bias, only the training set was used for exploration. 

The `specs.yaml` file points to the data in the data prep folder. It specifies delimiters of the input data, variable types, the target, etc. It looks like this:

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

