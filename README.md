# Starfall

## Linear Regression
Using the sample_data.csv I focused on the "cases" and "Cost" columns. I used the cases as the feature (independent variable) and the Cost as the target (dependent variable). 

![linear_regression](https://user-images.githubusercontent.com/109091887/207204406-b32c8ebe-f1c7-4648-8ab8-610fdaecfeb9.png)
(my images are not working correctly and I'm still figuring out why)

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are. 


## Machine Learning
Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 


