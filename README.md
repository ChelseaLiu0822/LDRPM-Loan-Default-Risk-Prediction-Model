# LDRPM Loan Default Risk Prediction Model Project
The Loan Default Risk Prediction Model project addresses a critical challenge in consumer finance: accurately predicting loan default risks, particularly for clients lacking a substantial credit history.
## Data Source
**Home Credit - Credit Risk Model Stability, Kaggle**  
Link: https://www.kaggle.com/competitions/home-credit-credit-risk-model-stability/data  
Dataset File Size: 26.76GB  
Approximate Number of Records: ~1.5millions  
Original Data: /Data/OriginalData     
**Prediction Results**: /Data/*results.csv

## Objectives
1. Data preprocessing  
Processing missing value, duplicate values and encoding categorical variables (if necessary).
 
3. Exploratory data analysis  
We will conduct outlier detection, figure out the data trend, and conduct correlations analysis.

4. Feature engineering  
Identify and incorporate pertinent features, such as deposit amount and incoming debit card transactions amount. Then we may need to employ aggregation functions that will condense the historical records associated with each “case_id” into a single feature.

5. Feature Selection  
We will use some methods to examine the effect of feature importance and selecting only a certain number of the most important features on model performance.

6. Model Selection  
**references**:  
We will use different models, such as CatBoost, XGBoost and LightGBM. Then, we will evaluate the models by using AUC(Area Under the Receiver Operating Characteristic Curve). 

7. Model Tuning and Prediction  
Lastly, we will tune a model and make predictions on the test dataset using this tuned model. Then, we predict a probability for the target score.

## Data Explanation
Goal of this competition is to predict risk qualty of clients (or to be precise applications of cients), soclient and his/her application is entity (case id) for which your model predict probability of default (credit score).

(1) depth=0 (what we call static attributes) are attributes that are aggregated on case id level. Example can be age of client or gender, 1 record per 1 case id.
(2) depth=1, those are attributes where we have several records per client/appication. Example can be previous appications or loans incredit bureau register, each client can have from 0 to n records, Therefore. for one case id there might be several records. and to indeythem we use num group1
(3) depth=2: For some attributes with depth=1 we have more detailed information, for example for previous applications we have data abouiinstalments like date of pavments or days past due of each payments. lt means for each previous application, you can have 0..n recordsabout instalments/payments. And as an index is used num_group2

To sum up, 1 client can have several previous applications, and each of those previous applicaions can have several records aboutinstalments, payments, days past due, etc.
## How to run the code and download data :

1.You can directly click on open in colab button to run the code on google colab, since when we train the model, we used more than 29 G RAM, so we subscried to colab pro for getting more RAM, you might need more than default RAM to run the code.

2.The first cell of the code is to download data from kaggle, but if you facing problem like file expire(the file might expire three days after we update the link to the file ), you can use this link: https://www.kaggle.com/code/jetakow/home-credit-2024-starter-notebook/notebook
To the starter Notebook on kaggle and click on Copy&Edit,( you might need log into kaggle as well), after go to kaggle notebook, click on File -> Open in colab, and copy paste the first cell of code to replace our old first cell to get a new link to the file.

In this way you can download the data from kaggle.
