# Starfall
Triangle_branch

## Linear Regression
Using the sample_data.csv I focused on the "cases" and "Cost" columns. I used the cases as the feature (independent variable) and the Cost as the target (dependent variable). 

![scaled_linear_regression](https://user-images.githubusercontent.com/109091887/208565119-1a69f486-5057-426f-bc0a-daebbb983e16.png)
{realized i need to label the axises to make the graph easier to read.}

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are. 

## Logistical Regression
Next I decided to use logistical regression to attempt to predict Cost based on all the other 24 features in the dataset. I didn't scale the data when setting up the model this time but I think I will after this. After training the data and comparing the predictions to the actual Cost, the accuracy score was 0.0. Obviously these results are less than I had hoped so for my second iteration I'm going to scale the data and potentially remove several features.

## Machine Learning
Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 

After completing the basic neural network, using all 24 features, and 100 epochs, the accuracy is 0.0. Not the results I was looking for but I think I can improve the accuracy by removing some features. Since the basic neural network wasn't very successful, my next model will be a deep learning model since deep learning models are better at making predictions with many features. At this point, I'm hoping for the deep learning model will result in an accuracy higher than 0.0.
