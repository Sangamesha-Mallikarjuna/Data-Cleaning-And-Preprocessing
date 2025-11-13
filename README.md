# Data-Cleaning-And-Preprocessing
A data-cleaning project using Python (Pandas) — includes handling missing values, fixing data types, removing duplicates, and standardizing text values."
README – Data Cleaning Using Python (Pandas)
📖 Project Overview

This project demonstrates a complete data-cleaning workflow using Python and Pandas.
The dataset used contains air-pollution information from multiple cities and countries.
Our goal is to clean, standardize, and prepare the data for further analysis or visualization.

  Steps Performed
1️⃣ Importing Required Libraries

We imported core Python libraries needed for data manipulation:

pandas

numpy

import pandas as pd
import numpy as np

2️⃣ Importing the Dataset

The dataset was loaded into a Pandas DataFrame using:

df = pd.read_csv("global_air_pollution_dataset.csv")

3️⃣ Identifying Missing & Null Values

We checked for missing values using:

df.isnull().sum()


This helped determine which columns had incomplete data (e.g., missing Country names).

4️⃣ Replacing / Handling Missing Values

We replaced missing or invalid entries (e.g., "Unknown", empty strings) with NaN:

df = df.replace("", np.nan)
df = df.replace("Unknown", np.nan)


We also used:

df.fillna(value, inplace=True)  # (Optional based on requirement)

5️⃣ Finding and Handling Duplicate Rows

To identify duplicate records:

df.duplicated().sum()
df[df.duplicated()]


To remove duplicates:

df.drop_duplicates(inplace=True)

6️⃣ Standardizing Text Values

We cleaned text columns to maintain consistency:

✔ Converting specific columns to uppercase
df[["Country", "City"]] = df[["Country", "City"]].apply(lambda x: x.str.upper())

✔ Converting all column names to uppercase
df.columns = df.columns.str.upper()


This ensures uniform formatting across the dataset.

  Summary of What Was Cleaned
Task	Status
Data imported	 Done
Missing values identified	 Done
Missing values replaced	 Done
Duplicate rows checked & removed	 Done
Text values standardized	 Done
Column names normalized	 Done
