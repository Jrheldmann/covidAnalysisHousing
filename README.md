# Starfall
00-team-01 Group Project Final

## Selected Topic

Team Starfall has chosed to develop a machine learning model to predict the change in housing prices in a given U.S. county based on the number of local COVID cases. Demographic data for each county will also be taken into consideration. In the U.S., there is a wide variety of socioeconomic statuses and pre-existing housing market conditions in a given county. Because buying or selling a home is such a major life event and financial strain, these demographic data must be included because we expect that the predictive power of any model will likely vary from county to county based on some of these factors.

## Selection Rationale

Our team initially sought to use COVID datasets to predict spikes in COVID cases in a given U.S. county based on trends in historic weekly COVID data from that county. This seemed like a good topic for its inherent current cultural relevance, as well as the volume of COVID case data publicly available from the Centers for Disease Control (CDC). As per reommendations from the instructor and teaching assistant regarding the scope of that investigation being too large and not having a clearly defined business-use case, we decided to pivot to a modified topic.

We were able to retain the county-based COVID case dataset, but shifted the target prediction to home sales. We felt this was a good compromise to retain our initial interest in a current and impactful topic. While it might seem counter-intuitive, adding the home sales data as a predictive target did actually narrow the scope of the machine learning model. Rather than trying to train a model to use one set of historic COVID data to predict that same type of data might change in the future, we can now use the historic COVID data and the temporaliy and geographically matched housing data to train a model to only predict the housing data's changes. This is much more likely to lead to a successful machine learning model, and also draws a much clearer picture of how that model can be used for a business use.

## Data sources

As previously stated, COVID case data by county was sourced from the CDC. Demographic data by county was sourced from the U.S. Census Bureau, and home sales data by country was sourced from Zillow.

## Questions to be answered

We hope to determine whether a machine learning model can be a helpful tool in real estate transactions by answering a number of questions from the datasets. First, are the number of COVID cases in a geographic area impacting housing prices in those areas? Are prices rising where COVID cases are lower, and vice versa? Is the population density of a geographic area the driving force behind higher COVID case numbers, and therefore driving home prices down in those areas? Are home prices in rural, suburban, and urban areas being impacted the same way by COVID cases, or is the rate of home price change different based on these location classifications? And finally, are the findings of the previous questions the same across demographics, or are demogrphic differences between counties mitigating or amplifying the model's predictive power in some way?