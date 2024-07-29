
#this model will predict the trend(up/down) of futer 10th minut based on tha analysis of past 40 min

# AMD Stock Price Prediction Using LSTM

## Overview

This project aims to predict the future price movements of AMD stock using Long Short-Term Memory (LSTM) networks. The focus is on predicting the sign (positive or negative) of price changes over the next 10 minutes based on the past 40 minutes of trading data. This approach helps in short-term trading and scalping strategies.

## Project Workflow

1. **Data Loading and Preprocessing**:
   - Load AMD stock data from a CSV file.
   - Calculate technical indicators for scalping and short-term analysis.
   - Handle missing values using forward and backward filling.
   - Create sequences of past 40 minutes data to use as input features for the LSTM model.

2. **Technical Indicators Calculated**:
   - Simple Moving Averages (SMA)

3. **Target Calculation**:
   - Calculate the cumulative percentage change in price over the next 10 rows.

4. **Model Training**:
   - Split the data into training and testing sets.
   - Normalize the data using `StandardScaler`.
   - Define and train the LSTM model using early stopping to prevent overfitting.

5. **Model Evaluation**:
   - Evaluate the model performance using Mean Squared Error (MSE) on the test set.
   - Predict the future price changes and compare them to the actual values.
   - Calculate the accuracy of predicting the correct sign (positive or negative) of price changes.

6. **Visualization**:
   - Plot the training and validation loss over epochs.
   - Display the results of actual vs. predicted values.

## Results

- The model successfully predicts the sign of future price changes with a certain accuracy.
- A comparison of the model's predictions with actual values is provided.
- Number of correct predictions: 9438
-Total number of instances: 11899
-Accuracy: 79.32% that means  it will predic  80 percent of times  will prize  incres or decreas correctley 
## Why Not Use Traditional Models?

Traditional models that use open, high, close, and volume data to predict the target price often claim high accuracy (e.g., 99%). However, these models can be misleading and may not be reliable in real-world trading scenarios. Specifically:

- **High Accuracy but Low Practical Value**: Models claiming 99% accuracy may not perform well in predicting the direction of price changes. In practice, they might even result in losses.
- **Failure to Predict Sign**: These models often fail to predict the sign (positive or negative) of future price changes, which is crucial for making profitable trading decisions.
- **Need for Sequential Data Analysis**: LSTM models are designed to analyze sequences of data, making them suitable for capturing temporal dependencies in stock prices.

By using LSTM, we leverage the past 40 minutes of trading data to predict the sign of price changes over the next 10 minutes, which is more aligned with short-term trading strategies.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yug201/amd-stock-price-prediction-lstm.git
   cd amd-stock-price-prediction-lstm
