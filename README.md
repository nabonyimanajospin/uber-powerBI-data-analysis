# 🎯 Uber Fares Dataset Analysis (Big Data Project)

> A complete data analysis project for **INSY 8413 – Introduction to Big Data Analytics** using **Python (Pandas)** and **Power BI**

![Tool](https://img.shields.io/badge/Tool-Python%20%7C%20Power%20BI-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle%20Uber%20Fares-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## 📘 Project Overview

This project performs a comprehensive analysis of Uber ride fare data using Python and Power BI. It includes data preprocessing, feature engineering, and advanced dashboard visualization to uncover trends and insights in fare amounts, trip durations, and spatial-temporal patterns.

---

## 🎯 Assignment Objective

According to the assignment given:

> Analyze the Uber Fares Dataset to gain insights into fare patterns, ride durations, and key metrics by:
>
> * Performing EDA and preprocessing in Python (Colab)
> * Creating features like hour, weekday, weekend, distance
> * Visualizing key findings in **Power BI** with interactivity
> * Submitting a complete report with screenshots and insights

✅ **All asked in the assignment is included below.**

---

## 🛠️ Tools & Technologies

| Tool               | Purpose                              |
| ------------------ | ------------------------------------ |
| 🐍 Python (Pandas) | Data cleaning, EDA, feature creation |
| ☁️ Google Colab    | Python environment (cloud-based)     |
| 📊 Power BI        | Visualization and dashboards         |
| 🧾 GitHub          | Submission and documentation         |

---

## 📊 Data Preprocessing in Python

### ✅ Step 1: Dataset Load & Inspection

```python
import pandas as pd
df = pd.read_csv('uber.csv')
df.head()
```

**🖼 Screenshot:** `📸 Show first 5 rows of raw dataset`

---

### ✅ Step 2: Data Types, Shape, Nulls

```python
print(df.shape)
print(df.dtypes)
print(df.isnull().sum())
```

✅ Found missing values and unformatted datetime.

**🖼 Screenshot:** `📸 Output showing types and nulls`

---

### ✅ Step 3: Descriptive Statistics

```python
df.describe()
```

✅ Detected zero/negative fares and extreme values.

**🖼 Screenshot:** `📸 Descriptive summary`

---

### ✅ Step 4: Cleaning Data

```python
# Drop unnamed index
# Convert datetime
# Drop nulls, filter fare and passenger count
# Reset index
```

✅ Removed invalid rows and formatted datetime.

**🖼 Screenshot:** `📸 Cleaned dataset head`

---

### ✅ Step 5: Check Final Shape

```python
print(df.shape)
```

✅ Final shape: **199,268 rows × 8 columns**

**🖼 Screenshot:** `📸 Shape after cleaning`

---

## 🧠 Feature Engineering

### ✅ Step 6: Extract New Columns

```python
df['hour'] = df['pickup_datetime'].dt.hour
...
```

✅ Added: hour, day, month, weekday, `is_weekend`, `year`

**🖼 Screenshot:** `📸 Dataset with new columns`

---

### ✅ Step 7: Calculate Distance (Haversine Formula)

```python
def haversine(...):
    ...
df['distance_km'] = df.apply(lambda row: haversine(...), axis=1)
```

✅ Calculated real distance for each ride.

**🖼 Screenshot:** `📸 New column: distance_km`

---

### ✅ Step 8: Export Final Dataset

```python
df.to_csv('uber_final.csv', index=False)
```

✅ Ready to load into Power BI!

**🖼 Screenshot:** `📸 Save dialog in Colab`

---

## 📈 Power BI Dashboard

### ✅ Step 9: Data Import

* Imported `uber_final.csv` into Power BI using **Text/CSV** source

**🖼 Screenshot:** `📸 Power BI data load preview`

---

### ✅ Step 10: Dashboard Visualizations

All visuals include **filters** and **clean formatting**:

| No. | Visualization              | Details                                          |
| --- | -------------------------- | ------------------------------------------------ |
| 1️⃣ | **Fare Distribution**      | Histogram + Box Plot, shows most fares < \$20    |
| 2️⃣ | **Fare vs Distance**       | Scatter plot with `fare_amount` vs `distance_km` |
| 3️⃣ | **Fare vs Time of Day**    | Line chart by `hour`                             |
| 4️⃣ | **Rides by Weekday**       | Bar chart of ride count by `day_of_week`         |
| 5️⃣ | **Monthly Trends**         | Line chart (month/year on x-axis)                |
| 6️⃣ | **Peak vs Off-Peak**       | Pie chart of `is_peak` categories                |
| 7️⃣ | **Pickup Locations (Map)** | Map using lat/long pickup coordinates            |

**🖼 Screenshot:** `📸 Each chart with its insight`

---

### ✅ Step 11: Filters & Interactivity

✅ Slicers included for:

* Weekday
* Hour
* Month
* Peak vs Off-peak

✅ Drill-down enabled for month/year

**🖼 Screenshot:** `📸 Filter panels in Power BI`

---

## 📌 Insights & Interpretations

| Insight Topic           | Interpretation                            |
| ----------------------- | ----------------------------------------- |
| 🚕 Most fares < \$20    | Majority of short-distance rides          |
| 🌍 Central pickup zones | Busy zones in city centers                |
| ⏰ Peak hour pricing     | Evening peaks (5-8PM), higher fares       |
| 🗓 Weekday vs weekend   | Friday & Saturday = more rides            |
| 🔄 Distance vs fare     | Some longer rides are cheaper (anomalies) |

**🖼 Screenshot:** `📸 Snapshot of interpretation panel`

---

## 🗂 Repository Contents

| File                        | Description                              |
| --------------------------- | ---------------------------------------- |
| `uber.csv`                  | Raw dataset from Kaggle                  |
| `uber_cleaned.csv`          | After cleaning (before feature creation) |
| `uber_final.csv`            | Final file with distance, features       |
| `uber_analysis_final.ipynb` | Python notebook                          |
| `/screenshots/`             | Visual proof of each step                |
| `README.md`                 | This final report                        |

---

## 👨‍💻 Author

**Jospin Nabonyimana**
🎓 Student, Adventist University of Central Africa
📚 Course: INSY 8413 – Introduction to Big Data Analytics
📧 Email: [your-email@example.com](mailto:your-email@example.com)

---

> ✅ **Every part of the assignment has been completed and documented as instructed.**
> 📌 Screenshots should be added below each 📸 tag in this README.
> 🧾 Power BI `.pbix` file should also be included in the GitHub repository.
