# Installations
Python 3.8.5

!pip install kaggle

!pip install pandasql

!pip install scipy

!pip install statsmodels

# Business Understanding
Airbnb can be quite a profitable venture for many hosts. Maximizing guest occupancy is a key priority for hosts to maximize revenue. The goal of this project is to examine features that impact Airbnb occupancy rates, specifically asking the followjng questions:

1) Do occupancy rates differ among markets?

2) Does price have an impact on occupancy rate? And if so what is the magnitude of this relationship

3) How do property features impact occupancy rate?

4) Do Airbnb hosts with higher ratings have higher occupancy rates?

# Data Understanding

The data is taken from webscraping a series of Airbnb reviews and can be found through the following Kaggle links.

Seattle: https://www.kaggle.com/airbnb/seattle/data

Boston: https://www.kaggle.com/airbnb/boston

# Prepare Data

In order to obtain the needed occupancy rate, the number of days where a property was occupied (or rather unavailable), were aggregated by each listing. Additionally, the total number of days a property was listed on the market was also aggregated by each listing. Through the following calculation, occupancy rate was calculated as such:

Occupancy Rate = Number of occupied days / Total number of days on the market

After obtaining the occupancy rate, a series of left joins (using SQL syntax within Python) created the master dataframe for analysis.

# Data Modeling

Analyzing the differences between markets (Seattle and Boston) was performed by grouping the mean occupancy rate by each market and examining the differences between the two.

Ordinary Least Squares (OLS) was conducted to estimate the relationship between price and occupancy rate.

Similar to the approach taken to examine the differences between markets, the mean occupancy rate was grouped by each room type and property type to examine the differences across each category. Additionally, occupancy rate was also grouped by both room type and property type for a deeper analysis.

Lastly, to examine the impact of ratings on occupancy rate buckets were established to examine the rates across each bucket. 

# Evaluation of Results

Airbnb occupancy rates were 12% higher in Boston compared to Seattle. Reasons for such a difference might be attributed to the geographic locations of each respective city, where Boston is located on the heavily populated Eastern Seaboard close to major markets like New York and Philadelphia, while Seattle is located in a much less densely populated region.

Through a series of OLS regressions there was no significant relationship between price and occupancy rate, as dominstated by a lack of statistical significance of the regression coefficient and an R-Squared value of 0.

When examining how room type impacted occupancy rates, Entire home/apartment scored the highest occupancy rate at 46.9%. Condominium properties (59.2%) exhibited the highest occupancy rates among property type features. When aggregating occupancy rate by both room type property features, the data displayed Condominiums that are either an entire home/apartment or a private room had the highest occupancy rates at 61.4% and 55.1% respectively.

Higher ratings did appear to have a relationship with higher occupancy rates. Among listings that had a minimum of 10 reviews, properties with perfect rating scores had the highest occupancy rate at 45%.

# File Description
Included in this repisitory is the "Udacity Airbnb Blog.ipynb" file which contains all the necessary code to run this analysis. A detailed summary of this analysis can be found through the following link: https://medium.com/@ceisen/analysis-of-factors-that-influence-airbnb-occupancy-rates-8e75a9c56b5b

# How to Interact with this project
The workbook included in this repository is designed to allow the user to replicate the results of this analysis. This includes conducting the necessary data processing, including the execution of various SQL queries, to transform the data for needed analysis. 

Additonally, all running this script will allow the user to replicate the statisitical methods utilized in this analysis with detailed tables of the findings. 

# Licensing, Authors, Acknowledgements
Credit must be given to Airbnb for the data. You can find the Licensing for the data and other descriptive information in the following Kaggle links below. Additional credit must go to Udacity for providing a high level template to construct this project while also providing the necessary teachings. 
