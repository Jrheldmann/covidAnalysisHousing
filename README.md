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

### Realization
After a lot of trial and error with basic neural networks and deep learning models, as well as revisiting logisitical regression, I still am not achieving good accuracy results. I attempted to reduce the basic neural network to just two features, cases and POPESTIMATE, and still had 0.0 accuracy. I think the machine is having difficultly predicting the cost of a house so it may be better to create a new column that determines if the price increases or decreases from the previous month. That way this can be a binary target, instead of a quantitative, which I think would be easier to predict based on the features. 

### Second Segment

Description of preliminary data preprocessing
- Using sample_data.csv, there are 26 columns. As a precautionary measure, all rows and columns that contain all null values will be removed. The data in this dataframe is from year 2017 to 2021. In order to not have Pre-Covid-19 data skew our results, all data prior to the year 2019 will be removed. We belive this will allow us to set a baseline of how housing costs have changed prior to the pandemic. 

Description of preliminary feature engineering and preliminary feature selection, including the decision-making process
- For the linear regression model, we will use Covid Cases as the feature, and House Cost as the target. In other models, we will removing other columns, such as county/state and per capita income, that we don't feel will be important features in predicting our target. Right now the target of House Cost is a quantitative variable, which may present a problem with neural networks. If the neural network produces results with low accuracy, we may have to create a a new column that represents whether there is a Cost Increase or Cost Decrease from the previous month. This column would be binary and might allow the neural network to have improved accuracy. 

![linear_regression](https://user-images.githubusercontent.com/109091887/209036936-a2f53f8c-03d2-4940-ba62-9372d25c919c.png)

Description of how data was split into training and testing sets
- 

Explanation of model choice, including limitations and benefits
