# LDRPM Loan Default Risk Prediction Model Project
The Loan Default Risk Prediction Model project addresses a critical challenge in consumer finance: accurately predicting loan default risks, particularly for clients lacking a substantial credit history.
## Data Source
**Home Credit - Credit Risk Model Stability, Kaggle**  
Link: https://www.kaggle.com/competitions/home-credit-credit-risk-model-stability/data  
Dataset File Size: 26.76GB  
Approximate Number of Records: ~1.5millions  
Original Data: /Data/OriginalData  

## Objectives
1. Data preprocessing  
Processing missing value, duplicate values and encoding categorical variables (if necessary).  
code:  DataPreprocessing.ipynb  
results:CleaningData.zip  
2. Exploratory data analysis  
We will conduct outlier detection, figure out the data trend, and conduct correlations analysis.

3. Feature engineering  
Identify and incorporate pertinent features, such as deposit amount and incoming debit card transactions amount. Then we may need to employ aggregation functions that will condense the historical records associated with each “case_id” into a single feature.

4. Feature Selection  
We will use some methods, such as PCA(Principal Component Analysis) to examine the effect of feature importance and selecting only a certain number of the most important features on model performance.

5. Model Selection  
**references**:  
We will use different models, such as CatBoost, XGBoost and LightGBM. Then, we will evaluate the models by using a gini stability metric. First, we get the weekly gini scores:  
gini= 2* AUC -1 	   (1)  
Fitting the weekly gini scores, we obtain a linear regression a*x+b, which aids in obtaining the stability metric:  
Stability metric = mean(gini) + 88.0*min(0,a) - 0.5 * std(residuals)	   (2)  
Then by performing cross validation or employing metrics such as Mean Absolute Error (MAE) and Root Mean Square Error (RMSE), we will determine the best untuned model.

6. Model Tuning and Prediction  
Lastly, we will tune a model and make predictions on the test dataset using this tuned model. Then, we predict a probability for the target score.
