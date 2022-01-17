
# Analysis of Life Expectancy

Throughout this data analysis project we will try to see the relationship between Gross Domestic Product (GDP) and life expectancy of 6 countries (Chile, Germany, USA, Mexico, China and Zimbabwe) from 2000 to 2015.
## Authors

- [@Ismaelpbla](https://github.com/Ismaelpbla)


## DATA

In this project we are going to analyze life expectancy in different countries.
For this we are going to use the csv file that has been provided to us 
at Codecademy: all_data.csv.

In a first glance at the first 5 data we see the following:

|  Country |Year   |Life Expectancy at birth (years)   |GDP   |
|---|---|---|---|
|   Chile|   2000|   77.3|   7.786093e+10|
|   Chile|   2001|   77.3|   7.097992e+10|
|   Chile|   2002|   77.8|   6.973681e+10|
|   Chile|   2003|   77.9|   7.564346e+10|
|   Chile|   2004|   78.0|   9.921039e+10|

If we look at the last 3 data we see something different:

|   Country|   Year|Life Expectancy at birth (years)    |GDP   |
|---|---|---|---|
|   Zimbabwe|   2013|   58.0|   1.545177e+10|
|   Zimbabwe|   2014|   59.2|   1.589105e+10|
|   Zimbabwe|   2015|   60.7|   1.630467e+10|

From these views we can deduce that the Dataframe is composed of 4 variables.
Two of them are quantitative variables (Life Expectancy at birth (years) and GDP), 
while the other two ('Country' and 'Year') are qualitative variables that are alphabetically and numerically
are organized alphabetically and numerically from highest to lowest respectively.

In this Dataframe we handle 96 data, so it is not necessary to apply SQL, since this amount of data is very manageable.
is very manageable.

The dtypes of each of the variables are consistent with respect to the type of variables they are: year is int64, Country is Object and Life expectancy at birth (years) and GDP are float64.
and GDP are float64.

If we observe the maximum and minimum values we see:

- That the most recent year is 2015 and the oldest is 2000.
- That the life expectancy variable is a minimum of 41 years and a maximum of 81 years.
- That the minimum value of the GDP of all countries is approximately 4000 million and the maximum value is 18 trillion 100 million.

The mean of the quantitative variables are:
- 72.8 years in terms of life expectancy for all countries with a standard deviation of 10.67
- 3.880 trillion for GDP with a standard deviation of 5.2 trillion.

Seeing that there is a big difference between the minimum, the mean and the maximum value in the case of GDP
in the case of the GDP variable, we calculate the coefficient of variation, observing that:
- The life expectancy variable has a coefficient of variation close to 0
so that there is little variability.
- The GDP variable, on the other hand, has a coefficient of variation close to 1, so that there is a lot of variability.
so that there is a lot of variability.

## LIMPIEZA DE DATOS

At the first glance we have taken at the Dataframe it looks like the data is pretty clean. However, let's check a few things:

If there are Missing Data
If there are duplicates
Check inconsistent data (Capitalization, Formats, and syntax errors)

Using the heatmap method, we observe that there is no missing data in the entire dataframe.

We check that there are no duplicates in the whole dataframe using the duplicated() method.

There is no inconsistent data, but the name of the variable "Life expectancy at birth (years)" is too long and will give us problems in the future. So we are going to rename it with the rename() method to 'Life_exp'.

We also changed the name from "United States of America" to "USA", for the same reasons. This time we used the .replace() method.



## DATA ANALYSIS

In this dataframe we can make a quite obvious comparison, and that is, how has life expectancy varied from 2000 to 2015 in the 6 countries of the dataframe?

First we must extract from the dataframe 6 tables with the 6 different countries.

Then we will make a figure in which we will project, for each country, the life expectancy vs. the variable Year, in order to see how life expectancy has varied in 15 years, from 2000 to 2015.

However, how life expectancy has varied does not tell us much. We can observe how there are some countries like Chile or Mexico that have moments in which their life expectancy decreases rapidly, and then rises again. And countries like China, USA or Germany whose life expectancy increases gradually over time.

Zimbabwe is the only one that presents a very particular evolution of its life expectancy, different from the rest. It can be observed how life expectancy decreases a lot from the year 2000 to 2004 and from there it grows again almost exponentially.

Although it is interesting to analyze the evolution of life expectancy, in our database we have another variable which is the Gross Domestic Product (GDP) of each country. Is there any relationship between life expectancy and GDP of each country?

We are going to project on the same graph as life expectancy, the GDP of each country. To do this we will use the twinx() method.

![set image](https://raw.githubusercontent.com/Ismaelpbla/Life_Expectancy/7df87fe0179e0187b5930034a50f26deac9d6b81/Figures/Lineplot.png)
#### Figura 1

Looking at the two line graphs, we see that there is a clear relationship between these two variables, which can be observed in all countries:

# CONCLUSIONS


The relationships that can be observed between life expectancy and GDP in each country are as follows:

a) In Chile it can be seen how both curves run parallel until 2010 in which there is a decrease in life expectancy, this may be due to a decrease in the birth rate as there was a period of economic recession during 2008 as can be seen in the GDP curve.

b) In Germany, the economic crises of 2008 and 2012 and their corresponding recoveries in 2010 and 2014 can be seen very well. Both periods of economic recovery are associated with increases in life expectancy.

c) The United States presents an almost perfect coincidence between GDP and life expectancy. A greater separation between the two curves was seen in the global economic crisis of 2008. The increase in life expectancy slowed down two years later, probably due to the 2008 crisis.

d) Mexico had the largest decline in GDP of all the countries in this analysis, also during 2008. This had a considerable impact on life expectancy. It is curious to note the increase in life expectancy that occurred just at the time of the lowest GDP in the country.

e) China has a symmetrical distribution between life expectancy and GDP. While GDP increases exponentially since 2000, life expectancy tends to stabilize at 76 years.

f) Finally, in Zimbabwe we can also observe how the 2008 crisis affected its already damaged economy. But life expectancy continued to grow exponentially since 2004 regardless of this period of crisis. It is worth noting the coincidence of the increase in life expectancy and GDP in this country between 208 and 2011.

In general terms, it can be observed in all countries:

- That the economic crises and the loss of wealth of the countries affect, a few years later, their life expectancy.
- That economic recoveries imply exactly the opposite, i.e. the greater the wealth, the longer the life expectancy.
- That these last two conclusions are not applicable to all countries, there are exceptions such as China or Zimbabwe where the effects of the increase are not seen.

