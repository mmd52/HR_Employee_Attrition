# IBM HR Employee Attrition

>The data has been taken from [IBM Employee HR Attrition Kaggle](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset) 
 > The main Business problem that is being solved here is how can a system be created to help big companies control their attrition by understanding which employee could leave so as to provide him/her some incentives to stay back.

# How to Navigate ?
Note: *3X* project uses only Python 3.X and Tableau 10.0 and above for analysis

* PPT - Contains Business problem and conversion to DS problem
* Tableau - EDA Insights
* Feature Selection
* Various classification models
* Final PPT - Interpretation
* Report


### Installation
```sh
$ pip install imblearn
# For Smote
```


##### Problem Statement

> Our client is ABC a leading firm and is doing well in the sector. It is recently facing a steep increase in its employee attrition . Employee attrition has gone up from 14% to 25% in the last 1 year . We are asked to prepare a strategy to immediately tackle this issue such that the firm’s business is not hampered and also to propose an efficient employee satisfaction program for long run. Currently, no such program is in place . Further salary hikes are not an option.

* The slides are [here](https://github.com/mmd52/3XDataMining/blob/master/Attrition_Management.pdf)

##### Exploratory Data analysis
* Data is imbalanced by class we have 83% who have not left the company and 17% who have left the company
* The age group of IBM employees in this data set is concentrated between 25-45 years
* Attrition is more common in the younger age groups and it is more likely with females As Expected it is more common amongst single Employees
* People who leave the company get lower opportunities to travel the company
* People having very high education tend to have lower attrition
* The correlation plot was as expected
* Link to eda workbook in python is [here](https://github.com/mmd52/3XDataMining/blob/master/EDA_UnderstandingData.ipynb)
* From the Tableau plots we can conclude that below mentioned category are having higher attrition rate:
* * Sales department among all the departments
* * Human Resources and Technical Degree in Education
* * Single’s in Marital status (Will not use this due to GDPR)
* * Male in comparison to females in Gender (Will not use this due to GDPR)
* * Employee with job satisfaction value 1
* * Job level 1 in job level
* * Life balance having value 1
* * Employee staying at distant place
* * Environment Satisfaction value 1
* Link to Tableau workbook for EDA is [here](https://github.com/mmd52/3XDataMining/blob/master/IBM_Attrition.twbx)
* Link to Tableau output is [here](https://github.com/mmd52/3XDataMining/blob/master/IBM_Attrition.pdf)

##### Data Cleaning (Data balancing and one hot encoding)
> As our data is imabalanced we decided to oversample the minority class using a technique known as Synthetic minority oversampling technique or smote. The research paper for smote is [here](https://github.com/mmd52/3XDataMining/blob/master/SmotePaper.pdf)
> The code for data cleaning is [here](https://github.com/mmd52/3XDataMining/blob/master/DataCleaning.ipynb)
> The smote code is applied on classification training sets. For example [Decision Tree](https://github.com/mmd52/3XDataMining/blob/master/ModelingDtree_Final.ipynb)

##### Modeling for prediction
In order to find a model which could help with the prediction process we ran several data mining models
* [Decision Tree and Random forest](https://github.com/mmd52/3XDataMining/blob/master/ModelingDtree_Final.ipynb)
* [Logistic Regression](https://github.com/mmd52/3XDataMining/blob/master/ModelingLogisticRegression_Final.ipynb)
* [Support Vector Machines](https://github.com/mmd52/3XDataMining/blob/master/ModelingSVM_Final.ipynb)
* [Artificial Neural Networks](https://github.com/mmd52/3XDataMining/blob/master/ANN.ipynb)
* [Extreme Gradient Boosting](https://github.com/mmd52/3XDataMining/blob/master/XGBoost.ipynb)
* [Stacking a XGBOOST on a decsion tree](https://github.com/mmd52/3XDataMining/blob/master/XGBoost_Stacker.ipynb)

Summary:
> We achieved the best accuracy of 88.31% using XGBOOST with the help of smote data.
> However logistic regression was not far behind with the accuracy of 88.04%.

##### Conclusion
> We ended up creating an early warning system for our customer in order to help them predict if an employee has a possiblity of leaving the company or not