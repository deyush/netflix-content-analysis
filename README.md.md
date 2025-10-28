\# 🎬 Netflix Content Analysis


\## 📌 Project Overview

This project explores Netflix's content catalog to uncover trends in genre popularity, country-wise distribution, release year patterns, and maturity ratings. The goal is to demonstrate data analytics skills through Python-based EDA and an interactive Power BI dashboard.


\## 📂 Dataset Information

\- **Source**: *\[Kaggle - Netflix Titles Dataset]*(https://www.kaggle.com/datasets/alluringxstalwart/netflix-data)

\- **Format**: CSV

\- **Key Columns**:

 - `title`, `type`, `release\_year`, `country`, `genre`, `rating`, `duration`, `description`


\## 🎯 Project Goals

\- Clean and preprocess Netflix content data

\- Perform exploratory data analysis (EDA) to identify trends

\- Build an interactive dashboard in Power BI

\- Generate insights and recommendations for content strategy


\## 🛠️ Tools \& Technologies

\- \*\*Python\*\*: Pandas, NumPy, Matplotlib, Seaborn

\- \*\*Power BI\*\*: Dashboard creation and interactivity

\- \*\*Jupyter Notebook\*\*: For EDA and data wrangling

\- \*\*GitHub\*\*: Version control and portfolio hosting


\## 📁 Folder Structure


**Netflix\_Content\_Analysis/** 

**│** 

**├── README.md** 

**├── data/** 

**│ ├── raw/** 

**│ └── processed/** 

**├── notebooks/** 

**│ ├── 01\_data\_cleaning.ipynb** 

**├── scripts/** 

**│ └── utils.py** 

**├── powerbi/** 

**│ ├── Netflix\_Dashboard.pbix** 

**│ └── screenshots/** 

**├── reports/** 

**│ └── Netflix\_Insights.pdf** 

**└── assets/** 


\## 🚀 Next Steps

1\. Load and clean the dataset in Python

2\. Perform EDA and visualize key trends

3\. Build a Power BI dashboard with filters and slicers

4\. Summarize insights and recommendations


**---**

🧼 Data Cleaning & Preprocessing (Python + PowerBI)

The raw Netflix dataset was cleaned and enriched using Python before being imported into Power BI:

- Renamed columns for clarity (e.g., m_title → title, m_runtime → runtime)
- Handled missing values by filling nulls in key fields like maturity, runtime, genre, audio, and subtitles
- Created new features:
	- genre_list, subtitle_list, cast_list: split multi-value fields into lists
	- runtime_value: extracted numeric runtime
	- runtime_type: identified runtime format (e.g., hours, minutes, seasons)

- Exploratory visuals included:

	- Maturity rating distribution
	- Top 10 genres
	- Content release trend over time

- Saved cleaned dataset to /data/processed/netflix_cleaned.csv for use in Power BI

Additional, I have done the following in Power Query and DAX:

- Removed unnecessary columns: description, synopsis, cast, director, genre_list, subtitle_list, cast_list were dropped to reduce noise.
- Handled missing values: Nulls were addressed in key columns like genre, audio_language, and duration.
- Extracted runtime: Parsed duration values like "1h 34m" into total minutes using regex and conditional logic.


Created new columns:

- RuntimeMinutes: Numeric runtime in minutes
- MaturityLabel: Based on "maturity" column, I have renamed the maturity levels
- ContentType: Categorized entries as "Movies" or "TV Shows" based on runtime format ("m" and "h" for movies, "Seasons" for "TV Shows")
- YearBucket: Grouped release years into intervals (e.g., 1990–1995, 1996–2000)
- audio_grouped: Ensured consistent formatting of language names (e.g., removed trailing spaces, corrected casing) and unified similar entries (e.g., "English" and "ENGLISH" → "English"); Aggregated low-frequency languages into a single "Other" category


📊 Power BI Dashboard Development

An interactive dashboard was built in Power BI to visualize key insights. The following measures, visuals, and features were implemented:

✅ Measures Created

1. TotalTitles: Total number of titles
2. MovieCount / TVShowCount: Count of titles by content type
3. MovieShare / TVShowShare: Percentage breakdown of Movies vs. TV Shows
4. AverageRuntime: Mean runtime in minutes
5. TotalRuntimeHours: Total runtime converted to hours
6. UniqueLanguages: Number of distinct audio languages
7. TopGenre: Most frequent genre

📈 Visuals Included

- KPI Panel: Displays total titles, content type breakdown, average runtime, total runtime, language diversity, and top genre
- Genre Popularity by Maturity Rating: Horizontal stacked bar chart
- Content Growth Over Time: Vertical line chart grouped by period of time
- Top Genres: Treemap showing genre volume
- Content Type by Maturity: Stacked column chart
- Audio Language Distribution: Donut chart
- Slicers: Added for maturity rating, year bucket, genre, and content type to enable dynamic filtering


📌 Final Insights & Conclusions

- Movies dominate Netflix's catalog, accounting for over 75% of titles.
- Drama is the most popular genre, followed by Comedy and Action.
- Content growth peaked around 2020, reflecting Netflix's global expansion.
- Average runtime is 78 minutes, indicating a focus on digestible content.
- Language diversity is strong, with 53 audio languages represented.
- Maturity ratings skew toward adult content, especially in Drama and Action.
- TV Shows tend to have higher maturity ratings than Movies.
