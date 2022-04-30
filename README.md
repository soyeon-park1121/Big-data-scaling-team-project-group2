# Selling Price of Used Cars

This repository is composed of 5 different notebook like this:
10-data-processing
20-eda
21-eda-sale_price_gap
30-modeling-predict_selling_price
31-modeling-predict_sale_price_gap

10 notebook shows data processing. 20 and 21 show EDA part, and 30 and 31 consists of modeling. One is for predicting selling price and the other is for predicting sale price gap (selling price - MMR)

## 10-data-processing
In this notebook, we cleaned raw data. By using PySpark, we calculated the percentage of missing data for each column. For the categorical data, we used mode to impute data, while we chose mean values for numerical data when we imputed the rest of the columns. The column ‘body’ has 88 different categorical values. As this decreased the accuracy of model, we simplified the column by combining similar concepts. For example, there were ‘crew cab’, ‘quad cab’, and ‘cab’. Since they refer to the same ‘cab’, we combined them as ‘cab’. We applied this method to other types of car as well. Lastly, we removed the outlier in the column 'selling price'. We excluded 10% of upper and bottom bound to remove outliers which would drop the accuracy of model. For feature engineering, I created a new varialbe called 'madeRegion' using 'Vin'. The first 2 letters of Vin means country or region codes. Also, we extracted 'saleyear' from sale date, since people consider only year when they consider used cars.

## 20-eda
This is notebook is for exploratory data analysis. This notebook answers 2 questions in the final report: Question 1 (What is the relationship between odometer and selling price?) and Question 2 (What brand is good to have considering selling later?). Using matplotlib package, I created a scatter plot showing the relationship between odoemter and selling price to answer the Question 1. Also, I generated a line plot of which the x-axis is the year used, and the y-axis is selling price. This data visualization answers the Question 2. Besides that, this notebook also contains other visualization such as a pie chart showing the proportion of values, a bar chart showing the popularity of colors in used car market, and a scatter plot showing the relation between MMR and selling price.

## 21-eda-sale_price_gap
In this notebook, we want to find the relation between MMR and the actual sale price. We define Sale Price Gap = Final Sale Price – MMR. We did some EDA and plot the distribution of the sale price gap.

## 30-modeling-predict_selling_price
In this notebook, we built a pipeline to change all the category variables and assemble all the features in one column. Then we used the MLlib to build 3 kinds of model, which are linear regression, decision tree, and random forest. Then we calculated the correlation between the features and selling price. Finally, we used the for-loop to find out the depth for the best decision tree model.

## 31-modeling
In this notebook, we use Google Cloud to build models to predict the sale price gap, which is in the examination part of the report. We choose linear regression and decision tree to complete it.
