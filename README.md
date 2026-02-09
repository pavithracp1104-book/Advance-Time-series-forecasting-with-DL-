Advanced Time Series Forecasting with Deep Learning and Explainability
1. Project Description

This project implements and evaluates a deep learning based time series forecasting model using a Long Short Term Memory neural network. The objective is to perform multi step forecasting on a real world financial time series and compare its performance against a classical statistical baseline model. In addition to prediction accuracy, post hoc explainability techniques are applied to interpret how historical time steps influence future forecasts.

2. Dataset Used

Dataset
S and P 500 daily closing price data

Source
Yahoo Finance

Time span
2010 to 2024

Target variable
Daily closing price

The dataset exhibits non stationarity, volatility clustering, and long term temporal dependencies, making it suitable for deep learning based sequence modeling.

3. Data Preprocessing

The following preprocessing steps were implemented in the program

Removal of missing values

Scaling using Min Max normalization

Sliding window sequence generation

Input sequence length of 30 historical time steps

Multi step forecasting horizon of 5 future time steps

Train test split of 80 percent training and 20 percent testing

The processed data was reshaped into three dimensional tensors suitable for LSTM input.

4. Deep Learning Model Architecture

The forecasting model is a stacked Long Short Term Memory network implemented in Python.

Architecture details

Input layer receiving sequences of length 30

First LSTM layer with 64 hidden units and sequence output enabled

Second LSTM layer with 64 hidden units

Dropout layers applied to reduce overfitting

Fully connected dense output layer producing multi step forecasts

Training configuration

Optimizer Adam

Loss function Mean Squared Error

Early stopping based on validation loss

5. Forecasting Strategy

The model performs multi step forecasting for five future time steps. For evaluation and explainability consistency, the first predicted step t plus one was used for detailed metric reporting and SHAP analysis.

6. Baseline Model

A Seasonal Autoregressive Integrated Moving Average model was implemented as a classical baseline.

Baseline characteristics

SARIMA model trained on the same training data

Forecast horizon matched to the LSTM model

Evaluated using the same test set

Performance compared using identical error metrics

7. Evaluation Metrics and Results

The trained models were evaluated on the held out test set using Root Mean Squared Error and Mean Absolute Error.

LSTM t plus one results

RMSE
93.17507047219262

MAE
76.13423047434635

SARIMA results

RMSE
961.2020148744957

MAE
892.7866085929627

8. Performance Analysis

The LSTM model significantly outperforms the SARIMA baseline on both evaluation metrics. The large error values observed in the SARIMA model indicate its inability to capture complex non linear temporal dependencies present in the financial time series. In contrast, the LSTM model effectively learns long range patterns and short term dynamics, resulting in substantially lower prediction error.

9. Explainability Method

Model interpretability was achieved using SHapley Additive exPlanations.

Explainability setup

Historical time steps were treated as individual input features

Input sequences were flattened for compatibility with SHAP KernelExplainer

SHAP values were computed for the t plus one forecast output

10. Explainability Results and Interpretation

The SHAP analysis shows that recent historical time steps have the strongest influence on the model’s predictions. Time steps closest to the forecast horizon contribute most positively or negatively to the predicted value, while older time steps have diminishing influence. This behavior aligns with financial intuition, where recent market movements tend to have a stronger impact on short term price forecasts.

11. Project Implementation Details

Complete runnable Python code implemented in a single notebook cell

Data preprocessing, model training, evaluation, and explainability included

Visualizations generated for predictions and SHAP feature importance

All results derived from actual model execution

12. Conclusion

This project demonstrates that deep learning based sequence models can significantly outperform classical statistical methods for complex time series forecasting tasks. By integrating SHAP based explainability, the project not only achieves strong predictive performance but also provides interpretable insights into temporal dependencies learned by the model.
