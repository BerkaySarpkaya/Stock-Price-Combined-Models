## Stock-Price-Combined-Models
This is a Stock Price Prediction Project with multiple models including LSTM and Prophet in order to compare the results. Data is derived from AlphaVantage.com through its API.

<!--ts-->
* [Objective](#Objective)
* [Requirements](#Requirements)
* [Dataset](#Dataset)
* [Data Preparation](#Data-Preparation)
* [Model Evaluation](#Model-Evaluation)
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

Forecasting the future of stock data is a challenging task due to the uncertainties in financial markets and numerous factors. Therefore, it is often difficult to detect seasonalities in stock data. In this context, the results of the modeling study evaluated the performance of five different models: Holt-Winters, AR (AutoRegressive), ARIMA (AutoRegressive Integrated Moving Average), LSTM (Long Short-Term Memory), and Prophet.

<img src="https://github.com/BerkaySarpkaya/Stock-Price-Combined-Models/blob/main/Images/All%20Models.png" alt="Figure 1">
<em>Figure 1. Real Data vs Model Predictions</em>

<img src="https://github.com/BerkaySarpkaya/Stock-Price-Combined-Models/blob/main/Images/Model%20Comparison.png" alt="Figure 2">
<em>Figure 2. Model Comparison</em>


It is noteworthy that the Holt-Winters model has high error rates comparing to AR and ARIMA models. AR and ARIMA models outperformed the others. These models are known for their ability to predict future trends and changes based on past price movements. However, the LSTM and Prophet models did not perform as well as expected in this particular case, despite offering deeper and more flexible approaches to better understand and learn the complexities of stock data over time.

Possible reasons for the low success rates of the LSTM and Prophet models may include the size of the dataset, the choice of features, or the appropriateness of the model hyperparameters. To achieve impressive results in financial markets, these models may need to be more carefully tuned and better adapted to the dynamics specific to a given asset class.

## License

This project is licensed under the MIT License. See the <a href="https://github.com/BerkaySarpkaya/Stock-Price-Combined-Models/blob/main/LICENSE"> LICENCE</a> file for details.
