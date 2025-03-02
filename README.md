# week-1-AQI-Prediction
# Data Analysis on Air Quality Index (AQI)

This project involves data analysis on the Air Quality Index (AQI) using Python libraries such as `numpy`, `pandas`, `matplotlib`, and `seaborn`.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Data Loading](#data-loading)
  - [Data Cleaning](#data-cleaning)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project aims to analyze the Air Quality Index (AQI) data to gain insights into the air quality across different regions. We will perform data cleaning, exploratory data analysis (EDA), and visualize the data to understand the underlying patterns.

## Getting Started

### Prerequisites

Make sure you have the following libraries installed:

- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`

You can install these libraries using `pip`:

```sh
pip install numpy pandas matplotlib seaborn
```
Data Cleaning
Clean the data by checking for duplicates and handling missing values:
# Display the number of rows and columns
print("\nShape of the dataframe:")
print(df.shape)

# Get an overview of the dataframe
print("\nDataframe info:")
df.info()

# Check for duplicate rows
print("\nNumber of duplicate rows:")
print(df.duplicated().sum())

# Check for missing values
print("\nMissing values in each column:")
print(df.isnull().sum())

# Drop rows where 'AQI' has missing values
df.dropna(subset=['AQI'], inplace=True)

# Recheck for missing values
print("\nMissing values after dropping rows with missing 'AQI':")
print(df.isnull().sum().sort_values(ascending=False))

# Display the new shape of the dataframe
print("\nNew shape of the dataframe:")
print(df.shape)

# Summary statistics of the dataframe
print("\nSummary statistics of the dataframe:")
print(df.describe().T)  # Transpose for better readability

# Percentage of null values in each column
null_values_percentage = (df.isnull().sum() / df.isnull().count() * 100).sort_values(ascending=False)
print("\nPercentage of null values in each column:")
print(null_values_percentage)

#Exploratory Data Analysis (EDA)
Visualize the distribution of 'AQI' and relationships with other variables:
# Visualize distribution of AQI
sns.histplot(df['AQI'], kde=True)
plt.title('Distribution of AQI')
plt.show()

# Visualize AQI by City
sns.boxplot(x='City', y='AQI', data=df)
plt.title('AQI by City')
plt.show()

# Correlation Analysis
plt.figure(figsize=(10, 8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Matrix')
plt.show()

#Contributing
Contributions are welcome! Please open an issue or submit a pull request.

#License
This project is licensed under the MIT License. See the LICENSE file for details.


Feel free to customize this README file to better suit your project's specifics. If you need any more adjustments, let me know!
