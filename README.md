# nyc-data-analysis
This project is a data-driven exploration of New York City, leveraging NYC Open Data to uncover insights across three key urban facets: public safety, public health, and environmental infrastructure.


---

# NYC Urban Life Analysis: Arrests, Restaurant Inspections, and Street Trees

## **Project Overview**

This project analyzes three NYC Open Data datasets  **NYPD Arrests**, **Restaurant Inspections**, and **Street Tree Census 2015**  to uncover insights about urban life, public services, and environmental quality across boroughs. Using SQL and Python, the project performs data cleaning, aggregation, and visualization to reveal crime trends, restaurant compliance, and tree health patterns.

---

## **Project Objectives**

* **Crime Analysis:** Identify arrest trends and hotspots across NYC boroughs.
* **Restaurant Compliance:** Evaluate inspection results to determine high-risk areas and common violations.
* **Environmental Assessment:** Analyze tree distribution and health to understand urban environmental quality.

---

## **Datasets Used**

1. **NYPD_Arrests.csv** – Arrests data including offense type, location, and demographics.
2. **Restaurant_Inspection.csv** – Inspection scores, grades, violations, and restaurant locations.
3. **Street_Tree_Census_2015.csv** – Tree species, health, and location information.

> All datasets are available from [NYC Open Data](https://opendata.cityofnewyork.us/).

---

## **Installation & Requirements**

Python 3.x environment with the following libraries:

```bash
pip install pandas sqlite3 matplotlib seaborn
```

---

## **How to Run**

1. Place the CSV files in your project directory.
2. Open the Jupyter Notebook or Python script.
3. Load the datasets into an in-memory SQLite database:

```python
import pandas as pd
import os
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
from IPython.display import display, HTML
%matplotlib inline
import sqlite3

# Create SQLite in-memory database
connection = sqlite3.connect(':memory:')

# Load datasets
pd.read_csv("NYPD_Arrests.csv").to_sql('NYPD_Arrests', connection, if_exists='replace', index=False)
pd.read_csv("Restaurant_Inspection.csv").to_sql('Restaurant_Inspection', connection, if_exists='replace', index=False)
pd.read_csv("Street_Tree_Census_2015.csv").to_sql('Street_Tree_Census_2015', connection, if_exists='replace', index=False)
```

4. Run SQL queries to extract insights.
5. Visualize results using **matplotlib** or **seaborn**.

---

## **Project Structure**

```
nyc-data-analysis/
├── .gitignore
├── data_cleaned/
│   ├── NYPD_Arrests_Clean.csv
│   ├── Restaurant_Inspection_Clean.csv
│   └── Street_Tree_Census_2015_Clean.csv
├── data_raw/
├── docs/
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_sql_queries.ipynb
│   └── 03_visualization.ipynb
├── reports/
├── scripts/
├── sql/
│   ├── create_tables.sql
│   ├── query#1.sql
│   ├── query#2.sql
│   ├── query#3.sql
│   ├── query#4.sql
│   ├── query#5.sql
│   └── query#6.sql
├── Visualization/
│   ├── README.md
│   ├── NYPD_Arrests/
│   │   ├── OUTLIER_DETECTION_USING_IQR.ipynb (or .py)
│   │   ├── Arrests_by_borough.png (or .html)
│   │   └── Borough_Distribution_Bar_Plot.png (or .html)
│   ├── Restaurant_Inspection/
│   │   ├── Count_grades_per_cuisine.png
│   │   ├── Number_of_restaurants_by_borough_and_grade.png
│   │   ├── Q1_results.png
│   │   ├── Q2_results.png
│   │   └── Top_10_Cuisines_by_Inspection_Count.png
│   ├── Street_Tree_Census/
│   │   ├── Tree_health_by_borough.png
│   │   ├── Tree_Health_Distribution_Stacked_Bar_Chart.png
│   │   └── Tree_Species_Diversity_Top_10_Pie_Chart.png
│   └── Top_10_Offense_Descriptions.png
└── README.md
```

---

## **Challenges & Solutions**

* **Data Quality Issues:** Missing or inconsistent values handled by cleaning, standardization, and imputation.
* **Large Dataset Size:** Queries optimized with CTEs and in-memory SQLite to improve performance.
* **Dataset Integration:** Standardized borough and location fields before joining datasets.

---

## **Future Steps**

* Integrate additional NYC datasets (crime trends, transportation, demographics) for deeper insights.
* Build automated pipelines and dashboards for real-time monitoring.
* Apply predictive modeling to forecast crime hotspots, restaurant violations, or areas of poor tree health.

---

## **Author**

Your Name – Muhammad Ehtesham


