📱 Smartphone Dataset Cleaning & Recommendation System (ADS Assignment 2)

This Jupyter Notebook presents a complete workflow for data cleaning, preprocessing, and building a basic product recommendation tool using a smartphone dataset (smartphones.csv).
It demonstrates how raw, messy data can be transformed into a clean, usable format for further analysis or modeling.

🚀 Features & Workflow
1. Importing Required Libraries

Uses Pandas for data manipulation and exploration.

Employs NumPy and Matplotlib/Seaborn (optional) for additional analysis and visualization.

2. Loading the Dataset

Loads raw data from smartphones.csv.

Displays the dataset shape and preview (first few records).

3. Exploring the Dataset

Prints dataset information (column names, datatypes, and missing values).

Generates descriptive statistics to understand numerical features.

Displays the top 10 rows for manual inspection.

4. Handling Missing Values

Price → Removes symbols like ₹ and commas, converts to float, fills missing entries with median.

Rating → Fills missing values with mean.

Camera → Missing values filled with mode (most frequent value).

Expandable Storage (card) → Missing replaced with "Not Specified".

Operating System (os) → Missing replaced with "Unknown".

5. Removing Duplicates

Detects and drops duplicate rows to maintain unique product entries.

6. Data Type Correction

Cleans text fields and extracts numeric values for analysis:

Column	Example (Before)	Example (After)
RAM	"8 GB"	8
Battery	"5000 mAh"	5000
Display	"6.5 inches"	6.5

Converts date fields (if available) to proper datetime format.

7. Exporting Cleaned Data

Saves the processed dataset as smartphones_cleaned.csv for later use or visualization.

8. Product Recommendation Function

A simple text-based recommendation feature:

def recommend_products(keyword, df, column="model"):
    results = df[df[column].str.contains(keyword, case=False, na=False)]
    return results


🔍 Example:

recommend_products("iPhone", df)

🧾 Example Output

Search: "Samsung"

model	price	rating	ram_gb	battery_mah	display_inches	os
Samsung Galaxy S21	69999.0	4.3	8.0	4000.0	6.2	Android
Samsung Galaxy A52	25999.0	4.1	6.0	4500.0	6.5	Android
🧩 Files Included
File	Description
smartphones.csv	Raw input dataset
smartphones_cleaned.csv	Cleaned and processed dataset
smartphone.ipynb	Jupyter Notebook containing all code and explanations


Output

The cleaned dataset will be automatically saved as smartphones_cleaned.csv.

Test Recommendations

Use the recommend_products() function to find phones by name or keyword.

🧠 Learning Objectives

Practice real-world data cleaning techniques.

Handle missing values, duplicates, and inconsistent formats.

Learn to extract numeric information from text-based columns.

Build a simple search-based recommendation function.

