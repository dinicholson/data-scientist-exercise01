# Model Summary

### Overview
A total of 13 features were explored relating to the demographic makeup of individuals in the census sample data (n=48,841). Using 10 variables, the final model classifies individuals as having an income greater or less than $50,000 with an accuracy of 85.4%. 

### Exploration 
The visualization below plots age against hours per week while delineating target events (green for over $50k and blue for under $50k). Intuitively, it reveals where we might find individuals making more than $50k per year: between 25 and 55 years of age and between 35 and 60 hours worked. Individuals working more than 50 hours per week make more than $50k at a rate of 43% (compared to rate of 24% for the entire sample). 

![alt text](https://github.com/dinicholson/data-scientist-exercise01/blob/master/summary/visuals/age_hrsWorked_target.PNG)

The clustering of individuals at 40, 45, 50, and 60 hour work weeks is likely do to self-reporting approximate hours--these workers also appear to take home higher incomes. This insight informed the addition of new variable that bins hours worked per week according to these commonly reported values, though it’s not as predictive as the raw variable. Provided that the data is available, an interesting follow up might be to investigate the likelihood that the individuals reporting weekly hours at these “round” values are salaried, and whether being salaried (as compared to hourly) is predictive of higher incomes.  

Education is one of the most telling variables in the model. As visualized below, there are stark contrasts in one’s likelihood to make more than $50k across education levels. 

![alt text](https://github.com/dinicholson/data-scientist-exercise01/blob/master/summary/visuals/education_vs_target.PNG)

Here is an overall look at the ranking of features available for prediction in terms of their linear relationship to the target variable (making over $50k).

![alt text](https://github.com/dinicholson/data-scientist-exercise01/blob/master/summary/visuals/ranked_variables.PNG)

### Results & Takeaways

While the final model provides a classification accuracy of 85.4%, there is room to drop variables if a simpler model is desired. The variables working class, sex, and binned hrs/week can be left out of the set of predictors with very small reductions in predictive accuracy.

In looking at the model parameters, marital status shows some of the largest effects. For example those who are married are much likelier to have an income greater than $50k, compared to those who are single, separated, widowed, or divorced. Individuals working as tech support, specialist professionals, and executives are also likelier to earn more than 50k than individuals working in other occupations, holding all else constant. Gender shows a small effect--men are 1.15 times as likely to make over 50k compared to women, all else being constant.

Of the categorical variables, education represents the largest effect. All else held constant, for each one unit increase in the level of education (i.e. from bachelor’s to master’s), the odds that an individual will earn more than $50k increases by 1.29.



### Appendix


__Final Model__  
Numeric: age, education_num, capital_gain, capital_loss, hours_week  
Categorical: martital_status, occupation, sex, workclass, hours_week_5  
AUC: 0.905288876345  
Accuracy: 0.854657113613  
No. of Parameters: 39  

#List of Parameters

| parameters                                            | coeff     |
|-------------------------------------------------------|-----------|
| C(hrs_salaried_5, Treatment(reference="other"))[T.40] |  0.059129 |
| C(hrs_salaried_5, Treatment(reference="other"))[T.45] |  0.515756 |
| C(hrs_salaried_5, Treatment(reference="other"))[T.50] |  0.644978 |
| C(hrs_salaried_5, Treatment(reference="other"))[T.60] | -0.004340 |
| C(marital_status)[T.Married-AF-spouse]                | 1.861631  |
| C(marital_status)[T.Married-civ-spouse]               | 1.864793  |
| C(marital_status)[T.Married-spouse-absent]            | 0.405229  |
| C(marital_status)[T.Never-married]                    | -0.782984 |
| C(marital_status)[T.Separated]                        | -0.862578 |
| C(marital_status)[T.Widowed]                          | -0.420026 |
| C(occupation)[T.Adm-clerical]                         | 0.146397  |
| C(occupation)[T.Armed-Forces]                         | 0.468383  |
| C(occupation)[T.Craft-repair]                         | 0.110841  |
| C(occupation)[T.Exec-managerial]                      | 0.686617  |
| C(occupation)[T.Farming-fishing]                      | -0.663996 |
| C(occupation)[T.Handlers-cleaners]                    | -0.240038 |
| C(occupation)[T.Machine-op-inspct]                    | -0.408008 |
| C(occupation)[T.Other-service]                        | -0.815793 |
| C(occupation)[T.Priv-house-serv]                      | -0.591623 |
| C(occupation)[T.Prof-specialty]                       | 0.763983  |
| C(occupation)[T.Protective-serv]                      | 0.762688  |
| C(occupation)[T.Sales]                                | 0.189691  |
| C(occupation)[T.Tech-support]                         | 0.850029  |
| C(occupation)[T.Transport-moving]                     | -0.151300 |
| C(sex)[T.Male]                                        | 0.139320  |
| C(workclass)[T.Federal-gov]                           | 0.553296  |
| C(workclass)[T.Local-gov]                             | 0.064974  |
| C(workclass)[T.Never-worked]                          | -0.005057 |
| C(workclass)[T.Private]                               | 0.293434  |
| C(workclass)[T.Self-emp-inc]                          | 0.646786  |
| C(workclass)[T.Self-emp-not-inc]                      | -0.124806 |
| C(workclass)[T.State-gov]                             | -0.140566 |
| C(workclass)[T.Without-pay]                           | -0.185247 |
| Intercept                                             | -3.943043 |
| age                                                   | 0.022989  |
| capital_gain                                          | 0.000282  |
| capital_loss                                          | 0.000657  |
| education_num                                         | 0.260364  |



![alt text](https://github.com/dinicholson/data-scientist-exercise01/blob/master/summary/visuals/roc_curve.PNG)



































