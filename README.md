![covid-housing](https://github.com/Jrheldmann/Starfall/blob/main/Square_role/readMeResources/covid-housing.png)
# Covid-19 Impact on Housing Prices in the US
## Group Members
 Members     | Role     |    Responsibilities  |
| ------------- | ------------- | -------- |
| Juhi          | Database  Lead       | Create databases |
| Will| Technology Lead         | 	Machine learning model|
| Tim |Dashboard Lead | Create a dashboard to present the data|
| Joe| Github Lead | Responsible for updating the repository and ReadMe|

## Overview 

### Selected Topic

Team Starfall has chosen to develop a machine learning model to predict the change in housing prices in a given U.S. county based on the number of local COVID cases. Demographic data for each county will also be taken into consideration. In the U.S., there is a wide variety of socioeconomic statuses and pre-existing housing market conditions in a given county. Because buying or selling a home is such a major life event and financial strain, these demographic data must be included because we expect that the predictive power of any model will likely vary from county to county based on some of these factors.

### Selection Rationale

Our team initially sought to use COVID datasets to predict spikes in COVID cases in a given U.S. county based on trends in historic weekly COVID data from that county. This seemed like a good topic for its inherent current cultural relevance, as well as the volume of COVID case data publicly available from the Centers for Disease Control (CDC). As per recommendations from the instructor and teaching assistant regarding the scope of that investigation being too large and not having a clearly defined business-use case, we decided to pivot to a modified topic.

We were able to retain the county-based COVID case dataset, but shifted the target prediction to home sales. We felt this was a good compromise to retain our initial interest in a current and impactful topic. While it might seem counter-intuitive, adding the home sales data as a predictive target did actually narrow the scope of the machine learning model. Rather than trying to train a model to use one set of historic COVID data to predict that same type of data might change in the future, we can now use the historic COVID data and the temporally and geographically matched housing data to train a model to only predict the housing data's changes. This is much more likely to lead to a successful machine learning model, and also draws a much clearer picture of how that model can be used for a business use.

### Data sources

As previously stated, COVID case data by county was sourced from the CDC. Demographic data by county was sourced from the U.S. Census Bureau, Rural-Urban Continuum Codes were sourced from the U.S. Department of Agriculture, and home sales data by county was sourced from Zillow.
Dependent Variable- Zillow Housing data: https://www.zillow.com/research/data/

Rural vs Urban counties- Rural-Urban Continuum Codes:https://www.ers.usda.gov/data-products/rural-urban-continuum-codes.aspx

Income per capita- ACS: https://data.census.gov/table?q=B19301:+PER+CAPITA+INCOME+IN+THE+PAST+12+MONTHS+(IN+2021+INFLATION-ADJUSTED+DOLLARS)&g=0100000US,$0500000&tid=ACSDT1Y2021.B19301

Population/Age/Sex 2017-2019- CC-EST2020-AGESEX-ALL.csv:https://www2.census.gov/programs-surveys/popest/datasets/2010-2020/counties/asrh/ Race/Ethnicity 2017-2019-CC-EST2020-AL6LDATA.csv:https://www2.census.gov/programs-surveys/popest/datasets/2010-2020/counties/asrh/

Population/Age/Sex 2020-2021 cc-est2021-agesex-all.csv:https://www2.census.gov/programs-surveys/popest/datasets/2020-2021/counties/asrh/

Race/Ethnicity 2020-2021 cc-est2021-all.csv:https://www2.census.gov/programs-surveys/popest/datasets/2020-2021/counties/asrh/

COVID-19 data: https://data.cdc.gov/Public-Health-Surveillance/United-States-COVID-19-Community-Levels-by-County/3nnm-4jni (Split into years for CSV size)

FIPS: https://github.com/kjhealy/us-county/blob/master/data/census/fips-by-state.csv

### Questions to be answered

We hope to determine whether a machine learning model can be a helpful tool in real estate transactions by answering a number of questions from the datasets. First, are the number of COVID cases in a geographic area impacting housing prices in those areas? Are prices rising where COVID cases are lower, and vice versa? Is the population density of a geographic area the driving force behind higher COVID case numbers, and therefore driving home prices down in those areas? Are home prices in rural, suburban, and urban areas being impacted the same way by COVID cases, or is the rate of home price change different based on these location classifications? And finally, are the findings of the previous questions the same across demographics, or are demographic differences between counties mitigating or amplifying the model's predictive power in some way?

## Presentation & Dashboard

Google Slideshow (rough cut, still very much in progress): https://docs.google.com/presentation/d/1kjO0vaHzWOCidoWfdnLT9qGtgoUTodmvxP2sFZ1uGJk/edit#slide=id.p

Tableau Public Workbook (also still very much in progress!): https://public.tableau.com/app/profile/tim5029/viz/Starfall_Dashboard/StarfallTemporaryDashboardIn-Progress?publish=yes

## Data Base

Data was cleaned (removing counties not in the US such as Washington DC or US territories, years not inbetween 2019 and 2021, and missing data).

Data that had multiple csv's were contacantated into one database, at this point we had 6 databases: income, race/ethnicity, population, Rural/urban, Zillow housing, COVID cases, and Fips. 
A challange at this point was making the time series Zillow file into multiple rows. This was done using the pd.stack() method. 

All databases were made sure to have either a FIPs, countyname,Statename, or countyname,StateAbrivation so that FIPS database can be used to join all databases. After this we have not yet removed the unneeded columns. 

ERD:

![ERD](https://user-images.githubusercontent.com/109693301/207495541-33df45d6-d182-4eb1-b512-86207fc6ce04.png)



All tables are connected by fips, fips by year, and fips by year and month. This ERD only contains columns we are going to keep.

Data was merged into two dataframes in pandas housing/covid data and demographic (population, race/eth, income, and Rural/urban areas). and was uploaded to MongoAtlas. Within SQL we were able to merge this data into merged_data and uploaded into MongoAtlas. All uploads used PyMongo.

Iterations in detail: (Insert link currently in Circle folder, Circle_roleReadMe.txt)

## Machine Learning

### Linear Regression
Using the sample_data.csv I focused on the "cases" and "Cost" columns. I used the cases as the feature (independent variable) and the Cost as the target (dependent variable). 

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are. 

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are.

### Logistical Regression
Next I decided to use logistical regression to attempt to predict Cost based on all the other 24 features in the dataset. I didn't scale the data when setting up the model this time but I think I will after this. After training the data and comparing the predictions to the actual Cost, the accuracy score was 0.0. Obviously these results are less than I had hoped so for my second iteration I'm going to scale the data and potentially remove several features.

### Neural Network
Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 

After completing the basic neural network, using all 24 features, and 100 epochs, the accuracy is 0.0. Not the results I was looking for but I think I can improve the accuracy by removing some features. Since the basic neural network wasn't very successful, my next model will be a deep learning model since deep learning models are better at making predictions with many features. At this point, I'm hoping for the deep learning model will result in an accuracy higher than 0.0.

### Second Segment

Description of preliminary data preprocessing
- Using sample_data.csv, there are 26 columns. As a precautionary measure, all rows and columns that contain all null values will be removed. The data in this dataframe is from year 2017 to 2021. In order to not have Pre-Covid-19 data skew our results, all data prior to the year 2019 will be removed. We belive this will allow us to set a baseline of how housing costs have changed prior to the pandemic. 

Description of preliminary feature engineering and preliminary feature selection, including the decision-making process
- For the linear regression model, we will use Covid Cases as the feature, and House Cost as the target. In other models, we will removing other columns, such as county/state and per capita income, that we don't feel will be important features in predicting our target. Right now the target of House Cost is a quantitative variable, which may present a problem with neural networks. If the neural network produces results with low accuracy, we may have to create a a new column that represents whether there is a Cost Increase or Cost Decrease from the previous month. This column would be binary and might allow the neural network to have improved accuracy. 

![linear_regression](https://user-images.githubusercontent.com/109091887/209036936-a2f53f8c-03d2-4940-ba62-9372d25c919c.png)

Description of how data was split into training and testing sets
- When using the basic neural network, the train_test_split method from the sklearn library will be used. By default, the train size will be we to 0.25. 

Explanation of model choice, including limitations and benefits
- Using a linear regression model be will beneficial to use if the data continues to stay linear. This will be determined when the entire dataset is imported into the model. If the Covid Cases and House Cost do not have a linear relationship then another model will be considered. Another limitation of this model if the removal of many possible features. These other potential feature may play a big role in making predictions of the target. Other models that are being considered are logisitical regression, PCA, neural networks, and deep learning models. 

## Conclusion

## Technology Used

Pandas

Jupyter notebook

SQL

MongoDB/MongoAtlas

Intended use- Tableau

