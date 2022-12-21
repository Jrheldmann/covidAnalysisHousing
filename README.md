![covid-housing](https://github.com/Jrheldmann/Starfall/blob/main/Square_role/readMeResources/covid-housing.png)
# Covid-19 Impact on Housing Prices in the US
## Group Members
 Members     | Role     |    Responsibilities  |
| ------------- | ------------- | -------- |
| Juhi          | Database  Lead       | Create databases |
| Will| Technology Lead         | 	Machine learning model|
| Tim |Dashboard Lead | Create a dashboard to present the data|
| Joe| Github Lead | Responsible for updating the repository and ReadMe|

### Communication Protocols

Communication happens primarily over slack group channel with emergency contact via direct texts between members.

## Overview 
<<<<<<< HEAD
In X role branch


## Questions that we hoped to answer and what we did answer

In X role branch

## Dashboard



## Data Base
=======
### Selected Topic

Team Starfall has chosen to develop a machine learning model to predict the change in housing prices in a given U.S. county based on the number of local COVID cases. Demographic data for each county will also be taken into consideration. In the U.S., there is a wide variety of socioeconomic statuses and pre-existing housing market conditions in a given county. Because buying or selling a home is such a major life event and financial strain, these demographic data must be included because we expect that the predictive power of any model will likely vary from county to county based on some of these factors.

### Selection Rationale

Our team initially sought to use COVID datasets to predict spikes in COVID cases in a given U.S. county based on trends in historic weekly COVID data from that county. This seemed like a good topic for its inherent current cultural relevance, as well as the volume of COVID case data publicly available from the Centers for Disease Control (CDC). As per recommendations from the instructor and teaching assistant regarding the scope of that investigation being too large and not having a clearly defined business-use case, we decided to pivot to a modified topic.

We were able to retain the county-based COVID case dataset, but shifted the target prediction to home sales. We felt this was a good compromise to retain our initial interest in a current and impactful topic. While it might seem counter-intuitive, adding the home sales data as a predictive target did actually narrow the scope of the machine learning model. Rather than trying to train a model to use one set of historic COVID data to predict that same type of data might change in the future, we can now use the historic COVID data and the temporally and geographically matched housing data to train a model to only predict the housing data's changes. This is much more likely to lead to a successful machine learning model, and also draws a much clearer picture of how that model can be used for a business use.

### Data sources

As previously stated, COVID case data by county was sourced from the CDC. Demographic data by county was sourced from the U.S. Census Bureau, Rural-Urban Continuum Codes were sourced from the U.S. Department of Agriculture, and home sales data by county was sourced from Zillow.

### Questions to be answered

We hope to determine whether a machine learning model can be a helpful tool in real estate transactions by answering a number of questions from the datasets. First, are the number of COVID cases in a geographic area impacting housing prices in those areas? Are prices rising where COVID cases are lower, and vice versa? Is the population density of a geographic area the driving force behind higher COVID case numbers, and therefore driving home prices down in those areas? Are home prices in rural, suburban, and urban areas being impacted the same way by COVID cases, or is the rate of home price change different based on these location classifications? And finally, are the findings of the previous questions the same across demographics, or are demographic differences between counties mitigating or amplifying the model's predictive power in some way?

## Presentation & Dashboard

Google Slideshow (rough cut, still very much in progress): https://docs.google.com/presentation/d/1kjO0vaHzWOCidoWfdnLT9qGtgoUTodmvxP2sFZ1uGJk/edit#slide=id.p

Tableau Public Workbook (also still very much in progress!): https://public.tableau.com/app/profile/tim5029/viz/Starfall_Dashboard/Story1?publish=yes

## Data Base

Data was cleaned (removing counties not in the US such as Washington DC or US territories, years not inbetween 2019 and 2021, and missing data).
### Data Sources

>>>>>>> cb4dcabe8c7fb3c64d8ad103c53281a8832fd46e
Dependent Variable- Zillow Housing data: https://www.zillow.com/research/data/

Rural vs Urban counties- Rural-Urban Continuum Codes:https://www.ers.usda.gov/data-products/rural-urban-continuum-codes.aspx

Income per capita- ACS: https://data.census.gov/table?q=B19301:+PER+CAPITA+INCOME+IN+THE+PAST+12+MONTHS+(IN+2021+INFLATION-ADJUSTED+DOLLARS)&g=0100000US,$0500000&tid=ACSDT1Y2021.B19301

Population/Age/Sex 2017-2019- CC-EST2020-AGESEX-ALL.csv:https://www2.census.gov/programs-surveys/popest/datasets/2010-2020/counties/asrh/ Race/Ethnicity 2017-2019-CC-EST2020-AL6LDATA.csv:https://www2.census.gov/programs-surveys/popest/datasets/2010-2020/counties/asrh/

Population/Age/Sex 2020-2021 cc-est2021-agesex-all.csv:https://www2.census.gov/programs-surveys/popest/datasets/2020-2021/counties/asrh/

Race/Ethnicity 2020-2021 cc-est2021-all.csv:https://www2.census.gov/programs-surveys/popest/datasets/2020-2021/counties/asrh/

COVID-19 data: https://data.cdc.gov/Public-Health-Surveillance/United-States-COVID-19-Community-Levels-by-County/3nnm-4jni (Split into years for CSV size)

FIPS: https://github.com/kjhealy/us-county/blob/master/data/census/fips-by-state.csv

<<<<<<< HEAD
Iteration 1:
Data was cleaned.

Income data was cleaned and concatenated into one database. We only kept year, county and income columns.

Race data was cleaned and concatenated in one database, and different races we kept were added together from male/female to total. 

Age/Sex was cleaned and concatenated in one database, age groups, age median, male/female ratio, counties and years will work.

Rural vs Urban counties was kept the same.


Needs: Find a way to transpose Zillow data into rows.

Iteration 2:
Originally we got data for the years 2017-2021 after the first round of ML we removed variables.

All databases were made sure to have either a FIPs, countyname,Statename, or countyname,StateAbrivation so that FIPS database can be used to join all databases. After this we have not yet removed the unneeded columns. 


ERD:

![ERD](https://user-images.githubusercontent.com/109693301/207495541-33df45d6-d182-4eb1-b512-86207fc6ce04.png)

All tables are connected by fips, fips by year, and fips by year and month. This ERD only contains columns we are going to keep.

For the housing cost Zillow data we used pd.stack() which allowed us to have all cost data to be in rows and indexed by their fips. This allows us to convert time series data into individual instances of data for each county. We went in and manually changed the names of rows because the issue with stack was that we were not able to manipulate the data after. Finally, we broke the dates into months and years to make the fips by year and fips by year and month above. This table is currently under Zillow_int2.csv

All examples of these iterations are currently in the Circle branch.

Needs: Merge data using SQL, and finish cleaning data.

Iteration 3:
We have cleaned all of the data individually removing all Nan when merging. We have merged the data into 2 dataframes, housing/covid data and demographic (population, race/eth, income, and Rural/urban areas).
We uploaded these 2 dataframes to Mongo. 

Needs: Merge these two frames in Mongo.

Iteration 4:
Pivot I merged the data in SQL not mongo as it was not working. The query is schema.sql. The data was then downloaded and uploaded into Mongodb (currently in the github as mergedata.csv in clean data).
Mongodb has been found to be shared over the cloud via Atlas. This is currently being tested. 

Needs: Mongodb needs to be shared with others.
=======
Iterations in detail: (Insert link currently in Circle folder)

## 
>>>>>>> cb4dcabe8c7fb3c64d8ad103c53281a8832fd46e

## Machine Learning

### Linear Regression
Using the sample_data.csv I focused on the "cases" and "Cost" columns. I used the cases as the feature (independent variable) and the Cost as the target (dependent variable). 

<<<<<<< HEAD
![linear_regression](https://user-images.githubusercontent.com/109091887/207204406-b32c8ebe-f1c7-4648-8ab8-610fdaecfeb9.png)
(my images are not working correctly and I'm still figuring out why)

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are. 


### Neural Network
Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 

=======
![scaled_linear_regression](https://user-images.githubusercontent.com/109091887/208565119-1a69f486-5057-426f-bc0a-daebbb983e16.png)
{realized i need to label the axises to make the graph easier to read.}

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are. 

### Logistical Regression
Next I decided to use logistical regression to attempt to predict Cost based on all the other 24 features in the dataset. I didn't scale the data when setting up the model this time but I think I will after this. After training the data and comparing the predictions to the actual Cost, the accuracy score was 0.0. Obviously these results are less than I had hoped so for my second iteration I'm going to scale the data and potentially remove several features.

### Machine Learning
Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 

After completing the basic neural network, using all 24 features, and 100 epochs, the accuracy is 0.0. Not the results I was looking for but I think I can improve the accuracy by removing some features. Since the basic neural network wasn't very successful, my next model will be a deep learning model since deep learning models are better at making predictions with many features. At this point, I'm hoping for the deep learning model will result in an accuracy higher than 0.0.

>>>>>>> cb4dcabe8c7fb3c64d8ad103c53281a8832fd46e
## Conclusion

## Technology Used

Pandas

Jupyter notebook

MongoDB

<<<<<<< HEAD
Intended use- Tableau
=======
Intended use- Tablau
>>>>>>> cb4dcabe8c7fb3c64d8ad103c53281a8832fd46e
