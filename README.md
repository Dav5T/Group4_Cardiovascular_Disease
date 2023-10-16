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
*  **Model: Random Forest** <br/>
  To run the model, we ended up using the clean_cardio_data.csv. This csv file was created when we were using keras optimization tool. After splitting the data set into train and test sets, we scaled it and trained it. After making our prediction, the results gave us an accuracy of 68.70%. We can see that the test data was split quit evenly between cardio and non-cardiovascular disease. Recall for predicting cardiovascular disease is 63%, we would prefer a higher percentage. In terms of feature importance, Hypertension Stage 2 and age are the key drivers when it comes to making decisions.  
![image](https://github.com/Dav5T/Group4_Cardiovascular_Disease/assets/130593953/49b11f38-3031-4045-b716-6ca1842e2dbd)
*  **Model: XGBoost** <br/>
 To run the model, we ended up using the clean_cardio_data.csv. Just like our Random Forst model it gve the same accuracy of 68.59%. The Confusion Matrix and Classification report spitted out very similar results. It isn't too suprisingly considering that they are quite similar in how it makes decisions. We did compare the training accuracy with the validation accuracy to see if there is possible change of overfitting, but as it turns out the model is predicting as it should 
![image](https://github.com/Dav5T/Group4_Cardiovascular_Disease/assets/130593953/e99f4b8b-205e-4196-9f37-a9a89f24a09c)
*  **Model: Keras Hypertuner and Deep Learning** <br/>
We first used the raw csv file (cardio_data_processed.csv) to clean up the data before running both. We ran the optimizer and the actual Neural Network on 2 different notebooks because the model would create extra layers from the optimizer when I wanted to test out the Deep Learning model. We ran optimizer a couple of times, and it would always output a different result. Once we saw that the best model was over 70% accuracy, we would stop the search and get a summary of the best model. Then we would use the combination to run the actual model. The model we chose was as follow:<br/><br/>
Model: "sequential"<br/>
=================================================================<br/>
 Layer (type)&emsp;              Output Shape&emsp;      Param #   <br/>
 =================================================================<br/>
 dense (Dense)&emsp;&emsp;         (None, 3)&emsp;                 39<br/>                                                                        
 dense_1 (Dense)&emsp;             (None, 5)&emsp;                 20<br/>                                                                    
 dense_2 (Dense)&emsp;             (None, 9)&emsp;                 54 <br/>                                                                   
 dense_3 (Dense)&emsp;             (None, 1)&emsp;                 10 <br/>                                                                    
=================================================================<br/>
Total params: 123 (492.00 Byte)<br/>
Trainable params: 123 (492.00 Byte)<br/>
Non-trainable params: 0 (0.00 Byte)<br/>
Activation function: tanh<br/>
Epoch: 7<br/>
=================================================================<br/>
The model was able to give us an accuracy of 70.08%. We also did a comparison of the training and validation accuracy to see if there was overfitting and as it turns out there wasn't any.
The confusion matrix had zeros for false negative and true negative. When it came to predicting at risk for cardiovascular disease we also got zeros based on the classification report. We decided to look at the ROC curve and calculate AUC to see if the model is accuracy is actually 70%. It turns out that AUC is 0.729 which is higher than the training accuracy. In addition, we inputted new information of a patient to see if the model can predict if someone is at risk of cardiovascular disease and it turned out that it was able to predict that the patient is at risk.
![image](https://github.com/Dav5T/Group4_Cardiovascular_Disease/assets/130593953/e0bfd29c-489a-4e6e-a1d5-4af232548682)


