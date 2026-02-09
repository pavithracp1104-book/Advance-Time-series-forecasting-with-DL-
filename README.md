Advanced Time Series Forecasting with Deep Learning and Explainability
1. Project Overview

This project implements an advanced time series forecasting system using deep learning and explainability techniques. A Long Short Term Memory neural network is used to perform multi step forecasting on a real world financial time series dataset. The project moves beyond traditional statistical models by comparing the deep learning approach against a classical SARIMA baseline. Post hoc explainability is applied to interpret which historical time steps most influence future predictions.

2. Objectives

Build a deep learning model for time series forecasting using LSTM

Perform multi step forecasting on a complex real world dataset

Apply data preprocessing including normalization and sequence windowing

Compare performance against a strong statistical baseline model

Use explainability techniques to interpret temporal dependencies

Demonstrate actionable insight generation in addition to predictive accuracy

3. Dataset Description

Source
S and P 500 Index data downloaded from Yahoo Finance

Type
Real world financial time series

Time period
2010 to 2024

Target variable
Daily closing price

This dataset is non stationary and noisy which makes it suitable for advanced deep learning based forecasting.

4. Data Preprocessing

The following preprocessing steps are applied

Removal of missing values

Min Max normalization

Sliding window sequence generation

Input sequence length of 30 time steps

Forecast horizon of 5 future steps

Train and test split of 80 percent and 20 percent

5. Deep Learning Model

The forecasting model is based on a stacked Long Short Term Memory architecture.

Model details

Two LSTM layers

Sixty four hidden units

Dropout regularization

Fully connected output layer

Adam optimizer

Mean squared error loss function

The model is trained to predict multiple future time steps simultaneously.

6. Forecasting Setup

The model performs multi step forecasting for the next five time steps. For evaluation and explainability stability the first forecasted step also referred to as t plus one is used for detailed analysis.

7. Evaluation Metrics

Model performance is evaluated on a held out test set using the following metrics

Root Mean Squared Error

Mean Absolute Error

These metrics are reported for both the deep learning model and the baseline model.

8. Baseline Model

A Seasonal Autoregressive Integrated Moving Average model is implemented as a baseline.

Baseline details

SARIMA with seasonal components

Trained on the same dataset

Evaluated using the same test horizon

Used to compare classical and deep learning approaches

9. Explainability Method

Post hoc explainability is implemented using SHapley Additive exPlanations.

Explainability process

Historical time steps are treated as individual input features

SHAP values are computed for the t plus one forecast

Feature importance indicates which past time steps most influence predictions

This approach provides interpretability for the deep learning model without modifying its architecture.

10. Results and Insights

The LSTM model demonstrates improved forecasting performance compared to the SARIMA baseline

SHAP analysis shows that recent historical time steps have the highest influence on future predictions

The model successfully learns temporal dependencies present in the financial time series

11. Project Structure

Single Python file containing data preprocessing training evaluation and explainability

README file describing methodology and results

The program is designed to run as a single cell in a Jupyter Notebook environment.

12. How to Run

Install required Python libraries

Run the Python program or execute it in a single Jupyter cell

The program will automatically download data train models evaluate performance and generate explainability outputs

13. Conclusion

This project demonstrates the application of deep learning to advanced time series forecasting while maintaining interpretability through explainability techniques. By combining LSTM based forecasting with SHAP analysis the project delivers both predictive performance and actionable insights into temporal behavior.
