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
