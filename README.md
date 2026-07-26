# Netflix Data Cleaning and Analysis Project (SQL + Python)

## 📌 Project Overview
This project involves cleaning, analyzing, and querying the Netflix Movies and TV Shows dataset using **Python (Pandas)** for data cleaning and exploratory analysis, and **SQL Server** for structured querying and insights.

---

## 🛠️ Tools & Technologies Used
- **Python** (Pandas, Matplotlib)
- **Jupyter Notebook** (via VS Code)
- **SQL Server** (Microsoft SQL Server 2022, accessed via `sqlcmd` and `pyodbc`/`SQLAlchemy`)
- **Dataset Source:** Netflix Movies and TV Shows dataset (Kaggle)

---

## 📁 Project Structure
```
NetflixDataCleaningandAnalysisProject(SQL+Python)/
│
├── data/
│   ├── netflix_titles.csv              # Original raw dataset
│   └── netflix_titles_cleaned.csv      # Cleaned dataset
│
├── notebooks/
│   └── netflix_data_cleaning.ipynb     # Python cleaning + analysis notebook
│
├── sql/
│   └── netflix_queries.sql             # All SQL queries used for analysis
│
├── venv/                               # Python virtual environment
└── README.md                           # Project documentation (this file)
```

---

## 🧹 Data Cleaning Steps (Python)
1. Loaded the raw dataset (8,807 rows × 12 columns)
2. Handled missing values:
   - `director`, `cast`, `country` → filled with `"Unknown"`
   - `date_added`, `rating`, `duration` → rows with missing values dropped (very small %)
3. Checked for duplicate rows (none found)
4. Converted `date_added` column to proper datetime format
5. Split `duration` column into `duration_number` (numeric) and `duration_type` (Season/min)
6. Final cleaned dataset: **8,790 rows × 14 columns**, zero missing values

---

## 📊 Exploratory Data Analysis (Python)
Visualizations created using Matplotlib:
1. Movies vs TV Shows distribution
2. Year-wise content added trend (2008–2021)
3. Top 10 countries producing Netflix content
4. Top 10 genres on Netflix
5. Content rating distribution (TV-MA, TV-14, etc.)

---

## 🗄️ SQL Analysis (SQL Server)
Cleaned data was loaded into a SQL Server database (`NetflixDB`, table: `netflix`) and queried for the following insights:

1. **Content type count** — Movies vs TV Shows
2. **Year-wise content trend** — titles added per year
3. **Top 10 countries** — using `STRING_SPLIT` to handle comma-separated values
4. **Top 10 genres** — using `STRING_SPLIT` on `listed_in`
5. **Rating distribution** — count of titles per content rating
6. **Top 10 directors** — most frequent directors (excluding "Unknown")
7. **Top 10 longest movies** — by duration in minutes

All queries are documented in `sql/netflix_queries.sql`.

---

## 🔑 Key Insights
- Netflix's library is **~70% Movies and ~30% TV Shows** (6,126 vs 2,664 titles)
- Content additions **peaked in 2019** (2,016 titles), with rapid growth from 2015–2019
- The **United States** produces the most content (3,680+ titles), followed by **India**
- **International Movies** is the most common genre category, followed by **Dramas** and **Comedies**
- **TV-MA** (Mature Audience) is the most common content rating, indicating Netflix's library skews toward adult audiences

---

## ✅ Conclusion
This project demonstrates an end-to-end data workflow: cleaning messy real-world data in Python, performing exploratory analysis with visualizations, and translating that analysis into structured SQL queries against a relational database — showcasing both **Python data wrangling** and **SQL querying** skills.
