Cardiovascular Disease EDA

In this project, an exploratory data analysis (EDA) of a cardiovascular health dataset is presented. The aim is to investigate biometric and lifestyle-related parameters and their connection to the possibility of cardiovascular disease.

The data contains the records of more than 68000 patients, the features being age (calculated in years after converting days), gender, height, weight, systolic blood pressure, diastolic blood pressure, cholesterol level, glucose level, smoking, alcohol consumption, and physical activity. The target variable is named cardio and takes the value 1 in case a patient is diagnosed with cardiovascular disease.

In the preprocessing step, columns that were not needed like id and Unnamed: 0 were dropped. The days in the age column were transformed into years to allow easier interpretation. Clearly implausible values of height, weight, and blood pressure were eliminated on medically realistic limits.

There are some important steps, which are involved in the analysis. Initially, a univariate analysis was done through the histogram and KDE curves to get insights into the distributions of continuous variables, such as age, weight, and blood pressure. Count plots were used to examine the categorical features including gender, cholesterol, and smoking status to see how these variables were distributed in the data. Bivariate examination used boxplots to compare numeric attributes amid cardiovascular disease and without cardiovascular disease patients and showed that patients with cardiovascular disease (heart disease) tend to be older, heavier, and have higher blood pressure. Also, a correlation matrix was generated to check the relationships among the features revealed moderate correlations of the target variable with systolic blood pressure, age, and cholesterol.

This repository contains the original dataset, a cleaned copy of it, the Jupyter notebook with the entire EDA workflow, a requirements.txt depencency file, and this README. To execute the analysis, letters needed to run the analysis are installed via pip install -r requirements.txt, and then the notebook file (Cardio_EDA.ipynb) is opened in Jupyter.

