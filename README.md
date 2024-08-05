# Final Project - Credit Card Customer Segmentation

## Project Overview

This project involves the implementation, training, and evaluation of a data model using Python. The data is cleaned, normalized, and standardized before modeling. The model uses data retrieved from either SQL or Spark and aims to achieve at least 75% classification accuracy or an R-squared value of 0.80.

## Requirements Met For Completion

### Data Model Implementation

- **Python Script**: The script is responsible for initializing, training, and evaluating the model.
- **Data Preparation**: The data is cleaned, normalized, and standardized prior to modeling to ensure accuracy and reliability.
- **Data Source**: The model utilizes data retrieved from SQL or Spark.
- **Model Performance**: The model demonstrates meaningful predictive power, achieving at least 75% classification accuracy or an R-squared value of 0.80.

### Data Model Optimization

- **Optimization Process**: The iterative changes made to the model and their impact on performance are documented within the Python script.
- **Performance Display**: The overall model performance is printed or displayed at the end of the script.

## About The Dataset

The dataset called `BankChurners.csv` contains comprehensive customer information from a consumer credit card portfolio, aimed at predicting customer attrition. It includes:

1. **Demographics:** Age, gender, marital status, income category.
2. **Credit Card Relationship:** Card type, number of months on book, inactive periods.
3. **Spending Behavior:** Total revolving balance, credit limit, average open-to-buy rate.
4. **Analytical Metrics:** Total amount of change from Q4 to Q1, average utilization ratio, Naive Bayes classifier attrition flag, combined card category with contact count over 12 months, dependent count, education level, months inactive.

The dataset provides up-to-date information across multiple variables, aiding in the management of the portfolio and individual customer service by predicting long-term account stability or potential departure.

It can be found on Kaggle: [Predicting Credit Card Customer Segmentation](https://www.kaggle.com/datasets/thedevastator/predicting-credit-card-customer-attrition-with-m)

## Step By Step Explanation

The jupyter notebook used called `Kmeans.ipynb` outlines the data analysis project using Principal Component Analysis (PCA) and clustering. Below, you will find a step by step explanation of what the data model does.

**1. Importing Libraries:** The model begins by importing necessary libraries such as: `pandas`, `StandardScaler`, `KMeans`, `matplotlib.pyplot`, `PCA`, `sqlalchemy`, `hvplot.pandas`, `URL` and `calinski_harabasz_score`.

**2. Connecting to the Database:** The code connects to a PostgreSQL database using SQLAlchemy and fetches data from a table called `bank_customers`.

**3. Cleaning the Data:** Rows with unknown values in the `income_category` column are dropped.

**4. Descriptive Statistics:** The code describes the dataset and its categorical columns.

**5. Filtering Relevant Columns:** The project filters out only the relevant columns for the marketing campaign.

**6. Data Preprocessing:**

- The gender column is mapped to numerical values (0 for female, 1 for male).
- The income vategory is also mapped to numerical values.
- The data is standarized using `StandardScaler`.

**7. Principal Component Analysis (PCA):** PCA is applied to reduce the dimensionality of the dataset.

**8. Clustering:** KMeans clustering is performed to segment the data into 4 clusters.

**9. Visualization:** The clusters are visualized using a scatter plot.

**10. Evaluating Clusters:** The quality of the clusters is evaluated using the Calinski-Harabasz score.

**11. Cluster Analysis:** The data is grouped by clusters and summarized for each cluster.

In summary, this project fetches customer data from a database, cleans and preprocesses it, reduces its dimensionality using PCA, segments it into clusters using KMeans, and evaluates the quality of these clusters. Finally, it analyzes and describes each cluster in detail.

## Tableau Dashboard

In order to better present the customer insights we found about demographic variables and credit information, we built a dashboard using Tableau which you can see published here: [Presenting_Dataset](https://public.tableau.com/app/profile/kevin.dorado/viz/Presenting_Dataset/Presentingthedata?publish=yes)

## Results