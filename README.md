# Commodity Prices

This is a website to showcase our final project for FIN 377 - Data Science for Finance course at Lehigh University.

To see the complete analysis file(s) click [here](https://github.com/julioveracruz/testwebsite/blob/main/notebooks/example.ipynb).

Maybe you want a different website them for the project? Consider `minimal-mistakes`:
1. [Go here](https://github.com/mmistakes/mm-github-pages-starter/generate).
2. In the resulting repo, click Settings, then Pages, then make sure the source is the main branch.
3. [The doc site is here](https://mmistakes.github.io/minimal-mistakes/docs/structure/) and will help you customize layouts and figure out how to use it.

## Table of contents
1. [Introduction](#introduction)
2. [Research Question](#meth)
3. [Data](#section2)
4. [Project Considerations](#other)
5. [Data Cleaning](#cleaning)
6. [Predictive Modeling](#modeling)

## Introduction  <a name="introduction"></a>

The main goal of this project is to explore whether it is possible to predict the price of various agricultural commodities (corn, wheat, and soybeans) by using machine learning techniques on macroeconomic, weather, and financial datasets.  

## Research Question <a name="meth"></a>

#### Can climate and macroeconomic indicators be used to predict the future domestic returns of Corn, Wheat, and Soybeans? Can we use historical data to create a model that "beats the market" by finding arbitrage opportunity, or does the Efficient Market Hypothesis hold?

## Data <a name="section2"></a>
### Commodities
- [Corn](https://www.investing.com/commodities/us-corn-historical-data)
- [Wheat](https://www.investing.com/commodities/us-wheat-historical-data)
- [Soybeans](https://www.investing.com/commodities/us-soybeans-historical-data)


### Climate Data
- Domestic data only
- Precipitation
- Snowfall
- Maximum Temperature
- Minimum Temperature
- Collected in McLean, IL; Whitman, WA; and Cass, ND
- Data collected from https://www.ncdc.noaa.gov/

### Macroeconomic Data
- [Unemployment](https://fred.stlouisfed.org/series/UNRATE)
- [Inflation (CPI)](https://fred.stlouisfed.org/series/CPIAUCSL)
- [Interest Rates](https://fred.stlouisfed.org/searchresults?st=interest)
- [GDP](https://fred.stlouisfed.org/series/GDP)
- [S&P500 Index Returns](https://www.investing.com/indices/us-spx-500-historical-data)


## Project Considerations <a name="other"></a>
- **Observation:** Time-Commodity 
- **Sample period:** 1990-2019
- **Financial Theory:** Empirical research has found that found positive historical returns together with low or even slightly negative equity-commodity correlations and positive inflation-commodity correlations. This model may help exploit this arbritrage opportunity. However, the Efficient Market Hypothesis holds that asset prices reflect all available information - eliminating arbitrage opportunities. The predictive data the is being gathered is widely available and commodities are traded continuously at large volumes.

## Data Cleaning <a name="cleaning"></a>
Data was cleaned in this [file](https://github.com/lukecost/CommodityPrices/blob/main/data_cleaning.ipynb).

#### Points of Interest
- GDP is computed quarterly, so the 'nearest' method is used to fill in missing DSP data.
- Commodity price and climate data are merged with macroeconomic data to create one DataFrame.
- Commodity prices translated flot types, then used to calculate returns. **A sample of this is below.**


Unnecessary columns are removed, common timeframes are implimented, and a final DataFrame is created by merging all cleaned data. Cleaned data is exported to a CSV file for reusability.

``` python
Commodities_Final['realized_ret_corn'] = (np.log(Commodities_Final['Corn_Future_Price'].shift(-1)) 
                                       - np.log(Commodities_Final['Corn_Future_Price']))
                                       
```

## Regression
The file containing regression on our data can be found [here](https://github.com/lukecost/CommodityPrices/blob/main/part1_regressions.ipynb)

The goal of using regression on our data is to gain an initial understanding of the degree of correlation between the various independent variable in our dataset and the explanatory variables (returns of commodity futures). 

These regressions examine the relationship between commodity returns the data described above.

#### Market Risk Premium Varibale
- Computed the monthly returns for the sp500
- Used the .rolling() function to compute a rolling, 60 month period average of the s&p 500 returns.
- Calculated estimates for the market risk premium for each observation in our dataset by subtracting a monthly risk free - rate (0.407%) from our s&p 500 returns
- Used a weighted average to ensure positive market risk premiums
- This variable is crucial for the regressions.

With all variables loaded in, the StatsModels library and API are used for regressions. **Code for corn regressions are below**

``` python
corn1 = sm_ols('realized_ret_corn ~ (market_risk_prem)',data=Commodities_DF).fit()
```
# add key statns and interpretation here

Below is a heatmap that describes the relationship between all of our variables in the corn dataset.
<img src="pics/corn_heat.jpg" alt="Corn Heatmap"/>


## Predictive Modeling <a name="modeling"></a>
We separated the data to create training and holdout sets. The training set would be used to train the model, whereas the holdout set would be used to test the accuracy of our trained model. Data from years 1990 - 2014 (80%) was used as the training data to create a model for our testing data consisting of years 2015-2019 (20%). 

X variables (independent) are separated from the y variable (dependent) for the model. In this case, commodity returns are the dependent variable.


## Summary <a name="summary"></a>

Blah blah 


```python
import seaborn as sns 
iris = sns.load_dataset('iris') 

print(iris.head(),  '\n---')
print(iris.tail(),  '\n---')
print(iris.columns, '\n---')
print("The shape is: ",iris.shape, '\n---')
print("Info:",iris.info(), '\n---') # memory usage, name, dtype, and # of non-null obs (--> # of missing obs) per variable
print(iris.describe(), '\n---') # summary stats, and you can customize the list!
print(iris['species'].value_counts()[:10], '\n---')
print(iris['species'].nunique(), '\n---')
```
## About the team

<img src="pics/mike.jpg" alt="Michael Rich" width="300"/>
<br>
Michael Rich is a Financial Engineering major in Lehigh University's IBE program. He can be reached at mbr223@lehigh.edu.
<br><br><br>
<img src="pics/alex.jpg" alt="Alex Outkou" width="300"/>
<br>
Alex Outkou is a Finance and Business Information Systems double major at Lehigh University. He can be reached at ado323@lehigh.edu.
<br><br><br>
<img src="pics/luke.JPG" alt="Luke Costello" width="300"/>
<br>
Luke Costello is pursuing a degree in Finance at Lehigh University. He can be reached at lrc224@lehigh.edu
<br><br><br>
<img src="pics/harry.jpg" alt="Harry Herman" width="300"/>
<br>
Harry Herman is a Finance major at Lehigh University. He can be reached at hsh423@lehigh.edu.


## More 

To view the GitHub repo for this website, click [here](https://github.com/donbowen/teamproject).
