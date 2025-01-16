This demo came about because I was thinking about how to deal with intercorrelation when ensembling several forecasts (e.g. if you try to mix together 10 different predictions of the weather tomorrow to create a single better quality prediction of tomorrow's weather) in a linear model.

Suppose you have n forecasts for some target variable - e.g. a dataset containing n predictors which should be positively correlated with the target column. What happens if you try ensembling the forecasts with a simple linear model, but you end up with some negative coefficients in your ensembling model?

We know that each feature is positively correlated with the target, and (assume) we have some prior that an increase in one forecast/feature should mean we increase our own prediction (and vice versa), so I don't really like this fit. It suggests that the negative coefficient is being used to fit the idiosyncratic noise shared between the predictors which is risky business when we don't have too much data to work with.

Here I try to demo and then resolve the issue.
