# Data_Cleaning_and_EDA_using_SQL
# 🚀 Layoff Data Cleaning and Analysis

## 📌 Overview
This project focuses on cleaning and analyzing layoff data using SQL. The dataset contains information about company layoffs, including total employees laid off, industry, location, date, and funding details. The goal is to remove inconsistencies, standardize data, handle missing values, and perform exploratory data analysis to uncover trends.

## 📂 Datasets
The project uses a dataset named `layoffs`, which is processed in a staging table `layoffs_staging2` to ensure data integrity before analysis.

## 🛠 Data Cleaning Process
The `data_cleaning.sql` script performs the following steps:

1. **Create Staging Tables** 📊  
   - Copies data into `layoffs_staging` to prevent modifications to the original table.
   
2. **Remove Duplicates** 🗑  
   - Uses `ROW_NUMBER()` to identify duplicate records and removes them.

3. **Standardizing Data** ✨  
   - Trims whitespace from company names.
   - Unifies industry names (e.g., renaming variations of "Crypto" to a single term).
   - Cleans up country names by removing unnecessary characters.
   - Converts date values to the correct `DATE` format.

4. **Handling NULL and Blank Values** 📝  
   - Fills missing industry values by matching existing company records.
   - Removes records where both `total_laid_off` and `percentage_laid_off` are NULL.

5. **Remove Unnecessary Columns** ⚡  
   - Drops the `row_num` column after removing duplicates.

## 📊 Exploratory Data Analysis (EDA)
The `exploratory_data_analysis.sql` script explores trends in layoffs, focusing on the following insights:

1. **General Statistics**
   - 📈 Maximum layoffs and layoff percentages.
   - 🕰 Earliest and latest recorded layoff events.

2. **Company-Wise Analysis**
   - 🏢 Identifies companies with the highest number of layoffs.
   - 🔍 Analyzes layoffs for companies where 100% of employees were laid off.

3. **Industry and Country Trends**
   - 🌍 Identifies industries and countries with the highest layoffs.

4. **Yearly and Monthly Layoff Trends**
   - 📆 Aggregates layoffs by year.
   - 📊 Uses a rolling sum to track cumulative layoffs over time.

5. **Top 5 Companies with Highest Layoffs Per Year**
   - 🏆 Uses `DENSE_RANK()` to identify leading companies in layoffs for each year.

## 🛠 How to Use
1. 📥 Import the dataset into MySQL.
2. 🔧 Run `data_cleaning.sql` to preprocess the data.
3. 📊 Run `exploratory_data_analysis.sql` to generate insights.

## 🛠 Tools Used
- **SQL (MySQL)** for data manipulation and analysis.
- **CTEs, Window Functions, and Aggregations** for efficient querying.



