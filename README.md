# Zero-and-One-Inflated Poisson Regression using EM Algorithm for Predicting Initial Values

This repository implements a **Zero-and-One-Inflated Poisson Regression** model using the **Expectation-Maximization (EM) Algorithm**. 
The goal of the project is to predict initial values in count data with an overrepresentation of zeros, common in areas such as insurance, healthcare, economics, and social sciences.

### Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [How It Works](#how-it-works)
- [Installation](#installation)

## Overview

Count data often exhibits an overabundance of zeros, which can make traditional Poisson regression unsuitable. **Zero-and-One-Inflated Poisson Regression** is an extension of the Poisson model that handles data with excess zeros and ones by combining two models:
1. A **Poisson model** for the non-zero counts.
2. A **logistic regression model** for the excess zeros.
3. A **logistic regression model** for the excess ones.

This implementation employs the **Expectation-Maximization (EM) algorithm** to estimate the model parameters. The EM algorithm is well-suited for situations where data contains latent (unobserved) variables, which in this case, are the binary indicators for zero or non-zero counts.

## Key Features

- **Zero-and-One-Inflated Poisson Regression**: A statistical model designed to handle count data with excess zeros.
- **Expectation-Maximization Algorithm**: Iterative method to estimate the model parameters for the ZIP regression.
- **Model Prediction**: Predict initial values or count outcomes for new observations.
- **Scalability**: Designed to work on datasets with large counts and excess zero values.

## How It Works

The ZOIP model consists of three main components:
1. **Zero-and-One-Inflated Component**: This models the probability of an observation being zero and ones using a logistic regression model.
2. **Poisson Component**: This models the actual counts (for non-zero values) using a Poisson distribution.

The **EM algorithm** is used to iteratively estimate the parameters of both components. It works by alternating between two steps:
1. **Expectation step (E-step)**: The algorithm estimates the likelihood of each observation belonging to either the zero-inflated component or the Poisson component.
2. **Maximization step (M-step)**: The parameters of both the logistic and Poisson models are updated based on the estimated likelihoods from the E-step.

This approach is particularly effective for handling datasets where zero counts are not simply a result of random variation but are systematically overrepresented.

## Installation

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/martizap-alt/zoipregression.git
    ```

2. Navigate into the project directory:

    ```bash
    cd zoipregression
    ```

3. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```
