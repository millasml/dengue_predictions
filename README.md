# DengAI: Predicting Disease Spread - My Attempts

## Welcome!
I started on this data competition on the 4th of Febuary, 2020. It is still in progress. Check out the competition details at https://www.drivendata.org/competitions/44/dengai-predicting-disease-spread/

## First Steps
The first thing i did was train an XGBoost model because its the quickest, and I just wanted to play around for awhile. It returned with an MAE of around 15, which is not too shabby for a first try.

## Trying to Refine the Gradient Boosting 

### City Split
Doing the city split somehow did not improve my accuracy, even though it should. Should tweak the parameters to account for the smaller data set per model.

### Only features with high correlation
Using only features with high correlation increased accuracy significantly. Possible to do PCA to get the best features

## Giving up on Gradient Boosting - LSTM Here we come
Gradient boosting models provide a very weak baseline. Hence, I am now exploring RNN in the form of LSTM. I also realized that i made a mistake in the test-train split - as this is time series data, I should split such that the test data is a continuous future, rather than random points in time.

Using LSTM was a good move - without any preprocessing, i managed to get a MSE of 28. This was lower than all the MSEs achieved with gradient boosting, along with city split and feature selection

### LSTM with Feature Selection
With a time step of 1, and using only the 4 features with high correlation. Managed to get a MSE of 26, finally putting myself in the top 20%!

# TO-DO
1. LSTM Tinkering
2. Look into PCA
