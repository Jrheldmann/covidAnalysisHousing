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
In X role branch


## Questions that we hoped to answer and what we did answer

In X role branch

## Dashboard



## Data Base
Dependent Variable- Zillow Housing data: https://www.zillow.com/research/data/

Rural vs Urban counties- Rural-Urban Continuum Codes:https://www.ers.usda.gov/data-products/rural-urban-continuum-codes.aspx

Income per capita- ACS: https://data.census.gov/table?q=B19301:+PER+CAPITA+INCOME+IN+THE+PAST+12+MONTHS+(IN+2021+INFLATION-ADJUSTED+DOLLARS)&g=0100000US,$0500000&tid=ACSDT1Y2021.B19301

Population/Age/Sex 2017-2019- CC-EST2020-AGESEX-ALL.csv:https://www2.census.gov/programs-surveys/popest/datasets/2010-2020/counties/asrh/ Race/Ethnicity 2017-2019-CC-EST2020-AL6LDATA.csv:https://www2.census.gov/programs-surveys/popest/datasets/2010-2020/counties/asrh/

Population/Age/Sex 2020-2021 cc-est2021-agesex-all.csv:https://www2.census.gov/programs-surveys/popest/datasets/2020-2021/counties/asrh/

Race/Ethnicity 2020-2021 cc-est2021-all.csv:https://www2.census.gov/programs-surveys/popest/datasets/2020-2021/counties/asrh/

COVID-19 data: https://data.cdc.gov/Public-Health-Surveillance/United-States-COVID-19-Community-Levels-by-County/3nnm-4jni (Split into years for CSV size)

FIPS: https://github.com/kjhealy/us-county/blob/master/data/census/fips-by-state.csv

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

## Machine Learning

### Linear Regression
Using the sample_data.csv I focused on the "cases" and "Cost" columns. I used the cases as the feature (independent variable) and the Cost as the target (dependent variable). 

![linear_regression](https://user-images.githubusercontent.com/109091887/207204406-b32c8ebe-f1c7-4648-8ab8-610fdaecfeb9.png)
(my images are not working correctly and I'm still figuring out why)

On Dave's suggestion, I scaled the data for cases and Cost and created a new linear regression model. The y-intercept changed due to the scaling and the slope changed from 0.06 to 0.08. There is a positive association between cases and Cost. It would be worth looking into the correlation coefficient also to see how strongly correlated the two variables are. 


### Neural Network
Next I decided to include all of the columns besides the C_S column, which represented the county and state. A different column labeled "FIPS" is the US postal code for each row so that represents the location of the successfully with a numerical value. Since all other columns were numerical with a wide range of numbers, I decided to scale each column. Then I began creating a basic neural network. As a preliminary value, I would hope that the basic neural network yields an accuracy score of 50% or above. Based on how successful the model it, I will consider using a deep learning model by creating additional layers and neurons. 

## Conclusion

## Technology Used

Pandas

Jupyter notebook

MongoDB

Intended use- Tablau
