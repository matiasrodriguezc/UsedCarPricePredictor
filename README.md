# Used Car Price Prediction Model

This repository contains a complete machine learning project in a **Python script** that predicts the price of used cars based on their features. The project demonstrates a full data science workflow, from raw data preprocessing to model training, evaluation, and interpretation using Python and popular data science libraries.

It serves as a practical, real-world example of applying a multiple linear regression model.

-----

## 🎯 Project Goal

The primary objective is to build a model that accurately predicts the `Price` of a used car. This involves a comprehensive data cleaning and feature engineering process to satisfy the assumptions of a linear regression model.

-----

## 📊 Dataset

The model is trained on the `used_cars_info.csv` dataset.

**Key features include:**

  * **`Brand`**: The brand of the car (e.g., BMW, Audi).
  * **`Price`**: The target variable we want to predict.
  * **`Body`**: The body type of the car (e.g., sedan, van).
  * **`Mileage`**: The distance the car has traveled.
  * **`EngineV`**: The engine volume.
  * **`Engine Type`**: The type of fuel the engine uses.
  * **`Registration`**: Whether the car has a registration.
  * **`Year`**: The year the car was manufactured.

-----

## 🛠️ Methodology & Key Steps

The script follows a structured approach to building the regression model:

1.  **Data Loading and Initial Exploration**:

      * The raw data is loaded using `pandas`.
      * Initial descriptive statistics are explored.

2.  **Data Cleaning (Preprocessing)**:

      * **Handling Missing Values**: Rows with missing values are dropped.
      * **Dealing with Outliers**: Outliers are removed from `Price`, `Mileage`, `EngineV`, and `Year`.
      * **Correcting Erroneous Data**: Invalid entries in `EngineV` are filtered out.

3.  **Checking OLS Assumptions**:

      * **Linearity**: The `Price` variable is log-transformed (`np.log`) to create a more linear relationship.
      * **Multicollinearity**: The Variance Inflation Factor (VIF) from `statsmodels` is used, and the `Year` feature is dropped.

4.  **Feature Engineering**:

      * **Dummy Variables**: Categorical features are converted into numerical dummy variables using `pd.get_dummies()`.

5.  **Model Training**:

      * **Data Scaling**: Input features are scaled using `StandardScaler` from `scikit-learn`.
      * **Train-Test Split**: The data is split into training (80%) and testing (20%) sets.
      * **Regression**: A `LinearRegression` model from `scikit-learn` is trained on the preprocessed data.

6.  **Model Evaluation**:

      * **Performance Analysis**: The script evaluates the model's performance on the test set by comparing its predictions against the actual target values.
      * **Interpretation**: The model's coefficients (weights) and intercept are examined to understand the relationships between the features and the car's log price.

-----

## ⚙️ Requirements

This project requires Python 3 and the following libraries:

  * `pandas`
  * `numpy`
  * `matplotlib`
  * `seaborn`
  * `statsmodels`
  * `scikit-learn`

-----

## 🚀 Installation & How to Run

1.  **Clone the repository**:

    ```bash
    git clone https://github.com/matiasrodriguezc/UsedCarPricePredictor.git
    ```

2.  **Navigate to the project directory**:

    ```bash
    cd UsedCarPricePredictor
    ```

3.  **Install the required libraries**:

    ```bash
    pip install pandas numpy matplotlib seaborn statsmodels scikit-learn
    ```

4.  **Run the Python Script**:

      * Save your code as a Python file (e.g., `car_price_prediction.py`).
      * Make sure the dataset `used_cars_info.csv` is in the same directory.
      * Execute the script from your terminal:

    <!-- end list -->

    ```bash
    python car_price_prediction.py
    ```

    The script will run from top to bottom, and any plots generated with `plt.show()` will be displayed. The final predictions and model analysis will be printed to the console.
