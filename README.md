# Geospatial Socioeconomic Mobility by Community

Final Report [here](https://github.com/francisfjin/geospatial_socioeconomic_mobility/blob/main/FinalReport.pdf) or check out the [website!](https://francisfjin.github.io/geospatial-classification/)

Main script: [finalproject.ipynb](https://github.com/francisfjin/Geospatial_SocioeconomicMobility/blob/main/finalproject.ipynb)

## Topic

Project using Classification machine learning methods to address the geographical variations in socioeconomic mobility amongst children in minority communities across America. The model predicts the level of future socioeconomic mobility using a variety of social, educational, and economic attributes, and highlights the most important features contributing to successful upward mobility, while deploying interactive visualizations with Plotly to portray results. 

![image map](https://github.com/francisfjin/Geospatial_SocioeconomicMobility/blob/main/images/map.png)

## Data

Source: [Opportunity Insights](https://opportunityinsights.org/data/).

[Neighborhood Characteristics by Commuting Zone](https://github.com/francisfjin/Geospatial_SocioeconomicMobility/blob/main/CZ_neighborhoodcharacteristicsbycsv.csv)

[Geography of Mobility: Commuting Zone Characteristics - Definitions and Data Sources](https://github.com/francisfjin/Geospatial_SocioeconomicMobility/blob/main/online_data_tables-8.xls)

## Data Cleaning and Pre-processing

Methods: Importing XLS and CSV files, slicing excel sheets, filtering for minority communities, cleaning and renaming columns, grouping by and merging on Commuting Zone, a unique numeric identifier for communities ranging across the entire United States. Resulting dataset has 40 features and 500 entries. 

Target variable is a metric to measure socioeconomic mobility, deemed “Absolute Upward Mobility” and engineered from the original [paper](https://opportunityinsights.org/paper/land-of-opportunity/) from Opportunity Insights. Defined as the mean future income rank of children whose parents are at the 25th percentile of the national parent income distribution. 


## EDA

Investigates statistical correlation of features vs. target variable with correlation tables and heat maps using Seaborn Library. 

Investigates distribution of target variable using distribution plots, histograms, and CDF plots using Matplotlib library. 

## Feature Selection

Removes duplicated features and uses Sklearn library's Mutual Information Classification to create feature importance rankings for both Binary and Multi-label Classification. Target variable for Binary is split into labels 1 for success and 0 for failure. Target variable for Multi-label is split by quartiles into Low, Medium, High, and Excellent for upward mobility. 

## Model Selection and Results

Binary Classification
- Logistic Regression with 5-fold Cross-Validation, Elastic Net Regularization, Hyper-parameter Tuning, Standard Scaler. (~90%/~85% accuracy)
- Ensemble methods: Random Forest Classifier, Gradient Boosting Classifier
- GridSearchCV hyper-parameter tuning

K-Means Clustering
- Unsupervised Learning Method to find optimal number of clusters using elbow method to inform multi-label classification

Multi-Label Classification
- Logistic Regression with 10-fold Cross-Validation, Elastic Net Regularization, Hyper-parameter Tuning, Standard Scaler (~80%/75% accuracy)
- Gradient Boosting Classifier
- GridSearchCV hyper-parameter tuning

## Visualizations

[Geopy](https://geopy.readthedocs.io/en/stable/) Library for longitude/latitude coordinate identification for communities

[Plotly](https://plotly.com/) Scattergeo for interactive map of USA of results
















