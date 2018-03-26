# 3X Data Mining

3X Data Mining is a data mining project created by 6 students completing their Masters in Data Science at the Bologna Business School

> The topic for 3X is Employee attrition. 
>The data has been taken from [IBM Employee HR Attrition Kaggle](https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset) 
 > The main Business problem that is being solved here is how can a system be created to help big companies control their attrition by understanding which employee could leave so as to provide him/her some incentives to stay back.
 
 The project members are
  - Mohammed Topiwalla
  - Sanchita Kumari
  - Patricia Londono
  - Vallerio Trotta
  - Millicent Otchere
  - Igor Pedevani

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

The slides are [here](IGORandMillicentWillgive.com)

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
* Link to Tableau workbook for EDA is [here](SanchitaWillGiveLinkToUpdate.com)

##### Feature Selection
> 3 Methods were employed for feature selection, first one was to use those variables which a model thought was relevant like a decision tree or SVM. link to code is [here](https://github.com/mmd52/3XDataMining/blob/master/Feature_Selection.ipynb)
> Second method was to use a backward elimination performed in statistics. link to output is [here](https://github.com/mmd52/3XDataMining/blob/master/SAS%20Feature%20Selection%20Logistic%20Model.pdf)
> Third method was to use a cfs subset evaluation algorithm performed in WEKA. Link to ouput is [here](https://github.com/mmd52/3XDataMining/blob/master/Data%20Mining%20Project%20Feature%20Selection%20Weka.xlsx)

##### Data Cleaning (Data balancing and one hot encoding)
> As our data is imabalanced we decided to oversample the minority class using a technique known as Synthetic minority oversampling technique or smote. The research paper for smote is [here](https://github.com/mmd52/3XDataMining/blob/master/SmotePaper.pdf)
> The code for SMOTE and one hot encoding is [here](https://github.com/mmd52/3XDataMining/blob/master/DataCleaning_And_Smote.ipynb)

##### Clustering
> Clustering was just done to see if our data falls in two perfect categories. The code is [here](https://github.com/mmd52/3XDataMining/blob/master/clustering3X.ipynb)

##### Modeling for prediction
In order to find a model which could help with the prediction process we ran several data mining models
* [Decision Tree and Random forest](https://github.com/mmd52/3XDataMining/blob/master/ModelingDtree_Final.ipynb)
* [Logistic Regression](https://github.com/mmd52/3XDataMining/blob/master/ModelingLogisticRegression_Final.ipynb)
* [Support Vector Machines](https://github.com/mmd52/3XDataMining/blob/master/ModelingSVM_Final.ipynb)
* [Artificial Neural Networks](https://github.com/mmd52/3XDataMining/blob/master/ANN.ipynb)

Summary:
| Model | Accuracy | ROC | KAPPA |
| ----- | ----- | ----- | ----- |
| Decision tree with variables selected from cfs subset eval | 84.23% | 0.61 | 0.25 |
| Random forest with variables selected from cfs subset eval | 87.77% | 0.61 | 0.25 |
| Logistic Regression with all the data | 87.5% | 0.65 | 0.397 |
| SVM with all the data | 82.0% | 0.59 | 0.23 |
| ANN | 73.5% | 0.68 | 0.41 |

>We achieved the best accuracy using random forest which is an ensemble of trees, However in a real life scenario we may need to explain the HR why are we saying someone is prone to leave in this case we will need to use a simple model like decision or logistic regression.

##### Conclusion
> We ended up creating an early warning system for our customer in order to help them predict if an employee has a possiblity of leaving the company or not
