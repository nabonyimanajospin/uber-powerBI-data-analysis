Name and ID:
____________
**Nabonyimana Jospin**  ![Badge](https://img.shields.io/badge/(26511)-green)
____________

# 🎯 Uber Fares Dataset Analysis (Big Data Project)

## 🔗 Kaggle Notebook

📘 *Full notebook on Kaggle*  
[👉 Click here to open the Uber Analysis on Kaggle](https://www.kaggle.com/code/jospinnabonyimana/introduction-to-big-data-kaggle)

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

**🖼 Screenshot:** 
<img width="1920" height="982" alt="image" src="https://github.com/user-attachments/assets/90336f78-58a7-4eca-9366-250c92ca3e21" />
---

### ✅ Step 2: Data Types, Shape, Nulls

```python
print(df.shape)
print(df.dtypes)
print(df.isnull().sum())
```

✅ Found missing values and unformatted datetime.
* Total Rows: 200,000
* Detected 1 missing value each in `dropoff_latitude` and `dropoff_longitude`
* Noticed `pickup_datetime` was not in datetime format

**📸 Screenshot:**
<img width="1920" height="832" alt="image" src="https://github.com/user-attachments/assets/557cc93c-efeb-4113-882f-fc855c22c808" />

---

### ✅ Step 3: Descriptive Statistics

```python
df.describe()
```

✅ Detected zero/negative fares and extreme values.
* Found negative or zero fare values
* Passenger count outliers (0, very high values)

**📸 Screenshot:**
<img width="1920" height="787" alt="image" src="https://github.com/user-attachments/assets/67b36b74-d359-40b7-a0cc-1e3a974b184f" />

---

### ✅ Step 4: Clean and Prepare Data

```python
# Drop unnamed index column
# Convert pickup_datetime
# Drop nulls
# Filter invalid fare_amount and passenger_count

...
```

**Key Cleaning Actions:**

* Dropped `Unnamed: 0` (useless index)
* Converted `pickup_datetime` to proper datetime format
* Dropped 2 null rows
* Removed trips with fare ≤ 0 and passenger count < 1 or > 6

**📸 Screenshot:**
<img width="1853" height="835" alt="image" src="https://github.com/user-attachments/assets/82b1b051-b6ac-4e50-8941-d3c4e1f9b4ac" />
<img width="1920" height="814" alt="image" src="https://github.com/user-attachments/assets/cece6a2f-f61e-4d99-a1ba-b883760d7664" />

---

### ✅ Step 5: Check Final Dataset Shape

```python
print(df.shape)
```

**📈 Final Shape: 199,268 rows × 8 columns**
**📸 Screenshot:**
<img width="1920" height="205" alt="image" src="https://github.com/user-attachments/assets/cfc4c1af-9b71-4b81-a992-8022f0394f01" />

---

## 🧠 Feature Engineering

### ✅ Step 6: Create New Analytical Columns

```python
df['hour'] = df['pickup_datetime'].dt.hour
...
```

* Extracted hour, day, month, weekday
* Created `is_weekend` boolean feature

**📸 Screenshot:**
<img width="1782" height="824" alt="image" src="https://github.com/user-attachments/assets/56cf675e-3324-486c-ba46-97fdf9989c4a" />


---

## 💾 Export to CSV for Power BI

### ✅ Step 7: Save Enhanced Dataset

```python
df.to_csv('uber_cleaned.csv', index=False)
```

* Downloaded the final cleaned file
* Ready to import into Power BI for visual analysis

**📸 Screenshot:**
![WhatsApp Image 2025-07-23 at 15 33 05_90511512](https://github.com/user-attachments/assets/3b302be8-e5c0-4422-8d76-ad074c987cb8)

---

### ✅ Step 8: Export Final Dataset

```python
df.to_csv('uber_final.csv', index=False)
```

✅ Ready to load into Power BI!

**🖼 Screenshot:**
![WhatsApp Image 2025-07-25 at 05 22 52_b2ba36f9](https://github.com/user-attachments/assets/937ce61b-7f4d-49b6-b181-c85ee425b237)

---

## 📈 Power BI Dashboard

### ✅ Step 9: Data Import

* Imported `uber_final.csv` into Power BI using **Text/CSV** source

**🖼 Screenshot:📸** 
<img width="1920" height="977" alt="image" src="https://github.com/user-attachments/assets/c2396716-4c39-41fc-8352-2288d3a60ccb" />

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

*_👆To be seen in the uploaded PowerBI Assignment file👆_

---

### ✅ Step 11: Filters & Interactivity

✅ Slicers included for:

* Weekday
* Hour
* Month
* Peak vs Off-peak

✅ Drill-down enabled for month/year

**🖼 Screenshot:**
<img width="1872" height="941" alt="image" src="https://github.com/user-attachments/assets/be75ad12-0d50-4448-b258-c06971146fad" />
<img width="1899" height="993" alt="image" src="https://github.com/user-attachments/assets/31b44de7-47cc-401e-b234-d34677397e26" />


---

## 📌 Insights & Interpretations

| Insight Topic           | Interpretation                            |
| ----------------------- | ----------------------------------------- |
| 🚕 Most fares < \$20    | Majority of short-distance rides          |
| 🌍 Central pickup zones | Busy zones in city centers                |
| ⏰ Peak hour pricing     | Evening peaks (5-8PM), higher fares       |
| 🗓 Weekday vs weekend   | Friday & Saturday = more rides            |
| 🔄 Distance vs fare     | Some longer rides are cheaper (anomalies) |

---

## 🗂 Repository Contents

| File                        | Description                              |
| --------------------------- | ---------------------------------------- |
| `uber.csv`                  | Raw dataset from Kaggle                  |
| `uber_cleaned.csv`          | After cleaning (before feature creation) |
| Link shared at the top | Python notebook                          |
|PowerBI Assignment.pbix| For visualizations and data relationship diagram|
| `/screenshots/`             | Visual proof of each step                |
| `README.md`                 | This final report                        |

---
Got it! Here's a **shorter, cleaner version** of the **Applications** section — still professional and impactful, but more concise for your README:

---

## 🌍 Applications

This Uber Fares analysis has practical relevance beyond the classroom. It demonstrates how data can support:

* **Fare Optimization**: Identifying peak hours and adjusting prices dynamically
* **Operational Efficiency**: Understanding when and where rides occur most to allocate drivers
* **Geospatial Insight**: Mapping pickups to reveal high-demand zones
* **Trend Forecasting**: Analyzing time patterns for better planning and decision-making

> 🎓 This project bridges academic learning with real-world data analytics — building practical skills in Python, Power BI, and data storytelling.

---

## 👨‍💻 Author

**Jospin Nabonyimana**

🎓 Student, Adventist University of Central Africa

📚 Course: INSY 8413 – Introduction to Big Data Analytics
# Contact

📧 Email: [jospinnabonyimana@gmail.com](mailto:jospinnabonyimana@gmail.com)  

---

## 📅 License

© Jospin Nabonyimana, 2025

> This project is for academic purposes under AUCA. All rights reserved.

