# Group4_Cardiovascular_Disease

## Files and Folders
* Data Folder
  * cardio_data_processed.csv is to be used with Cardiovascular_model.ipynb and Cardiovascular_model_auto_optimization.ipynb
  * clean_cardio_data.csv is to be used with random_forest.ipynb and XGBoost.ipynb
* Image
  * all 3 images are used in this report.
 
## Overview of the Analysis 
*  **Purpose:** <br/>
&emsp;The purpose of our model is to be able to predict if an individual is at risk of cardiovascular disease
*  **Data Processing:** <br/>
&emsp;Our target variable is cardio
*  **Feature variables**:<br/>
&emsp;Columns that we kepts were gender, cholestrol, glu, smoke, alc, active, cardio, age_years, bmi, elevated, hypertension Stage 1, Hypertension Sate 2, Normal
*  **Removed Columns:**<br/>
&emsp; We removed age, api_hi, api_lo, id, cardio, bp_category, height, and weight
*  **Cleaning up the data:** <br/>
After remvoing redundancies and irrelavent data, we first used a box plot whisker to find all the outliers and remove them from our data set. The raw data start at 68205 rows down to 62505 rows  

## Results 
*  **Model: Random Forests** <br\>
  To run the model, we ended up using the clean_cardio_data.csv. This csv file was created when we were using keras optimization tool. After splitting the data set into train and test sets, we scaled it and trained it. After making our prediction, the results gave us an accuracy of 68.70%. We can see that the test data was split quit evenly between cardio and non-cardiovascular disease. Recall for predicting cardiovascular disease is 63%, we would prefer a higher percentage. In terms of feature importance, Hypertension Stage 2 and age are the key drivers when it comes to making decisions.  
![image](https://github.com/Dav5T/Group4_Cardiovascular_Disease/assets/130593953/49b11f38-3031-4045-b716-6ca1842e2dbd)

  



