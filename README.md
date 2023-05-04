# Impact on GDP Growth Worldwide"

# Abstract

To investigate the relationship between fertility and GDP growth rate by controlling some other variables like population GDP, urban population percentage, we collected data from United Nation among 166 countries. After EDA and fitting the linear regression model, we concluded that fertility is negatively related to the growth rate. So, for countries who want to boost their GDP growth rate, improving fertility rate is not considered a wise practice.


# Introduction

The relationship between fertility, population growth and economic growth is complex. The initial research in this field mainly focused on the relationship between population and economy and society. Since then, scholars have gradually found that population structure rather than total population is the main factor affecting economic growth, and demographic dividend is associated with fertility rate change.

In ancient times, the abundance of the population was often a symbol of a nation's wealth because of the high mortality rate. In the era of mercantilism in Western Europe, some people have advocated increasing the working population, believing that a large population is a good thing and conducive to economic growth. However, according to Malthus's Essay on Population, the growth of population always exceeds the growth of the means of subsistence, so that unemployment, poverty, hunger and evil are inevitable, which are determined by the "natural law of population" that has nothing to do with the social system. From this point of view, more population is not better, so we can also say that higher fertility is not better.

Based on the above theoretical basis, the hypothesis of this paper is that countries with higher fertility rates will have slower economic growth. Therefore, this paper uses the statistical data of the United Nations, selects the corresponding variables, and uses the least square method to establish an econometric model to test this hypothesis.

# Data & EDA

The data comes from United Nations National Statistics, a sample of 166 countries. The variables included are GDP growth rate(gr), total fertility rate(fertility), GDP per capita in US dollars(ppgdp), female life expectancy(lifeExpF), percent of population in urban areas(pctUrban) and infant deaths by age year per 1000 live births(infantMortality). In addition, it's worth noting that the data are averages from 2009 to 2011. Finally, table 1 below shows the meanings and symbols of the variables.

<table>
<caption><span id="tab:table1">Table 1: </span>Data description</caption>

Variable       Introduction
-------------  ---------
gr             GDP growth rate
fertility      total fertility rate
ppgdp          GDP per capita
lifeExpf       female life expectancy
pctUrban       percent of population in urban areas
infatMortility infant deaths by age year per 1000 live births

</table>

Further some exploratory analysis is useful to find out information from the data. The GDP growth rate has an average level of 2.2%, with -3% the lowest and around 9% the highest (excluding an extreme value at around 18%). Fertility if averaging at 2.7%, ranged from 1.1% to 6.9%.

When comparing the average GDP growth rate over each region, basing on the given data set, we find out that, generally Asian and European countries have higher GDP growth rate. Among these selected Asian countries, China has a GDP growth rate of 9.3, which is the highest. In European, Bosnia and Herzegovina as a GDP growth rate of 8.3, which is the highest among all other countries in European region. But when we look at the fertility rate in Asian and European countries, the average level of fertility rate are 2.3 and 1.6 respectively, comparing to those in Africa(4.26) and Oceania(3.28). That also explained the low GDP growth rate we find from these 2 regions, where Africa has around 1.8 and Oceania is at 1.08 only. We are considering that the growth rate and fertility is negatively related, which is correct from the scatter plot below. In comparing population GDP, European countries are ranking top and African countries are ranking the bottom.

This finding matches our research results on fertility and growth rate. A higher fertility rate would cause serious social issues, including heavier burden in maintaining the whole society including healthcare, infrastructure investment, public security, education and more. These would prevent the country from fast economic growth. While in countries with especially those with higher path of development, people have more options pursuing a better living conditions and would put more things into consideration before fertility. 




Further we can run a correlation matrix. Correlation, or pearson correlation is measuring the inner relationship between 2 variables. From the correlation matrix below, we see that the correlation between fertility and growth rate are -0.22, which is a negative value. This means that a higher fertility rate may lead to a lower GDP growth rate. population GDP is also negatively correlated to the growth rate. We can interpret it as countries with high level of population GDP are hard to have a fast growth rate, which is true for many developed countries.

Another interesting finding from the matrix is that female life expectancy is positively correlated to growth rate, which means female with longer life expectancy would benefit the GDP growth. The reason could be various. Female with longer life would probably mean the society is equally treated females, and females are more likely to contribute to the growth rate of GDP. another way to look at it is that longer life is related to improved health system and living quality, which is true in fast developing countries.



# Modeling & Method

