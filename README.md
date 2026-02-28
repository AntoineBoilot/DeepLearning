# Neural Network for Next-Day Return Prediction

This repository contains a **class project** in quantitative finance and deep learning.

The goal of the project is to test whether a simple feedforward neural network can predict **next-day stock returns** using only past daily returns as inputs.

## Project overview

Predicting short-term financial returns is difficult because markets are noisy and daily returns have weak serial dependence.

In this project, we implemented a **neural network from scratch using NumPy** to forecast next-day returns from lagged returns, then compared its performance to a **linear regression benchmark**.

## Objective

The main objective is to assess whether a nonlinear model can extract predictive information from recent returns and outperform a standard linear model.

## Data

- Market data covers the period **2022 to 2025**
- Due to repeated Yahoo Finance rate limit issues, data was retrieved from **Stooq**
- Only **closing prices** were used
- Daily returns were computed from price changes
- Missing values were removed before training

## Features and target

The model uses the **five most recent daily returns** as input features:

- \(R_{t-5}\)
- \(R_{t-4}\)
- \(R_{t-3}\)
- \(R_{t-2}\)
- \(R_{t-1}\)

The target is:

- **Next-day return** \(R_t\)

The dataset was split as follows:

- **80% training set**
- **20% test set**

## Model architecture

The neural network is a simple feedforward network with:

- **Input layer:** 5 neurons
- **Hidden layer:** between 5 and 10 neurons
- **Activation function:** tanh
- **Output layer:** 1 neuron with linear output

The model was trained with:

- **Gradient descent**
- **Backpropagation**
- **Mean Squared Error (MSE)** loss

## Results

The main findings of the project are:

- Train and test MSE stabilize quickly
- Predicted returns are much smoother than actual returns
- The scatter plot of predicted vs real returns shows a weak relationship
- The neural network only slightly outperforms linear regression

### Performance comparison

- **Neural Network Test MSE:** 0.00007602
- **Linear Regression Test MSE:** 0.00007656

This suggests that the neural network does **not significantly outperform** the linear benchmark.

## Interpretation

The results are consistent with financial theory:

- Daily returns are highly noisy
- Autocorrelation in short-term returns is weak
- The signal-to-noise ratio is very low

As a result, both linear and nonlinear models mostly learn the unconditional mean rather than meaningful predictive dynamics.

## Limitations

This class project has several limitations:

- Only lagged returns are used as features
- No volatility indicators are included
- No macroeconomic variables are used
- The prediction horizon is very short

## Possible improvements

Future versions could be improved by adding:

- Technical indicators
- Volatility features
- Macroeconomic variables
- Longer prediction horizons
- More advanced architectures

## Files

This repository includes:

- `neural_network_finance.ipynb` — notebook containing the implementation and experiments
- `Deep_Learning_Boilot_Haddad_Report.pdf` — written class report with methodology and results

## Conclusion

This project shows how to build and evaluate a neural network for financial forecasting in a simple setting.

Even though neural networks are more flexible than linear models, this experiment confirms that **predicting next-day returns remains extremely difficult when only past returns are used**.

## Academic context

This repository was developed as part of a **class project** in finance / deep learning.
