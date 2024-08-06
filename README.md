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

And bank customers behaviors here: [Bank customer behaviors](https://public.tableau.com/app/profile/angeles.villagrana/viz/Bank_customers_17229080548870/Resume)

## Results

#### Cluster 0
- **Age**:
  - Customers in the highest income category (`$120K+`) have ages ranging from 26 to 62, with an average age of about 48.
  - Customers in the lowest income category (`Less than $40K`) have an age of 60.
- **Credit Limit**:
  - Higher income categories generally have higher average credit limits. For example, customers in the `$120K+` category have an average credit limit of around $23,298, while those in the `$40K - $60K` category have an average of about $14,493.
- **Utilization Ratio**:
  - Utilization ratios are relatively low across all categories, with a mean value below 0.1 in each group.
- **Total Revolving Balance**:
  - There is a wide range in total revolving balances, with the highest being over $2,500 for some income categories and $0 for others.

#### Cluster 1
- **Age**:
  - Customers in the `$40K - $60K` income category have ages ranging from 26 to 65, with an average age of about 47 for females and 57 for males.
  - Customers in the `Less than $40K` income category have ages ranging from 26 to 67, with an average age of about 46 for females and 52 for males.

- **Credit Limit**:
  - Credit limits vary significantly within the `$40K - $60K` category, with females having a maximum limit of approximately $15,698 and males about $3,506.
  - In the `Less than $40K` category, credit limits for females reach up to $15,987, while for males, it is about $7,098.

- **Utilization Ratio**:
  - Utilization ratios are higher in this cluster compared to the first, with some customers having utilization ratios as high as 0.999.
  - Mean utilization ratios are above 0.5 for females and above 0.6 for males in the `Less than $40K` category.

- **Total Revolving Balance**:
  - The total revolving balance is generally lower compared to the first cluster, with mean values around $1,690 for females and $1,675 for males in the `$40K - $60K` category.
  - For the `Less than $40K` category, mean revolving balances are approximately $1,664 for females and $1,712 for males.

#### Cluster 2
- **Age**:
  - Customers in the `$40K - $60K` income category have ages ranging from 26 to 65, with an average age of about 47.
  - Customers in the `Less than $40K` income category have ages ranging from 26 to 67, with an average age of about 45.

- **Credit Limit**:
  - Credit limits vary significantly within the `$40K - $60K` category, with a maximum limit of approximately $23,981.
  - In the `Less than $40K` category, credit limits reach up to $15,987.

- **Utilization Ratio**:
  - Utilization ratios are generally low in this cluster, with a maximum ratio of 0.468.
  - Mean utilization ratios are below 0.1 for most categories, indicating low credit usage.

- **Total Revolving Balance**:
  - The total revolving balance is generally low in this cluster, with mean values around $360 for females in the `$40K - $60K` category.
  - For the `Less than $40K` category, mean revolving balances are approximately $290.

#### Cluster 3
- **Age**:
  - Customers in the `$120K+` income category have ages ranging from 27 to 61, with an average age of about 46.
  - Customers in the `Less than $40K` income category have ages ranging from 38 to 55, with an average age of about 38.

- **Credit Limit**:
  - Credit limits vary significantly within the `$120K+` category, with a maximum limit of approximately $23,959.
  - In the `Less than $40K` category, credit limits reach up to $15,210.

- **Utilization Ratio**:
  - Utilization ratios are generally higher in this cluster, with a maximum ratio of 0.994.
  - Mean utilization ratios range from about 0.12 to 0.39 across different income categories.

- **Total Revolving Balance**:
  - The total revolving balance is generally higher in this cluster, with mean values around $1,867 for males in the `$120K+` category.
  - For the `Less than $40K` category, mean revolving balances are approximately $1,919.

### Conclusion
- After reviewing the clusters, the decision is made to launch a `5% cashback to cluster number 0` since it is the cluster with the lowest average credit utilization.
- `Cluster number 2 will be given 4%` since its credit utilization is very low with a maximum of 48%.
- For `Cluster number 3, 3.5%` since it maintains an average utilization of the credit line of 12 to 39%.
- While `Cluster number 1 will only be given 1%` since it has a greater use of the credit line, which overusing it could imply non-payment.