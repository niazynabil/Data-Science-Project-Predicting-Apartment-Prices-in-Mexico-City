# Data-Science-Project-Predicting-Apartment-Prices-in-Mexico-City
This project aims to predict apartment prices in Mexico City using data science techniques. The dataset used is from Kaggle and contains information about apartments in Mexico City, including their location, size, and price. The goal of this project is to create a model that accurately predicts the price of an apartment based on its features.

Data Wrangling:
To prepare the data for modeling, a function named "wrangle" was created. This function takes a file path as an argument and returns a DataFrame. The first step in data wrangling was to subset the data in the CSV file to include only relevant columns such as location, size, and price. Then outliers were removed from surface_covered_in_m2 column using quantile method in pandas. Next, separate "lat" and "lon" columns were created because their data type is object so each should be in their own column where the data type is float. 

Feature Engineering:
Mexico City is divided into 15 neighborhoods. A new feature called "neighborhood" was created from the "place_with_parent_names" column by extracting the name of the neighborhood from it. To further improve our model's performance, some columns containing low or high cardinality were dropped along with 50% null values and leakage features like 'price_usd_per_m2' which would not be available at prediction time.

Model Building:
After cleaning up our dataset we used glob to create a list of files then split Data into feature matrix and target vector. We then built our model using Ridge() model which is commonly used for regression problems like this one since it helps prevent overfitting by adding a penalty term to the loss function.

Data Preprocessing:
Before feeding our data into our model we needed to preprocess it using SimpleImputer strategy which replaces missing values with either mean or median value depending on what strategy we choose. We also used OneHotEncode transformer to convert categorical variables into numerical ones.

Model Evaluation:
To evaluate our model's performance we used mean absolute error (MAE) . The MAE measures the average absolute difference between predicted and actual prices.

Prediction Function:
Finally, a function named "make_prediction" was created that takes 4 arguments (area, lat, lon, neighborhood). This function uses our trained model to predict the price of an apartment based on its features. It returns a predicted price in USD.

Conclusion:
In conclusion, this project demonstrates how data science techniques can be used to predict apartment prices in Mexico City. By cleaning and preprocessing our dataset, feature engineering, and building a Ridge regression model we were able to achieve good results in predicting apartment prices. Our prediction function can be used by anyone looking to buy or sell an apartment in Mexico City.
