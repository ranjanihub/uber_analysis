# 🚖 Uber Trip Data Analysis Dashboard

An end-to-end data analytics project using **Python**, **SQL**, and **Power BI** to uncover insights from Uber trip records. This project demonstrates data cleaning, preprocessing, and interactive dashboard creation to explore travel behavior, trip categories, revenue, and location hotspots.

---

## 📌 Objective

To analyze Uber trip data and extract actionable insights such as:

* Most frequent locations
* Business vs Personal trip trends
* Total distance and max miles
* Ride purposes and travel time distribution
* Monthly revenue trends and peaks

---

## 🗃️ Dataset

* **Source**: [Kaggle – Uber Trips Dataset](https://www.kaggle.com/datasets)
* **File Used**: `UberDataset.csv`
* **Key Columns**:

  * `START_DATE`, `END_DATE`
  * `CATEGORY`, `PURPOSE`
  * `START_LOCATION`, `STOP_LOCATION`
  * `MILES`

---

## 💠 Tools & Technologies

| Tool           | Purpose                                    |
| -------------- | ------------------------------------------ |
| **Python**     | Data cleaning, datetime formatting         |
| **Pandas**     | Preprocessing, feature engineering         |
| **PostgreSQL** | SQL queries and aggregation                |
| **Power BI**   | Dashboard visualization and DAX metrics    |
| **DAX**        | Measures for distance, revenue, categories |

---

## 🔄 Data Cleaning (Python)

* Converted `START_DATE` and `END_DATE` to uniform datetime format
* Filled missing or invalid dates with a default fallback value (`01-01-2000 00:00`)
* Created additional features:

  * `RIDE_START_TIME`
  * `RIDE_END_TIME`
  * `Distance in KM` (converted from miles)

```python
df['START_DATE'] = pd.to_datetime(df['START_DATE'], format='%m/%d/%Y %H:%M', errors='coerce')
df['START_DATE'] = df['START_DATE'].fillna(pd.to_datetime('01-01-2000 00:00', format='%d-%m-%Y %H:%M'))
df['START_DATE'] = df['START_DATE'].dt.strftime('%d-%m-%Y %H:%M')
```

---

## 📊 Power BI Dashboard Features

| Visual                  | Insight Provided                            |
| ----------------------- | ------------------------------------------- |
| **Miles vs KM**         | Total and converted distance                |
| **Category Filter**     | Business vs Personal usage trends           |
| **Purpose Breakdown**   | Ride purpose insights (e.g. Commute, Visit) |
| **Monthly Filter**      | Dynamic analysis by time period             |
| **Time Duration Graph** | Ride frequency over months                  |
| **Revenue Graph**       | Count and amount of revenue per month       |
| **Location Hotspots**   | Most frequent pickup/drop-off areas         |

### 📷 Dashboard Screenshots

#### 1. Category and Distance Overview

![Dashboard 1](../images/92a402bf-d074-462c-8387-44df85bb3cbb.jpg)

#### 2. Location Hotspots and Purpose Filter

![Dashboard 2](../images/93e12b58-8fce-43b1-84ef-3d31030bbd49.jpg)

#### 3. Time Duration and Revenue Analysis

![Dashboard 3](../images/1d2ba0c8-4f82-47a6-a0f8-fa0fb3f95a7f.jpg)

#### 4. Purpose Donut Chart and Max Miles

![Dashboard 4](../images/e7e78b4d-f60e-4dba-9958-c5aece4f360a.jpg)

---

## 📈 Key Insights

* 🚗 **Highest trip counts**: June, July, and December
* 📍 **Top Locations**: CBD, Downtown, Medical Center
* 💼 **Business Trips** dominate over Personal in mileage
* 💰 **Peak Revenue** in December with a total of **256M**
* ⏱️ **Lowest travel duration** in May, highest in December

---

## 📁 Folder Structure

```
Uber-Trip-Analysis/
│
├── data/
│   └── UberDataset.csv
├── scripts/
│   └── clean_data.py
├── dashboard/
│   └── UberDashboard.pbix
├── images/
│   └── dashboard_screenshots.jpg
├── README.md
└── requirements.txt
```

---

## ✅ How to Run

1. Clone the repo

   ```bash
   git clone https://github.com/your-username/Uber-Trip-Analysis.git
   ```
2. Install Python dependencies

   ```bash
   pip install -r requirements.txt
   ```
3. Run the script to clean data

   ```bash
   python scripts/clean_data.py
   ```
4. Open `UberDashboard.pbix` in Power BI Desktop

---

## 📬 Contact

For questions or collaboration:
**Ranjani**
📧 [ranjaniranjani5694@gmail.com](mailto:ranjaniranjani5694@gmail.com)
🔗 [LinkedIn](https://linkedin.com/in/ranjani8)

---

## ⭐ Acknowledgments

* [Kaggle Dataset](https://www.kaggle.com/datasets)
* Uber for real-world trip data inspiration
