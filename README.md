# Used Car Price Prediction Using Machine Learning

## Project Overview

This project focuses on analysing used-car data and developing a machine learning model to predict vehicle selling prices.

The project follows an end-to-end data science workflow, beginning with data exploration and cleaning, followed by exploratory data analysis, feature selection, data preprocessing, machine learning model development, model comparison and evaluation.

The final selected model was deployed using Streamlit to allow users to enter vehicle information and obtain a predicted selling price.

An additional interactive Power BI dashboard was also developed to explore used-car pricing patterns and vehicle characteristics.

## Project Objectives

The main objectives of the project were to:

- Understand and clean the used-car dataset.
- Explore patterns and relationships within the data.
- Identify important variables associated with selling prices.
- Prepare the data for machine learning.
- Develop and compare multiple regression models.
- Select the best-performing model based on evaluation metrics.
- Deploy the selected model using Streamlit.
- Develop an additional Power BI dashboard for interactive data exploration.

- ## Dataset

The dataset contains information about used cars and their selling prices.

- Number of records: 15,411
- Original number of columns: 14
- Target variable: `selling_price`

The dataset contains numerical and categorical variables describing vehicle characteristics, usage, seller information and pricing.

### Main Variables

| Variable | Description |
|---|---|
| `car_name` | Name of the vehicle |
| `brand` | Vehicle manufacturer |
| `model` | Vehicle model |
| `vehicle_age` | Age of the vehicle |
| `km_driven` | Kilometres driven |
| `seller_type` | Type of seller |
| `fuel_type` | Type of fuel |
| `transmission_type` | Transmission type |
| `mileage` | Vehicle mileage |
| `engine` | Engine capacity |
| `max_power` | Maximum engine power |
| `seats` | Number of seats |
| `selling_price` | Selling price of the vehicle |

## Data Cleaning and Preprocessing

The dataset was inspected to understand its structure, data types and statistical characteristics.

An unnecessary identifier column, `Unnamed: 0`, was removed during the cleaning process.

The data was then prepared for machine learning by separating the predictor variables from the target variable and converting categorical variables into numerical representations using one-hot encoding.

After preprocessing, the feature matrix contained 281 features.

The dataset was divided into training and testing sets using an 80/20 split:

- Training records: 12,328
- Testing records: 3,083

## Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the characteristics of the used-car market and investigate relationships between vehicle attributes and selling price.

The analysis examined:

- Vehicle age
- Kilometres driven
- Mileage
- Engine size
- Maximum power
- Fuel type
- Transmission type
- Seller type
- Selling price

The EDA helped identify patterns in the dataset and supported the selection of variables for the machine learning stage.

## Feature Selection

Several vehicle characteristics were considered as potential predictors of selling price.

The final model analysis showed that `max_power` was the most influential feature, followed by `vehicle_age`, `mileage` and `engine`.

Feature importance analysis was used to understand which variables contributed most to the model's predictions.

## Machine Learning Models

Several regression models were developed and evaluated to determine which model provided the strongest predictive performance.

The models included:

- Linear Regression
- Random Forest Regression
- Tuned Random Forest Regression
- Gradient Boosting Regression
- Tuned Gradient Boosting Regression

The models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

## Model Comparison

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 178,516.10 | 385,236.04 | 0.8029 |
| Random Forest | 99,476.00 | 216,498.65 | 0.9377 |
| Tuned Random Forest | 101,722.42 | 232,928.68 | 0.9279 |
| Gradient Boosting | 129,971.99 | 261,873.54 | 0.9089 |
| Tuned Gradient Boosting | 116,421.85 | 232,946.17 | 0.9279 |

The original Random Forest model achieved the strongest overall test performance, with the highest R² score and the lowest MAE and RMSE among the evaluated models.

Therefore, the original Random Forest model was selected as the final model.

## Model Interpretation

Feature importance analysis showed that `max_power` was the most influential predictor of vehicle selling price.

Other important variables included:

- `vehicle_age`
- `mileage`
- `engine`

The analysis indicates that vehicle performance characteristics and vehicle age played an important role in predicting selling price.

## Streamlit Deployment

The selected Random Forest model was saved and integrated into a Streamlit application.

The application allows users to enter vehicle characteristics and receive a predicted selling price.

The application was tested locally using Streamlit and successfully produced a predicted vehicle price.

## Additional Power BI Dashboard

An additional interactive Power BI dashboard was developed to provide a visual exploration of the used-car dataset.

The dashboard includes:

- Total Listings
- Average Selling Price
- Highest Price
- Lowest Price
- Average Price by Vehicle Age
- Cars by Fuel Type
- Price Range Distribution
- Top 5 Brands by Average Price
- Transmission Type

Interactive filters were also included for:

- Brand
- Fuel Type
- Transmission
- Seller Type

A reset-filters function was added to improve dashboard usability.

The Power BI dashboard is an additional visualisation component of the project and was developed to complement the machine learning analysis.

## Results

The machine learning analysis demonstrated that the Random Forest regression model provided strong predictive performance on the used-car dataset.

The final model achieved:

- MAE: 99,476.00
- RMSE: 216,498.65
- R²: 0.9377

The model was subsequently deployed through Streamlit, allowing predictions to be generated from new vehicle information.

## Limitations

Some limitations of the project include:

- The dataset may not represent the entire used-car market.
- Vehicle prices can be affected by factors that are not included in the dataset.
- Some vehicle categories have relatively few observations.
- Extreme selling-price values may affect model performance.
- Predictions should be interpreted as estimates rather than guaranteed market prices.

## Conclusion

This project demonstrates an end-to-end machine learning workflow for used-car price prediction.

The process included data cleaning, exploratory data analysis, feature selection, preprocessing, model development, model comparison and evaluation.

Among the models tested, Random Forest Regression achieved the strongest predictive performance and was selected as the final model.

The model was deployed using Streamlit, while an additional Power BI dashboard was developed to provide interactive exploration of the used-car data.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Streamlit
- Power BI
- GitHub

## Project Structure

```text
used-car-price-prediction/
│
├── README.md
├── data/
│   └── car_price_dataset.csv
│
├── notebooks/
│   └── Used_Car_Price_Prediction.ipynb
│
├── models/
│   └── car_price_prediction_model.pkl
│
├── src/
│   └── app.py
│
├── dashboard/
│   └── Used_Car_Price_Analysis.pbix
│
├── images/
│   ├── dashboard.png
│   ├── streamlit_app.png
│   └── model_comparison.png
│
├── requirements.txt
└── .gitignore