To analyze the impact of fertility rate on economic growth, this paper chooses GDP growth rate(gr) as the explained variable, fertility rate(fertility) as the core explanatory variable, and the remaining variables as control variables. And then we can test and run linear regression models and find out a better performed model basing on its complexity, test statistic and R-square(Adjusted R-square). But before all these steps, first we need to test for the assumption of linear regression model.

Under this circumstance, we need to test 2 parts. The first one is outliers. We know that outliers could do harm to the performance of the model. After we draw the histogram of growth rate, we accidentally found an extreme value at 18.2%. Considering that we already have 166 observation in total, removing one observation is acceptable to the data set and model. On the other hand, since each row of data is about a specific country, so method that replacing extreme values may not be suitable here. So we just go delete that row from the dataset for further steps. See below.

Then we want to make sure that our data are not skewed. After drawing multiple histogram on these exploratory variables, we find these four variables("lifeExpF", "ppgdp", fertility", and "infantMortality") are skewed, to make sure we meet the assumption for the linear regression model, a nature way is doing log transformation. So, before testing regression models, wee took the log transformation on these four variables. After that we created 4 new variables names "LlifeExpF", "Lppgdp", "Lfertility", and "LinfantMortality", which are the log value of  "lifeExpF", "ppgdp", "fertility", and "infantMortality". Not only in this we we can fix the skewness of these variables, but also we are able to adjust the magnitude so our coefficients are not too large or too small to inteprete.

After all these steps we now can run linear regression models on "gr", explained by "Lfertility", "ppgdp", "LlifeExpF", "LinfantMortality" and "pctUrban". We will use these variables instead of original variables to run further analysis, like calculating key statistics, and performing linear regression with these variables. Comparing to those original variables without log transformation, we now able to meet the assumption of normality which is required if we want to run a linear regression model.

\newpage


# Result

Before running the regression model, we can find some descriptive statistic of the data were first performed after removing outliers as in the Table 2 below:


Variable          Mean     
-------------     --------- 
gr                2.155         
Lfertility        0.9076
Lppgdp            8.424
LlifeExpf         4.269
pctUrban          56.6
LinfatMortility   2.8892


Overall,the variables remain almost in the same order of magnitude. Next, the least squares method (OLS) is used to complete the estimation of the previous econometric model, and the parameter estimation results are shown in Table 3. 

Variable          Coefficient     Std. Error       t-value      Pr(>|t|)
-------------     ---------       -----------      --------     ---------
(Intercept)       -0.175349       9.210165         -0.019       0.9848
Lfertility        -3.067788       0.560073         -5.477       1.65e-07
Lppgdp            -0.101563       0.225360         -0.451       0.6528      
LlifeExpf         1.242057        1.881511         0.660        0.5101
pctUrban          0.532040        0.357595         1.488        0.1388
LinfatMortility   -0.015355       0.009165         -1.675       0.0958


It can be found that the regression coefficient of fertility is significantly negative at the 1% level, which indicates that the higher the fertility rate, the slower the GDP growth rate, which verifies the hypothesis of this paper. The model could be write down as:

gr = -0.175 - 3.068log(fertility) - 0.102log(ppgdp) + 1.242log(lifeExpF) +
0.532log(infantMortality) - 0.015pctUrban


# Conclusion

In this paper, GDP growth rate is taken as the proxy variable to measure the national economic growth rate, which is also taken as the explained variable, and fertility rate is taken as the explanatory variable. In addition, GDP per capita, female life expectancy, percent of population in urban areas and infant deaths by age year per 1000 live births are also introduced as control variables. We think that higher fertility tends to be accompanied by lower GDP growth. Finally, the least square method is used to construct an econometric model to test this hypothesis.

According to the regression results of the model, it can be seen that the regression coefficient of fertility rate is significantly negative at the level of 5%, which indicates that fertility rate will inhibit the economic growth rate, and this conclusion verifies the hypothesis of this paper.

In view of this conclusion, this paper holds that the government should not blindly emphasize the high fertility rate in the process of economic development, but should appropriately reduce the fertility rate.


# Discussion

There are aspects we could improve our researching process. First, the data set is good enough for use to generate an actionable suggestion to the government. We have only 166 countries within the study and teh time range is limited, if possible, we should consider enlarge our data size so numbers are more accurate. On the other hand, our data sampling process would be biased since most selected countries are UN members, so the effect of UN should also be treated as a control variable or we should perform sampling in a more random way.

To the model, usually we should have a way to evaluate its performance. Here we see an adjusted R square be 0.2116, it is good when working on real-world data, but still there are spaces we can improve the exist model. We can perform step-wise variable selection that excludes variables that lower the overall significance. And also we can use some more data to test the accuracy of our model and score its 


