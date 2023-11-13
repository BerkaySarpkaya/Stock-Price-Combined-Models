## Stock-Price-Combined-Models
This is a Stock Price Prediction Project with multiple models in order to compare the results. Data is derived from AlphaVantage.com through its API.

<!--ts-->
* [Objective](#Objective)
* [Requirements](#Requirements)
* [Dataset](#Dataset)
* [Data Preparation](#Data-Preparation)
* [Model Selection and Evaluation](#Model-Selection-and-Evaluation)
* [Inferences](#Inferences)
* [License](#License)
<!--te-->

## Objective

This repository contains an experiment to see how different models will predict the future of a stock data. All the models was fed with the first 90% of the stock history so that they can forecast the last 10 percent.

## Requirements

- Python Version: 3.11.6
- Pandas Version: 2.1.1
- Numpy Version: 1.24.4
- Matplotlib Version: 3.8.0
- Seaborn Version: 0.13.0
- Tensorflow Version: 2.13.0
- Scikit-Learn Version: 1.3.1
- pmdarima Version: 2.0.4
- statsmodels Version: 0.14.0
- Prophet Version: 1.1.4

The overview of the code can be seen on the following link <a href="https://github.com/BerkaySarpkaya/Stock-Price-Combined-Models/blob/main/WBS%20of%20Model%20File.txt"> Overview of the code</a>

## Dataset

Over 20 years of Berkshire Stock data was pulled from the AlphaVentage's website through its API, <a href="https://www.alphavantage.co/documentation/"> see the link</a>.

## Data Preparation

- Data was in JSON format. It was transformed into a dataframe on the first notebook <a href="https://github.com/BerkaySarpkaya/Stock-Price-Combined-Models/blob/main/Data-Collection-API.ipynb"> Data-Collection-API </a>.
- Missing days was filled with forward filling.

## Model Evaluation

### _Model Selection_

Forecasting the future of stock data is a challenging task due to the uncertainties in financial markets and numerous factors. In this context, the results of the modeling study evaluated the performance of five different models: Holt-Winters, AR (AutoRegressive), ARIMA (AutoRegressive Integrated Moving Average), LSTM (Long Short-Term Memory), and Prophet.

### _Model Evaluation_

- The refrence model had high bias and low variance with the accuracy score of 0.872 on train and 0.879 on test data.

- Among all the different cases, the normalized and dimensionality reduction applied dataset with catboost algorithm had the best accuracy of 0.9639 with the following confusion matrix

<img src="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/Images/Confusion-Matrix-DR-Normalized-Catboost.PNG" alt="Figure 1">

<em>Figure 1. Confusion matrix of the catboost model - 96.39% accuracy on validation set</em>

- After Hyperparameter tuning held on the final model with 3 degree of cross-validation, accuracy had slightly increased to 0.9641 on validation set, while having an accuracy score of 0.9785 on training set. These results indicates that the high bias problem of reference model has been solved with keeping the variance as low, indicating there is no high bias or overfitting problem.

- The final model's accuracy score was 0.9666 on the Test Set with confusion matrix:

<img src="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/Images/Best%20Catboost-Test%20Set.PNG" alt="Figure 2">

<em>Figure 2. Confusion matrix of the hyperparameter tuned catboost model - 96.66% accuracy on test set</em>

## Inferences

- In the all cases of different scaling methods X different models: Boosting Decision Tree methods were always the winners with the lead of catboost and lightgbm
- Top 5 models were always the Catboost, LightGBM, XGBoost, Extra Trees and Random Forest. Their performance almost did not change according to the scaling method as expected.
- Among the scaling methods, only no scaled (raw) data changed the performance of NN model dramatically with a possible reason of ineffective gradient descent process caused by oscilating with large moves. 

## License

This project is licensed under the MIT License. See the <a href="https://github.com/BerkaySarpkaya/Stock-Price-Combined-Models/blob/main/LICENSE"> LICENCE</a> file for details.
