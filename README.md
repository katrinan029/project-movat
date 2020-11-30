# PROJECT MOVAT
Project Movat explores the obesity epidemic in the United States. This study uses county-level data to look for relationships in data on seven indicators that can be theoretically linked to obesity rates in order to attempt to predict how obesity rates vary bsed on these indicators. 

## Table of Contents
* [BACKGROUND](#background)(#scope-and-limitations)
* [METHODOLOGY](#methodology)
* [RESULTS AND DISCUSSION](#results-and-discussion)
* [CONCLUSIONS AND RECOMMENDATIONS](#conclusions-and-recommendations)

## BACKGROUND
The obesity epidemic in the United States is an open secret; and a persistent butt of jokes and internet memes. It has gotten so
bad that American food companies have ended up up exporting this health crisis to developing nations in Asia. Wth the advent of government-subsidized health insurance and the costsassociated with comorbidities exacerbated by the condition, obesity can no longer be simply dismissed as merely a personal problem; it is now imperative to treat it as a public-health issue. Based on a series of discussions about the existing data sources, the project focused on six variables as predictors for obesity rates at the county level: 
1. median county income: the income of the 50th percentile in a given county. 
2. percent of adults with access to exercise oppurtunities: 
3. percent of ddults who are physically inactive:
4. high school graduation rate:
5. Primary care physician rate: 
6. Unemployment rate:
 
* SCOPE AND LIMITATIONS
In using the above variables to maodel obsity data in the United States, the Movat team necesarilly had to make certain assumptions: 
a.) the predictors of interest had direct and consistent relationships with the criterion variable.
b.) The predictors of interest varired sufficiently enough to make their relationships with the criterion meaningful. 
c.) that county-level data would be a valid proxyfor individual data that wasn't available. 
d.) that the variables abve would be valid representations of the phenomena that they were being used as proxies for (e,g. BMI classification for obesity rates, high school graduation rate for education, etc.)
e.) that relationshps with respect to statistical variability point to valid causal relationships


## METHODOLOGY
* THE MULTIPLE REGRESSION METHOD
Multiple linear regression is an excellent exploratory method for determining the existence and intensity of relationships a criterion variable shares with several predictor variables. At its face, a multiple regression can explain the sources of variability in a dataset; and the contributions of each source to pverall variability; as well as an estimate for predicted changes in the criterion based on changes in any single predictor. Multiple regression is particularly useful for producing predictive modelss that can be tested against new data to show how well a model performs.  Project Movat used a Python module called Statsmodels to perform these multipl regressions and concurrent modelling. 
* DATA COLLECTION
Project Movat relied on existing datasets to perform its analyses. Countyhealth rankings,org provided a good aggregation platform for obtaining county-level data on a varirty of indicators. For other predictors, we usedan Application Program Interface 
* PLOTTING THE DATA


## RESULTS AND DISCUSSION
* MODELLING OBESITY RATES
Preliminarily, predictive models were constructed and refined using a sample of the ~350 counties of the three most populous states in the United States: California, Texas, and Florida 
When creating predictive models using multiple regressions, it is important to remember that the coefficient of determination, the Multiple R^2 is merely one overall numberrepresenting a model's ability to correctly oredict all criterion values within the dataset. When the first model was tested, all seven proposed predictors were used

* MAIN EFFECTS
* NOTEABLE INTERACTION EFFECTS

## CONCLUSIONS AND RECOMMENDATIONS

### CONCLUSIONS
The layman's understanding of the obesity epidemic is an oversimplified abstraction. Obesity cannot be simply associated with one factor or another, whether social or health-related. 
It may turnout that solutions to the obesity epidemic require a nuanced understanding of the interactions that occur between multiple contributory variables. While access to exercise oppurtunities was found to have consistently robust predictive relationship with obesity rates(around a .5 percentage decrease in obesity for every additional percentage with access to exercise oppurtunities once other predictors are controlled for.), this relationship is also mediated by theinactivity rates of adults ina county. Similar interactions were plotted for various combinations of predictors. 

### RECOMMENDATIONS
A government commited to fighting the obesity epidemic may ask how to best combtat this public health crisis. The truth is that Project Movat cannot answer this question definitively. The best that can be said is that this prject has laid out a map for which variables have strong correlations with obesity rates; and that more dedicated researchers might examine whether these correlatons translate to causal relationships. Without proper research on causality, Project Movat will sadly not be helpful in informing public policy.For everything that has been said, any effort to parse conclusions out of regressions that display substantial interaction effects should  approach these findings.  with appropriate caution. The same must be said of any effort to use an analysis of county-level data to prescribe interventions for individuals. 
