# Car-Price-Prediction-with-XGBoost
This work is for the participation the challenge mentioned in the title, aiming to predict used vehicle prices based on the data given.

## Dataset
We are given train.csv and test.csv, with the former (as the name suggests) having 12 features column an 1 target column of price. The test data lacks the target price column so has 12 columns.

The test data is usually large (from my experience), having about 36k rows compared to the 54k rows in the training dataset. (may make the prediction hard if the test data distribution is marginally different from training data?)

## Methodology
Off the top of my head I will approach this similar to my previous project where we follow the steps of:
1. data exploration: distribution, outliers, data types, correlation...
2. data preprocessing: data cleaning, feature engineering, train-test split
3. modeling: we are using XGBRegressor 
4. model training & evaluation: use random search to tune the hyperparameter, then train the final model on the full dataset
6. output generation

## Future Enhancements

1. Feature engineering:
* Create interaction terms, especially between continuous and categorical variables.
* Add polynomial features for continuous variables.

2. Handle outliers:
* Check for and handle outliers in continuous variables like 'price' and 'mileage'.

3. Separate validation set:
* Consider creating a separate validation set instead of using the test set for final evaluation.

4. Hyperparameter tuning:
* Consider using Bayesian Optimization, or hyperopt, ref stackoverflow [post](https://stackoverflow.com/questions/66463422/xgboost-parameter-tuning-random-search) instead of RandomizedSearchCV for more efficient hyperparameter tuning.

5. Ensemble methods:
* Try stacking with other models like LightGBM or CatBoost.
