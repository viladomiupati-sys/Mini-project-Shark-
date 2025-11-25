# 🦈 Mini-Project: Shark Attacks Analysis

## Overview

This project analyzes historical shark attack data to extract meaningful insights and support business decisions. The Dev Team focuses on **data cleaning and exploratory analysis**, while the Research Team defines a **business case** to use the data for practical purposes.

---

## Day 1

### 🖥 Dev Team

**Objective:** Initial data check-up and cleaning.

```bash
# Install dependencies if needed
pip install openpyxl
pip install xlrd
```

```python
import pandas as pd

# Load the dataset
shark_df = pd.read_excel("Shark.xls")
shark_df

# Check general information about the dataset
shark_df.info()

# List all column names
shark_df.columns

# Removing extra columns with mostly NaN data
useless_columns = [
    "pdf",
    "href formula",
    "href",
    "Case Number",
    "Case Number.1",
    "original order",
    "Unnamed: 21",
    "Unnamed: 22"
]

shark_df.drop(columns=useless_columns, inplace=True)

# Preview cleaned dataset
shark_df.head()
```

---

### 🔬 Research Team

**Business Case: Surf Shop & Water Sports Safety**

**Scenario:**  
You run a surf shop that offers **surf lessons, rentals, and safety training**. You want to **maximize revenue while ensuring customer safety**. Shark attack data can help you **decide where and when to operate safely**.

#### 1️⃣ Objective

- Use shark attack data to **optimize beach locations** for lessons and rentals.
- Schedule lessons during **safer months and times**.
- Provide **safety training** informed by historical attack patterns.

#### 2️⃣ Key Questions to Answer

1. Which **beaches** have the **fewest shark attacks** historically?
2. During which **months or seasons** do attacks occur most frequently?
3. Are certain **activities** (surfing, swimming) more likely to be involved in attacks?
4. Are there patterns by **time of day** or **water conditions**?

---

## Day 2

### 🖥 Dev Team

Objective: Clean and standardize the dataset to make analysis easier and reduce unnecessary variation in outputs.

Example: Standardizing the Sex column

The dataset may have inconsistent values like M, Male, male, F, Female, or missing values. To unify these entries, we define a new column new_sex and map all variations to male, female, or unknown:

shark_df["new_sex"] = [
"male" if str(x).lower().startswith("m")
else "female" if str(x).lower().startswith("f")
else "unknown"
for x in shark_df['Sex']
]

Explanation:

str(x).lower().startswith("m") → detects all variations of male.

str(x).lower().startswith("f") → detects all variations of female.

Anything else is labeled "unknown".

This reduces inconsistencies and makes later analysis simpler.

---

### 🔬 Research Team

After reviewing REGEX techniques, we will implement code to clean and standardize the following shark attack dataset for better analysis and insights.

**Goals:**

- Identify safe beaches for lessons and rentals.
- Understand when attacks happen.
- Categorize activities to assess risk.

#### 🌍 Locations

- City, State, and Country fields may have extra spaces, punctuation, or misspellings.
- **Suggestions:**
  - Standardize names.
  - Split combined fields into separate columns.
  - Pay attention to missing or inconsistent country names, important for comparing risk by region.

#### 🏄 Activities

- Activities are written inconsistently (e.g., “Surf,” “Surfing,” “Surf lesson”).
- **Suggestions:**
  - Group similar activities under standard categories:
    - Surfing
    - Swimming
    - Wading
    - Fishing
    - ...etc.
  - Look for keywords in activity descriptions to classify correctly.

#### 📅 Dates

- Dates may be in different formats or missing.
- **Suggestions:**

  - Convert all dates to a standard format for analysis.

  ***

  ***
