# Starfall
Triangle_branch

# First Segment

- Takes in data from the provisional database

**Linear Regression**

Using the sample_data.csv I focused on the "cases" and "Cost" columns. I used the cases as the feature (independent variable) and the Cost as the target (dependent variable). 

![scaled_linear_regression](https://user-images.githubusercontent.com/109091887/208565119-1a69f486-5057-426f-bc0a-daebbb983e16.png)

- Outputs label for input data
There is a positive association between cases and Cost. The correlation coefficient between cases and Cost is 0.53

**Logistical Regression**

Next I decided to use logistical regression to attempt to predict Cost based on all the other 24 features in the dataset. I didn't scale the data when setting up the model this time but I think I will after this. After training the data and comparing the predictions to the actual Cost, the accuracy score was 0.0. Obviously these results are less than I had hoped so for my second iteration I'm going to scale the data and potentially remove several features.

**Machine Learning**

Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 

After completing the basic neural network, using all 24 features, and 100 epochs, the accuracy is 0.0. Not the results I was looking for but I think I can improve the accuracy by removing some features. Since the basic neural network wasn't very successful, my next model will be a deep learning model since deep learning models are better at making predictions with many features. At this point, I'm hoping for the deep learning model will result in an accuracy higher than 0.0.

## Realizations

After a lot of trial and error with basic neural networks and deep learning models, as well as revisiting logisitical regression, I still am not achieving good accuracy results. I attempted to reduce the basic neural network to just two features, cases and POPESTIMATE, and still had 0.0 accuracy. I think the machine is having difficultly predicting the cost of a house so it may be better to create a new column that determines if the price increases or decreases from the previous month. That way this can be a binary target, instead of a quantitative, which I think would be easier to predict based on the features. 

# Second Segment

- Description of preliminary data preprocessing
Using sample_data.csv, there are 26 columns. As a precautionary measure, all rows and columns that contain all null values will be removed. The data in this dataframe is from year 2017 to 2021. In order to not have Pre-Covid-19 data skew our results, all data prior to the year 2019 will be removed. We belive this will allow us to set a baseline of how housing costs have changed prior to the pandemic. 

- Description of preliminary feature engineering and preliminary feature selection, including the decision-making process
For the linear regression model, we will use Covid Cases as the feature, and House Cost as the target. In other models, we will removing other columns, such as county/state and per capita income, that we don't feel will be important features in predicting our target. Right now the target of House Cost is a quantitative variable, which may present a problem with neural networks. If the neural network produces results with low accuracy, we may have to create a a new column that represents whether there is a Cost Increase or Cost Decrease from the previous month. This column would be binary and might allow the neural network to have improved accuracy. 

![linear_regression](https://user-images.githubusercontent.com/109091887/209036936-a2f53f8c-03d2-4940-ba62-9372d25c919c.png)

- Description of how data was split into training and testing sets

When using the basic neural network, the train_test_split method from the sklearn library will be used. By default, the train size will be we to 0.25. 

- Explanation of model choice, including limitations and benefits

Using a linear regression model be will beneficial to use if the data continues to stay linear. This will be determined when the entire dataset is imported into the model. If the Covid Cases and House Cost do not have a linear relationship then another model will be considered. Another limitation of this model if the removal of many possible features. These other potential feature may play a big role in making predictions of the target. Other models that are being considered are logisitical regression, PCA, neural networks, and deep learning models. 

# Third Segment
- Description of data preprocessing

Now using the final data set, preprocessing began with removing any rows or columns that contained null values. Using years 2019, 2020, and 2021 will allow the machine learning models to make conclusions from data pre-covid, covid's peak, and the covid's tail.

- Description of feature engineering and the feature selection, including the decision-making process

Not going to use all features. use linear regression to compare each feature with the targets and check correlation. remove features with correlation close to 0. highlight features with strong correlation. 

- Description of how data was split into training and testing sets

When using the basic neural network, the train_test_split method from the sklearn library will be used. By default, the train size will be we to 0.25. 

Using the MinMaxScaler instead of StandardScaler so that values are scaled from 0 to 1, instead of -1 to 1.

Random Forest comparing predictions against y-test. Test correlation and MSE between these two.

PCA is a statistical technique to speed up machine learning algorithms when the number of input features (or dimensions) is too high. PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set.

- Explanation of model choice, including limitations and benefits


New Notes: first choice was linear, data doesn't appear to be linear. also compared linear relationship between each feature and target. moved onto basic neural netowrk and deep learning models. also testing random forests. 

Using a linear regression model be will beneficial to use if the data continues to stay linear. This will be determined when the entire dataset is imported into the model. If the Covid Cases and House Cost do not have a linear relationship then another model will be considered. Another limitation of this model if the removal of many possible features. These other potential feature may play a big role in making predictions of the target. Other models that are being considered are logisitical regression, PCA, neural networks, and deep learning models. 

- Explanation of changes in model choice (if changes occurred between the Segment 2 and Segment 3 deliverables)

discovering the data is not full linear so we moved away from that. originally testing basic neural networks and deep learning models and achieved 0 accuracy. updated scaler and changed first layer from sigmoid to relu. kept output layer as sigmoid. also testing random forests but uncertain of accuracy yet.

- Description of how they have trained the model thus far, and any additional training that will take place

originally the basic neural network was not training the model well. attempts were made to change the number or layers and neurons in each layer. features were removed. after the changing of the scaler and first layer function to relu, additional training will take place using all features. more training will be completed when the correlation is calculated between each feature and target and we are able to narrow features. hopefully this will help the model train the data better. 

- Description of current accuracy score

1.826 e-5
