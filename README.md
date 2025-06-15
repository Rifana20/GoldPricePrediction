# Gold Price Prediction

This project aims to predict the price of Gold (GLD) using historical market data, including the S&P 500 index (SPX), US Oil Fund (USO), Silver (SLV), and the Euro/US Dollar exchange rate (EUR/USD). A Random Forest Regressor model is trained and evaluated for this prediction task.

## Dataset

The dataset used is `gld_price_data.csv`, which contains historical daily prices for:
- **Date**: Date of the observation
- **SPX**: S&P 500 Index
- **GLD**: Gold Price (our target variable)
- **USO**: United States Oil Fund
- **SLV**: Silver Price
- **EUR/USD**: Euro to US Dollar Exchange Rate

## Project Structure

The code performs the following steps:

1.  **Data Loading and Exploration**:
    * Loads the `gld_price_data.csv` file into a Pandas DataFrame.
    * Displays the first and last 5 rows of the dataset.
    * Checks the number of rows and columns (`gold_data.shape`).
    * Provides basic information about the data types and non-null counts (`gold_data.info()`).
    * Verifies for any missing values (`gold_data.isnull().sum()`).
    * Generates descriptive statistics of the numerical features (`gold_data.describe()`).

2.  **Data Analysis and Visualization**:
    * Calculates the correlation matrix of the features (excluding 'Date').
    * Visualizes the correlation matrix using a heatmap to understand relationships between variables.
    * Prints the correlation values specifically with 'GLD' to identify key influencing factors.
    * Visualizes the distribution of 'GLD' prices using a `distplot`.

3.  **Model Training**:
    * Separates the features (X) from the target variable (Y - GLD price).
    * Splits the data into training and testing sets (80% training, 20% testing) using `train_test_split`.
    * Initializes and trains a `RandomForestRegressor` model with 100 estimators.

4.  **Model Evaluation**:
    * Makes predictions on the test set.
    * Calculates and prints the R-squared error to assess the model's performance.
    * Visualizes the actual GLD prices versus the predicted GLD prices using a line plot to visually inspect the model's accuracy.

## How to Run

This code is designed to be run in a Google Colab environment.

1.  **Open in Colab**: Click the "Open In Colab" badge at the top of the notebook.
2.  **Upload Data**: Upload the `gld_price_data.csv` file to your Colab environment (e.g., in the `/content/` directory as referenced in the code).
3.  **Run Cells**: Execute each code cell sequentially.

## Dependencies

The following Python libraries are required:

* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn`

These libraries can be installed using pip if you are running this outside of Colab:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
