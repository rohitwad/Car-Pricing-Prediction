# Car-Pricing-Prediction
<b>Problem Statement</b>: Build a multiple linear regression model for the prediction of car prices


<br/><b> 1) Data gathering</b>
<br/>&emsp;Train & Test csv files were provided
<br/><b> 2) Feature Engineering</b>
<br/> &emsp;i) Handling Categorical columns - Fueltype, aspiration, doornumber, enginelocation, drivewheel, enginetype, cylindernumber, carbody, fuelsystem
<br/> &emsp;ii) Data cleaning - correct the spelling mistakes 
<br/> &emsp;iii) Considering only company name for regression


<br/> Splitting Train & Test Set
<br/> Performing MinMax scaling

<br/> Applying RFE-Recursive Feature Elimination
<br/> &emsp; - It helps in identifying significant columns along with their ranking importance

Using statsmodels.api to add constant to model
Find Variance Inflation Factor (VIF)
Remove column having VIF > 5
Fit the model again
Repeat till VIF is less than 5 for all columns
Now check if any column has p-value > 0.05
Remove that particular column 
Fit the model again
Repeat till p-value is less than 0.05 for all columns


<br/> &emsp;iii) Considering only company name for regression
<br/> <b> 3) Feature Selection</b>
<br/> &emsp;Dropping columns : ID & Is_Lead (y), not required in model building
<br/><b> 4) Model Creation</b>
<br/> &emsp; i) For Logistic Regression, we perform steps 2 & 3 : Feature Engg & Feature Selection
<br/> &emsp; ii) For CatBoost Classifier, 
<br/> &emsp; &emsp; -> we do not perform data pre-processing steps here like handling categorical variables of below columns : 
<br/> &emsp; &emsp; &emsp;"Gender","Region_Code","Occupation","Channel_Code","Credit_Product","Is_Active"
<br/> &emsp; &emsp; -> Missing values/Nan values can be handled internally by algo, but still we handled Nan values 
<br/><b> 5) Testing the model</b>
<br/> &emsp; i) Local Accuracy:
<br/> &emsp; &emsp; 1) Logistic Regression - 77.65
<br/> &emsp; &emsp; 2) CatBoost Classifier - 79.36
<br/> &emsp; ii) AnalyticsVidhya Accuracy:
<br/> &emsp; &emsp; 1) Logistic Regression - With Percentage - Private Score : 0.727
<br/> &emsp; &emsp; 2) Catboost Classifier - 1000 iterations - Private Score : 0.783
<br/> &emsp; &emsp; Public Rank : 1727 
<br/> &emsp; &emsp; Public Leaderboard: 0.7319135583
<br/> &emsp;Metrics : Confusion matrix & ROC curve
<br/> <b> 6) Deployment</b>
<br/> &emsp;Model built has been deployed in <b>Heroku (PaaS) using Flask</b>
<br/> &emsp;It can be accessed via link: https://creditcard-purchase-prediction.herokuapp.com/
<br/> &emsp;For time being, Logistic Regression is used in api prediction
<br/> &emsp;Files reqd for deployment : 2 pickle files-scaler & model, app.py, index.html, procfile, requirements.txt
<br/> &emsp;Credits : Krish Naik - 
<br/> &emsp;Reference Links :
<br/> &emsp;&emsp;1) Deployment of ML models in Heroku using FLASK : 
<br/> &emsp;&emsp;https://www.youtube.com/watch?v=mrExsjcvF4o&t=880s
<br/> &emsp;&emsp;2) How To Debug Logs And Web Application In Heroku|Data Science :
<br/> &emsp;&emsp;https://www.youtube.com/watch?v=U350rWtxGwg&t=952s

