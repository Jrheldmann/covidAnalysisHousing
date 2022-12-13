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

## Questions that we hoped to answer and what we did answer

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

Income data was cleaned and concatanated into one database. We only kept year, county and income columns.

Race data was cleaned and concatanated in one database, different races we kept were added together from male/female to total. 

Age/Sex was cleaned and concatanated in one database, age groups, age median, male/female ratio, counties and years will work.

Rural vs Urban counties was kept the same.


Needs: Find a way to transpose Zillow data into rows.

Iteration 2:
Originally we got data for years 2017-2021 after first round of ML we removed variables.

All databases were made sure to have either a FIPs, countyname,Statename, or countyname,StateAbrivation so that FIPS database can be used to join all databases. 

Needs: Merge data using SQL.

## Machine Learning

## Conclusion

## Technology Used
