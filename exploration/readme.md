###Notes on the Exploratory Reporting

This open source exploration utility is borrowed from the TDSP Team from Microsoft. I'm currently using it for our practicum project. The Jupyter notebook `Exploration.ipynb` will build interative visuals as detailed below. For detailed documentation see here: https://github.com/Azure/Azure-TDSP-Utilities
 

The `specs.yaml` file points to the data in the data prep folder. It specifies delimiters of the input data, variable types, target, etc.

```yaml
DataFilePath:
    ..\\data prep\\exercise01_flat.csv
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
