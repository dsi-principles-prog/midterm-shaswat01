## Breast Cancer data:

<p> The dataset that I have choosen is the Breast Cancer Dataset. In this datsaet we have different attributes given which are related with the cancer type. We have been given the type of cancer i.e. Benign or Malignant according to the related rows.
The idea is to perform an exploratory analysis of the information contained in the dataset, figuring out ways of making the dataset tidier. The ultimate objective is to, in the end, build and compare models to predict if a given tumor is benign or malignant (breast cancer) using the information available on this dataset. <br>
Source: https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(original)
</p>
<p>
The Probelm with the dataset is that there are very less values after 2 in the mitoses column. (Mitoses column has values 1-10). It's better to have more values to traina model, so I did discreetization on that column, meaning that values 2 and after 2, I added them so that column has only 2 values, ie 1 and 2.<br>
Other problem with this dataset is that there are NA values. Now either we can remove these NA values or we can impute them. Imputing means filling NA or missing values with mean, median or random values. I choose to impute those with random values as it gave me higher accuracy on modelling. I choose to impute values because there are already less rows and i don't want to train model on even more less rows. More that data, better the fitting of model will be. <br>
Another problem is that for ML model it's better to have the predicted column to be a integer than string. In this dataset we are predicting whether the type of cancer is Benign or Malignant. So the user have make change in this column to make a new column so that it shows 1 for benign and 2 for malignant.<br>
Last thing to do in this dataset is to normalise it so that machine learning model will be able to predict Diagnosis with more accuracy. Normalise change the values of numeric columns in the dataset to a common scale, without distorting differences in the ranges of values.<br>
</p>

The following are orders in which the files should be run --- <br>

<b>1. 10_import :</b> This file include the importing of the dataset along with the important libraries required for this project. After importing i did some assert checking in the dataset.<br>

<b>2. 20_explore :</b> This file includes the EDA of the data. I did barplot and boxplot to get some insights in that data, to check the outliers.<br>

<b>3. 30_feature_engineering:</b> This file includes the functions that I used to do the feature engineering on the dataset. At the end I saved the new dataset (Clean_norm_BreastCancer.csv) which includes all the cleaned columns that are of our interest for modelling. (First column is the one that is to be predicted)<br>

<b>4. 21_explore :</b> This files includes the EDA I did on the new cleaned dataset. I checked the the correlation of all the columns and found that mitoses column is the one which is very less correlated with other columns.<br>

<b>5. 40_model :</b> This file include the kmeans and random forest model. I have checked whether including the mitoses column (which was less correlated with other features) will increase or decrease accuracy. In kmeans I clustered the data according to type of cancer,Benign or Malignant (1 for Benign and 2 for Malignant). I got accuracy of 93.13% with kmeans and 96.65% with Random Forest without including the mitoses column which is the highest. <br>
