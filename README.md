# Leishmaniasis Prediction — PFE

An end-to-end data science project developed as part of my Master's final-year project, focused on predicting the monthly number of **leishmaniasis cases in Ouarzazate, Morocco** using historical epidemiological data and climatic variables.

## Project Overview

Leishmaniasis is influenced by several environmental and climatic factors. The objective of this project is to build a predictive system capable of forecasting future case counts by combining historical epidemiological observations with climate data.

The project covers the complete data science workflow:

- Data collection and preparation
- Climate data retrieval through the **NASA POWER API**
- Exploratory data analysis
- Time-series feature engineering
- Multivariate forecasting using **LSTM**
- Model evaluation
- Prediction explainability using **SHAP**
- Visualization and decision-support reporting with **Power BI**

## Objectives

The main objectives of the project are to:

- Analyze historical leishmaniasis trends in Ouarzazate.
- Study the relationship between climatic conditions and disease occurrence.
- Build a model capable of forecasting monthly leishmaniasis cases.
- Incorporate temporal dependencies using lagged epidemiological and climate variables.
- Explain the contribution of the different variables to model predictions.
- Present the results through an interactive analytical dashboard.

## Data

The project combines two main categories of data:

### Epidemiological Data

Historical monthly records of leishmaniasis cases in the Ouarzazate region.

### Climate Data

Climate variables are collected automatically using the **NASA POWER API**, including variables such as:

- Temperature
- Humidity
- Precipitation
- Solar-related variables
- Other relevant environmental indicators

The climate observations are aligned with the epidemiological time series before modeling.

## Data Processing

The preprocessing pipeline includes:

- Missing-value handling
- Data cleaning
- Date alignment
- Time-series aggregation
- Feature scaling
- Lag feature generation
- Climate and epidemiological data integration
- Transformation into sequences suitable for LSTM training

Special attention is given to maintaining the temporal order of observations in order to avoid data leakage.

## Feature Engineering

To capture delayed effects between climatic conditions and disease occurrence, the model uses several lagged variables.

Examples include:

- Previous leishmaniasis case counts
- Previous-month temperature values
- Previous precipitation levels
- Lagged humidity indicators
- Seasonal and temporal features

These features allow the model to learn relationships that may occur with a delay rather than only using current-month conditions.

## Model

The forecasting model is based on a **multivariate Long Short-Term Memory neural network (LSTM)** implemented using TensorFlow.

LSTMs are particularly suitable for this problem because they can learn long-term and short-term dependencies in sequential data.

The model receives sequences containing epidemiological and climatic information and produces a prediction of the number of cases for a future period.

## Model Explainability

To improve interpretability, the project integrates **SHAP**.

SHAP values are used to analyze how individual variables influence the model's predictions.

This makes it possible to identify factors that contribute the most to predicted increases or decreases in leishmaniasis cases.

The explainability layer is important because the project is intended not only to generate predictions, but also to provide useful information for decision-making.

## Visualization

The project includes a **Power BI dashboard** designed to present:

- Historical leishmaniasis cases
- Predicted case counts
- Forecast trends
- Climate indicators
- Epidemiological KPIs
- Important predictive factors
- SHAP-based model explanations

The dashboard provides a more accessible interface for interpreting the results of the predictive model.

## Technologies Used

- **Python**
- **TensorFlow / Keras**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **SHAP**
- **NASA POWER API**
- **Power BI**
- **Jupyter Notebook**

## Project Workflow

```text
Epidemiological Data
        |
        v
Data Cleaning
        |
        +-------------------+
        |                   |
        |             NASA POWER API
        |                   |
        |             Climate Data
        |                   |
        +---------+---------+
                  |
                  v
          Data Integration
                  |
                  v
         Feature Engineering
                  |
                  v
        Time-Series Sequences
                  |
                  v
             LSTM Model
                  |
                  v
            Predictions
                  |
          +-------+-------+
          |               |
          v               v
     SHAP Analysis     Power BI
          |               |
          +-------+-------+
                  |
                  v
          Decision Support
