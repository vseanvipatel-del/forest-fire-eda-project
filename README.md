# forest-fire-eda-project
# 🔥 Brazilian Amazon Forest Fires — Exploratory Data Analysis (EDA)

This repository contains a beginner-friendly, structured Exploratory Data Analysis (EDA) on the **Brazilian Amazon Forest Fires (1998–2017)** dataset. Using Python's core data science libraries (**Pandas** and **NumPy**), this project demonstrates foundational data-wrangling, cleaning, seasonality modeling, and feature engineering techniques on environmental data.

## 📌 Project Overview
The main goal of this analysis is to monitor, clean, and extract actionable insights from historical fire reports across various Brazilian states. The project serves as an introductory portfolio piece showcasing how to seamlessly combine Pandas dataframes with NumPy arrays to calculate statistics, filter anomalies, and track year-over-year trends.

---

## 📊 Dataset Structure
The analysis handles two relational files containing historical wildfire logs:
* **Primary Dataset Files:** `forest_fire.csv` & `forest_fire_2.csv`

The dataset records are distributed across **5 core features**:
* **`year`:** The calendar year of the reported fire.
* **`state`:** The specific Brazilian state.
* **`month`:** The month name (originally in Portuguese).
* **`number`:** Total number of forest fires officially reported.
* **`date`:** Specific tracking date entry.

---

## 🔍 Analytical Milestones & Workflow

The workflow is broken down into 10 structured notebook modules:

### 1. Data Ingestion & Schema Inspection
* Resolves file encoding constraints using `latin-1` to successfully load text arrays.
* Extracts basic shape coordinates, structural data types, and inspects top records.

### 2. Statistical Descriptive Analysis
* Leverages Pandas `.describe()` alongside manual NumPy array aggregations.
* Evaluates data spread metrics such as mean, median, standard deviation, and peak-to-peak range (`np.ptp`).

### 3. Data Integrity & Deduplication
* Quantifies missing data counts and maps missing percentages column-by-column.
* Identifies exact duplicate rows using `.duplicated()` and drops them to prevent statistical skewing.

### 4. Macro Trend & Year-over-Year (YoY) Analysis
* Groups fire frequency counts by year to identify peak and baseline wildfire seasons.
* Utilizes NumPy's `np.diff()` vector math function to compute exact year-over-year fluctuations.

### 5. Spatial Risk Classification
* Ranks Brazilian states based on historical fire volumes.
* Applies `np.percentile()` to mathematically isolate and classify high-risk zones sitting above the 75th percentile.

### 6. Seasonality & Month Mapping
* Standardizes Portuguese month strings into logical numeric sequences.
* Evaluates peak fire months against global dataset baselines to establish a calendar risk curve.

### 7. Conditional Filtering & Slicing
* Implements multi-conditional boolean criteria filtering (e.g., extracting extreme records with more than 500 fires in specific state parameters).

### 8. Reshaping & Pattern Correlation
* Re-pivots data matrices (`state` $\times$ `year`) to look for repeating chronological patterns.
* Employs `.corr()` and `np.corrcoef()` to look for structural alignment/similarities between different tracking years.

### 9. Feature Engineering
* Minimizes target variable data skewness by applying a logarithmic transformation via `np.log1p()`.
* Creates categorical severity classification tags (`Low`, `Medium`, `High`) via custom function `.apply()` mapping.
* Extracts calendar quarters from raw datetime fields.

### 10. File Consolidation & Set Audits
* Stacks both separate CSV sources vertically into a single tracking master frame via `pd.concat()`.
* Applies explicit string source tags to systematically evaluate statistical data behaviors between the two text logs.
* Runs Python set mathematics (`-`, `&`) to isolate calendar overlap discrepancies.

---

## 🛠️ Tech Stack & Requirements
Ensure your target execution machine features Python 3.9+ along with these baseline numerical computation packages:
* **Pandas**
* **NumPy**
* **Jupyter Notebook**

To download the dependencies directly, run:
```bash
pip install pandas numpy jupyter
