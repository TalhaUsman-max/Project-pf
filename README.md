# ===============================
# Data Analysis 
* Apple Sales 2024 Data
# ===============================

# -------------------------------
# Importing Libraries
# -------------------------------
import pandas as pd

import matplotlib.pyplot as plt

# -------------------------------
# 1. Data Loading and Initial Exploration
# -------------------------------

# Reading the CSV file into a DataFrame
df = pd.read_csv('project.csv')

# Displaying the first 5 rows of the dataset
print("First 5 rows of the dataset:")
print(df.head(5))

# Displaying the last few rows to check the end of the dataset
print("\nLast few rows of the dataset:")
print(df.tail())

# -------------------------------
# 2. Dataset Information
# -------------------------------

# Displaying general information about the dataset
print("\nDataset Information (Data Types & Memory Usage):")
df.info()

# Displaying a random sample of 5 rows from the dataset for a quick check
print("\nRandom Sample of 5 rows:")
print(df.sample(5))

# -------------------------------
# 3. Descriptive Statistics
# -------------------------------

# Descriptive statistics for numerical columns
print("\nDescriptive Statistics (Numerical Columns):")
print(df.describe())

# Descriptive statistics for all columns (including categorical)
print("\nDescriptive Statistics (All Columns):")
print(df.describe(include="all"))

# -------------------------------
# 4. Handling Duplicates
# -------------------------------

# Dropping duplicates from the dataset if any
print("\nData after removing duplicates:")
df_dropped = df.drop_duplicates()
print(df_dropped)

# -------------------------------
# 5. Data Selection
# -------------------------------

# Accessing specific columns for analysis
# Example: Accessing a column named "iPad Sales"
print("\nAccessing 'iPad Sales (in million units)':")
print(df["iPad Sales (in million units)"])

# Accessing multiple columns at once
print("\nAccessing multiple columns: 'State', 'Region', 'iPhone Sales (in million units)':")
print(df[["State", "Region", "iPhone Sales (in million units)"]])

# Accessing a specific column (Wearables)
print("\nAccessing 'Wearables (in million units)':")
print(df[["Wearables (in million units)"]])

# -------------------------------
# 6. Summary Statistics
# -------------------------------

# Calculating the mean of 'Wearables (in million units)'
print("\nMean of 'Wearables (in million units)':")
print(df["Wearables (in million units)"].mean())

# Finding the mode of 'iPad Sales (in million units)'
print("\nMode of 'iPad Sales (in million units)':")
print(df["iPad Sales (in million units)"].mode())

# Finding the median of 'Mac Sales (in million units)'
print("\nMedian of 'Mac Sales (in million units)':")
print(df["Mac Sales (in million units)"].median())

# Summing up the values of 'Mac Sales' and 'Wearables'
print("\nSum of 'Mac Sales (in million units)' and 'Wearables (in million units)':")
print(df[["Mac Sales (in million units)", "Wearables (in million units)"]].sum())

# Counting the non-null values in each column
print("\nCount of non-null values in each column:")
print(df.count())

# -------------------------------
# 7. Data Visualization
# -------------------------------

# Plotting a line chart for 'iPad Sales'
print("\nPlotting 'iPad Sales (in million units)' value counts (Line Plot):")
df['iPad Sales (in million units)'].value_counts().plot(kind="line")
plt.show()

# Plotting a bar chart for 'iPhone Sales'
print("\nPlotting 'iPhone Sales (in million units)' value counts (Bar Plot):")
df['iPhone Sales (in million units)'].value_counts().plot(kind="bar")
plt.show()

# Plotting a horizontal bar chart for 'iPhone Sales'
print("\nPlotting 'iPhone Sales (in million units)' value counts (Horizontal Bar Plot):")
df['iPhone Sales (in million units)'].value_counts().plot(kind="barh")
plt.show()

# Plotting a histogram for 'Mac Sales'
print("\nPlotting 'Mac Sales (in million units)' value counts (Histogram):")
df["Mac Sales (in million units)"].value_counts().plot(kind='hist')
plt.xlabel('Category')
plt.ylabel('Frequency')
plt.title("Histogram of Mac Sales")
plt.show()

# Plotting a box plot for 'iPad Sales'
print("\nPlotting 'iPad Sales (in million units)' value counts (Box Plot):")
df["iPad Sales (in million units)"].value_counts().plot(kind='box')
plt.show()

# Plotting an area chart for 'iPhone Sales'
print("\nPlotting 'iPhone Sales (in million units)' value counts (Area Plot):")
df['iPhone Sales (in million units)'].value_counts().plot(kind='area')
plt.show()

# Plotting a pie chart for 'iPhone Sales'
print("\nPlotting 'iPhone Sales (in million units)' value counts (Pie Chart):")
df['iPhone Sales (in million units)'].value_counts().plot(kind='pie')
plt.show()

# -------------------------------
# 8. Handling Missing Data
# -------------------------------

# Checking for missing values in the dataset
print("\nChecking for missing values in the dataset:")
print(df.isnull())

# Summing up missing values in each column
print("\nSumming up missing values in each column:")
print(df.isnull().sum())

# Checking for non-null values in the dataset
print("\nChecking for non-null values:")
print(df.notnull())

# Filling missing values in the 'Services Revenue (in billion $)' column with a value of 10
print("\nFilling missing values in 'Services Revenue (in billion $)':")
df["Services Revenue (in billion $)"].fillna(10, inplace=True)
print(df)

# -------------------------------
# 9. Dropping Missing Data
# -------------------------------

# Checking for missing values in the 'iPhone Sales' column
print("\nChecking for missing values in 'iPhone Sales (in million units)':")
print(df["iPhone Sales (in million units)"].isnull())

# Dropping rows with any missing values
print("\nDataset after dropping rows with missing values:")
df_cleaned = df.dropna()
print(df_cleaned)

# -------------------------------
# 10. Accessing Specific Rows
# -------------------------------

# Accessing specific rows by labels using .loc
print("\nAccessing specific rows using .loc:")
print(df.loc[[2, 5, 8, 18, 60]])

# Accessing specific rows by index positions using .iloc
print("\nAccessing specific rows using .iloc:")
print(df.iloc[[2, 23, 345, 478, 579, 789, 12]])
