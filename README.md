# iNAV Calculation and Metrics Evaluation for ETF Pricing

This project implements the calculation of **intraday Net Asset Value (iNAV)** for an Australian-listed ETF (NDQ), using the **Nasdaq 100 Futures** as a proxy. The project also calculates key metrics like **Mean Absolute Error (MAE)**, **Mean Squared Error (MSE)**, and **R²** to evaluate the performance of iNAV prediction against actual NDQ prices.

## Project Overview

### Purpose

The goal of this project is to compute the **iNAV** of the NDQ ETF by:
1. Using the **Nasdaq 100 Futures** (NQ) as a proxy for the underlying asset price.
2. Calculating the **percentage change** in the Futures value throughout the trading day.
3. Updating the **iNAV** based on the Futures price and the **AUD/USD exchange rate** at the same timestamp.
4. Calculating key error metrics (**MAE**, **MSE**, and **R²**) to compare the predicted iNAV values against the actual closing prices of NDQ.

### Key Metrics to Assess Pricing Model
- **MAE (Mean Absolute Error)**: Measures the average absolute difference between the actual and predicted iNAV values.
- **MSE (Mean Squared Error)**: Measures the average squared differences between the actual and predicted iNAV values. Penalizes larger errors more heavily.
- **R² (R-squared)**: Measures the proportion of variance in the actual NDQ prices that can be explained by the iNAV.

## Data Sources

1. **Nasdaq 100 Futures (NQ)**: The futures prices of the Nasdaq 100 index, used as a proxy for the underlying index.
2. **AUD/USD Exchange Rate**: The exchange rate between the Australian Dollar (AUD) and the US Dollar (USD).
3. **NDQ (Australian-listed ETF)**: The Australian-listed ETF that tracks the performance of the Nasdaq 100 index.
4. **QQQ (US-listed ETF)**: The US-listed ETF that tracks the performance of the Nasdaq 100 index.

The data is provided in **CSV** format and includes intraday data at 5-second intervals for the Futures, Exchange Rate, and NDQ ETF.

## Steps for Calculation

1. **Filter and Align Data**: Filter the datasets to align the timestamps, ensuring that the data for **Futures** and **AUD/USD** is synchronized at each 5-second interval.
2. **EOD NAV Calculation**: Use the **EOD NAV** (closing price) for the **QQQ ETF** as a reference to calculate the initial NAV for NDQ in **USD**.
3. **iNAV Calculation**: Update the **iNAV** based on the change in **Nasdaq 100 Futures** and the **AUD/USD exchange rate**.
4. **Metrics Evaluation**: Calculate the **MAE**, **MSE**, and **R²** metrics to evaluate the accuracy of the iNAV predictions against actual NDQ prices.
