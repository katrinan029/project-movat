# PROJECT MOVAT
Project Movat explores the obesity epidemic in the United States. This study uses county-level data to look for relationships in data on seven indicators that can be theoretically linked to obesity rates in order to attempt to predict how obesity rates vary bsed on these indicators. 

## Table of Contents
* [BACKGROUND](#background)
* [METHODOLOGY](#methodology)
* [RESULTS AND DISCUSSION](#results-and-discussion)
* [CONCLUSIONS AND RECOMMENDATIONS](#conclusions-and-recommendations)

## BACKGROUND
The obesity epidemic in the United States is an open secret; and an ongoing issue throughout the country. The issue has become increasingly worse over the years resulting in American food companies exporting the health crisis to development nations such as countries in Asia. With the advent of government-subsidized health insurance and the costs associated with commodities exacerbated by the condition, obesity can no longer be simply dismissed as merely a personal problem; it is now imperative to treat it as a public-health issue. Based on a series of discussions about the existing data sources, the project focused on six variables as predictors for obesity rates at the county level:
1. Median household income
2. Percent of adults with access to exercise opportunities
3. Percent of adults who are physically inactive
4. High school graduation rate
5. Primary care physician rate
6. Unemployment rate

 
* SCOPE AND LIMITATIONS
In using the above variables to model obesity data in the United States, the Movat team made the following assumptions:
a) the predictors of interest had direct and consistent relationships with the criterion variable.
b) The predictors of interest varied sufficiently enough to make their relationships with the criterion meaningful;
c) county-level data would be a valid proxy for individual data that wasn't available.
d) the variables above would be valid representations of the phenomena that they were being used as proxies for (e.g.) BMI classification for obesity rates, high school graduation rate for education, etc.);
e) relationships with respect to statistical variability point to, if not necessarily prove, valid causal relationships.
Should any of these assumptions be proven false, it would severely limit the validity of this analysis. 

## METHODOLOGY
* THE MULTIPLE REGRESSION METHOD
Multiple linear regression is an excellent exploratory method for determining the existence and intensity of relationships a criterion variable shares with several predictor variables. At its face, a multiple regression can explain the sources of variability in a dataset; and the contributions of each source to overall variability; as well as an estimate for predicted changes in the criterion based on changes in any single predictor. Multiple regression is particularly useful for producing predictive models that can be tested against new data to show how well a model performs.  Project Movat used a Python module called Stats models to perform these multiple regressions and concurrent modelling. In order to handle the large amount of data involved, a Python module called Pandas DataFrames was used. 
* DATA COLLECTION
Project Movat relied on existing datasets to perform its analyses. Countyhealth rankings,org provided a good aggregation platform for obtaining county-level data on a variety of indicators. For other predictors, we used an Application Program Interface. 
* PLOTTING THE DATA
In order to make valid plots of multi-variate data, a combination of Python libraries was used. The first was Matplotlib, which allows for easy plotting of data; and the second was “mpl toolkits” whose mpplot 3D-functionality allowed for the plotting of multivariate data. 

## RESULTS AND DISCUSSION
* MODELLING OBESITY RATES
Preliminarily, predictive models were constructed and refined using a sample of the ~350 counties of the three most populous states in the United States: California, Texas, and Florida 
When creating predictive models using multiple regressions, it is important to remember that the coefficient of determination, the Multiple R^2 is merely one overall number representing a model's ability to correctly predict all criterion values within the dataset. When the first model was tested, all six proposed predictors were used
 which produced a Multiple R of 0.98 (F=2886, p<.01. However, this model was also tested against all counties of the US which showed that the model was unstable likely due to overfitting. A new model took in the three best predictors from the first model: Physically Inactive Rate (p<.05), Median Income(p<.05), and Unemployment Rate (p<.05).
 The New three-predictor model (R^2=0.399, p<.01) was then tested against the full dataset ad performed respectably with less instability in the coefficients. This reduced model was then used to guide the estraction of permutations of two-predictor models for plotting. 
 
* MAIN EFFECTS
Of the six predictors of interest: Those that became part of the reduced model could reliably predict variations in obesity rate when considered independently. Physical Inactivity predicted a significant increase in obesity rate (95%CI: .459-.639) for every percentage point increase.  Unemployment Rate did the same (95% CI: 0.351-0.956); but this was found to be largely due to the near-nonexistence of variation in unemployment rates across the US (Plot 2.3). Moreover, as the next section discusses, significant interaction effects were found in the predictors which means that these regression coefficients should be taken with caution. 

* NOTEABLE INTERACTION EFFECTS
In almost every iterration of Movat models, statistcal analysis pointed to the possible of multicollinearities. Multiple regression can make predictions on the assuption that a predictor is acting without the influence of other predictors. This assumption cannot be accepted as true when multicollinearity is at work. To check for interaction effects due to collinearity, five two-predictor models were frmed and plotted.
Plot 3.5 considers a model where Physical Inactivity Rate works in tandem with Access to Exercise oppurtunities. This plot shows that regressing from Access to Exercise Rates may not always be accurate as its influence on obesity rate is mediated by  Physical Inactivity Rates. Simply put. Access ro Exercise Oppurtunities doesn't really predict Obesity Rates when people are unable or unwilling to use such oppurtunities. 
Plot 3.1 considers the influence of Physical Inactivity against that of Median Income. While both appear to predict a great deal of variability in Obesity Rates, the influence of Physical Inactivity appears to diminish in medium to high income counties as opposed to lower-income counties. However, it's not clear how much of this is genuine interaction; and how much is caused by the simple fact that there are fewer higher-income counties than lower-income ones. 
Plot 3.2 is a more straightforward figure plotting the interaction between High School Graduation Rates and Access to Primary Care Physicians. It shouldn't be surprising that obesity rates are lower in counties with high graduation rates and high physician access. However, the influence of High school graduation rates appears to increase as primary care physician access rate decreases. It appears that expert opinion matters more in mitigating obesity rates when people are less equipped with the education to make healthier decisions on their own. 

## CONCLUSIONS AND RECOMMENDATIONS

### CONCLUSIONS
The layman's understanding of the obesity epidemic is an oversimplified abstraction. Obesity cannot be simply associated with one factor or another, whether social or health related. 
It may turn out that solutions to the obesity epidemic require a nuanced understanding of the interactions that occur between multiple contributory variables. While access to exercise opportunities was found to have consistently robust predictive relationship with obesity rates(around a .5 percentage decrease in obesity for every additional percentage with access to exercise opportunities once other predictors are controlled for.), this relationship is also mediated by the inactivity rates of adults in a county. Similar interactions were plotted for various combinations of predictors. 

### RECOMMENDATIONS
A government committed to fighting the obesity epidemic may ask how to best combat this public health crisis. The truth is that Project Movat cannot answer this question definitively. The best that can be said is that this project has laid out a map for which variables have strong correlations with obesity rates; and that more dedicated researchers might examine whether these correlations translate to causal relationships. Without proper research on causality, Project Movat will sadly not be helpful in informing public policy. For everything that has been said, any effort to parse conclusions out of regressions that display substantial interaction effects should  approach these findings.  with appropriate caution. The same must be said of any effort to use an analysis of county-level data to prescribe interventions for individuals. 
