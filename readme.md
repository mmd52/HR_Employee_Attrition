# IBM HR Employee Attrition

>The data has been taken from [IBM Employee HR Attrition Kaggle](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset) 
 > The main Business problem that is being solved here is how can a system be created to help big companies control their attrition by understanding which employee could leave so as to provide him/her some incentives to stay back.

# How to Navigate ?
Note: *3X* project uses only Python 3.X and Tableau 10.0 and above for analysis

* PPT - Contains Business problem and conversion to DS problem
* Tableau - EDA Insights
* Feature Selection - Some work in Weka (The output is recorded in the excel file)
* Various classification models
* Final PPT - Interpretation
* Report - duh!


### Installation
```sh
$ pip install imblearn
# For Smote
```


##### Problem Statement

> Our client is IBM a leading firm and is doing well in the sector. It is recently facing a steep increase in its employee attrition . Employee attrition has gone up from 14% to 25% in the last 1 year . We are asked to prepare a strategy to immediately tackle this issue such that the firm’s business is not hampered and also to propose an efficient employee satisfaction program for long run. Currently, no such program is in place . Further salary hikes are not an option.

* The slides are [here](https://github.com/mmd52/3XDataMining/blob/master/Attrition%20Management.pdf)
* The Report is [here](https://github.com/mmd52/3XDataMining/blob/master/3x.pdf)

##### Exploratory Data analysis
* Data is imbalance by class we have 83% who have not left the company and 17% who have left the company
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

##### Feature Selection
> 3 Methods were employed for feature selection, first one was to use those variables which a model thought was relevant like a decision tree or SVM. link to code is [here](https://github.com/mmd52/3XDataMining/blob/master/Feature_Selection.ipynb)
> Second method was to use a backward elimination performed in statistics. link to output is [here](https://github.com/mmd52/3XDataMining/blob/master/SAS%20Feature%20Selection%20Logistic%20Model.pdf)
> Third method was to use a cfs subset evaluation algorithm performed in WEKA. Link to ouput is [here](https://github.com/mmd52/3XDataMining/blob/master/Data%20Mining%20Project%20Feature%20Selection%20Weka.xlsx)

##### Data Cleaning (Data balancing and one hot encoding)
> As our data is imabalanced we decided to oversample the minority class using a technique known as Synthetic minority oversampling technique or smote. The research paper for smote is [here](https://github.com/mmd52/3XDataMining/blob/master/SmotePaper.pdf)
> The code for SMOTE and one hot encoding is [here](https://github.com/mmd52/3XDataMining/blob/master/DataCleaning_And_Smote.ipynb)

##### Clustering
> Clustering was just done to see if our data falls in two perfect categories. The code is [here](https://github.com/mmd52/3XDataMining/blob/master/Clustering3XFinal.ipynb)

##### Association
* Association rule mining was just done to see if our data has some patterns (Association was done in weka). The output is [here](https://github.com/mmd52/3XDataMining/blob/master/AssociationWekaOutput.md)
* Code to prepare its data is [here](https://github.com/mmd52/3XDataMining/blob/master/DataCleaning_ForAssociation.ipynb)

##### Modeling for prediction
In order to find a model which could help with the prediction process we ran several data mining models
* [Decision Tree and Random forest](https://github.com/mmd52/3XDataMining/blob/master/ModelingDtree_Final.ipynb)
* [Logistic Regression](https://github.com/mmd52/3XDataMining/blob/master/ModelingLogisticRegression_Final.ipynb)
* [Support Vector Machines](https://github.com/mmd52/3XDataMining/blob/master/ModelingSVM_Final.ipynb)
* [Artificial Neural Networks](https://github.com/mmd52/3XDataMining/blob/master/ANN.ipynb)
* [Extreme Gradient Boosting](https://github.com/mmd52/3XDataMining/blob/master/XGBoost.ipynb)
* [Stacking a XGBOOST on a decsion tree](https://github.com/mmd52/3XDataMining/blob/master/XGBoost_Stacker.ipynb)

Summary:
* Decision tree with smote dataset 2 ACC-> 92.22% ROC-> 0.92 KAPPA-> 0.84 
* Random forest with entire dataset  ACC-> 87.72% ROC-> 0.59 KAPPA-> 0.26
* Logistic Regression with entire dataset  ACC-> 88.04% ROC-> 0.67 KAPPA-> 0.42
* SVM   ACC-> 83.9% ROC-> 0.58 KAPPA-> 0.19 
* ANN   ACC-> 85.86% ROC-> 0.64 KAPPA-> 0.33
* XGBOOST with smote dataset 1 acc-> 91.41% ROC-> 0.87 KAPPA-> 0.74

> We achieved the best accuracy using Decision tree with the help of smote data.
> However we believe that with more data XGBoost can outperfrom decision tree.

##### Conclusion
> We ended up creating an early warning system for our customer in order to help them predict if an employee has a possiblity of leaving the company or not
