# 📱 Google Play Store Exploratory Data Analysis (EDA)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Computation-013243?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-4c72b0)

An end-to-end Exploratory Data Analysis (EDA) investigating market trends, user engagement, rating distributions, pricing models, and app size characteristics across 10,000+ Android applications on the Google Play Store.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Key Questions Addressed](#-key-questions-addressed)
- [Dataset Architecture](#-dataset-architecture)
- [Data Cleaning & Transformation](#-data-cleaning--transformation)
- [Exploratory Analysis & Core Findings](#-exploratory-analysis--core-findings)
- [Deep Dives & Advanced Insights](#-deep-dives--advanced-insights)
- [Visualizations Used](#-visualizations-used)
- [Project Structure](#-project-structure)
- [Installation & Getting Started](#-installation--getting-started)
- [Limitations](#-limitations)
- [Future Roadmap](#-future-roadmap)

---

## 📊 Project Overview

This project analyzes the Google Play Store dataset to uncover the underlying factors that correlate with app success, high user ratings, and mass adoption. By evaluating categorical distributions, update cadences, app sizes, and monetization strategies, the study generates actionable business and product intelligence for developers and stakeholders.

---

## 🎯 Key Questions Addressed

* What is the global average app rating, and how many apps hit the $\ge 4.0$ benchmark?
* How does app volume break down between free and monetization models?
* Does app file size or unit price constrain overall install volume?
* Is there a significant statistical correlation between download counts and user ratings?
* Which genres and categories generate the highest aggregate installs and strongest user satisfaction?
* What are the historical update velocity patterns across active applications?

---

## 📂 Dataset Architecture

The raw dataset contains **10,841 app records** across **13 features**:

| Column | Description |
| :--- | :--- |
| `App` | Application title |
| `Category` | Category grouping (e.g., GAME, FAMILY, TOOLS) |
| `Rating` | Average user rating ($1.0$ – $5.0$) |
| `Reviews` | Total count of user reviews submitted |
| `Size` | App footprint (MB, KB, or "Varies with device") |
| `Installs` | Install brackets (e.g., `1,000,000+`) |
| `Type` | Monetization mechanism (`Free` vs `Paid`) |
| `Price` | Listed purchase price in USD |
| `Content Rating` | Target audience demographic classification |
| `Genres` | Sub-category / genre tags |
| `Last Updated` | Date of the latest version release |
| `Current Ver` | Active version release string |
| `Android Ver` | Minimum supported Android OS requirement |

---

## 🧹 Data Cleaning & Transformation

Extensive preprocessing was performed in Pandas to standardize raw strings, convert mixed units, and correct anomalies:

1. **Rating Validation:** Dropped 1 corrupt record containing an invalid rating ($>5.0$) and dropped rows with missing ratings, reducing the working set to **9,366 high-fidelity records**.
2. **Review Normalization:** Cast the string-based `Reviews` column into 64-bit integer format.
3. **App Size Standardization:** Converted all mixed measurement units (`MB` and `KB`) to a uniform floating-point MB scale. Replaced `"Varies with device"` with the overall median app size.
4. **Installs Cleaning:** Stripped string symbols (`+` and `,`) and converted records to numeric integers.
5. **Price Parsing:** Removed currency indicators (`$`) and converted values to continuous floating-point numbers.
6. **Imputation:** Imputed missing values in categorical fields (`Type`, `Content Rating`) using their respective statistical mode.
7. **Datetime Conversion:** Parsed `Last Updated` into native Pandas `datetime64[ns]` timestamps.

---

## 🔍 Exploratory Analysis & Core Findings

* **Overall Rating Distribution:** The mean rating across all cleaned apps is **4.19 / 5.0**, indicating an overall positively skewed rating distribution. A total of **7,368 apps** achieve a rating of $4.0$ or higher.
* **Ecosystem Breadth:** Contains **33 unique categories**, heavily populated by Family, Games, and Tools.
* **App Size Characteristics:** Average app size is **21.39 MB** with a median of **14.0 MB**. Games lead category sizes at an average of **41.83 MB**, followed by Family apps at **28.95 MB**.
* **Monetization Breakdown:** Heavily dominated by the ad/in-app purchase model:
  * **Free Apps:** `93.1%` (Average reviews: `~551K`)
  * **Paid Apps:** `6.9%` (Average reviews: `~14K`)
* **Audience Target:** The `Everyone` content rating accounts for the vast majority of applications across both free and paid segments.
* **Top Adoption Sectors:** Top 5 categories driving aggregate download volume:
  1. `GAME`
  2. `COMMUNICATION`
  3. `PRODUCTIVITY`
  4. `SOCIAL`
  5. `TOOLS`

---

## 📈 Deep Dives & Advanced Insights

### Correlation Realities
* **Installs vs. Rating ($r = 0.05$):** Near-zero correlation indicates that reaching high install tiers is not predictive of superior app ratings.
* **App Size vs. Installs ($r = 0.04$):** Application payload size shows practically no inhibitory effect on user install volume.

### Pricing Impact
* No linear correlation exists between price and app rating. Apps priced above **$100** show lower customer satisfaction scores, while the **$50–$100** niche maintains high ratings, though supported by a smaller sample size.

### Update Patterns
* Update density accelerates sharply into **2018**, with **6,508 apps** recording their most recent update in that single year (concentrated in July–August).

### High-Volume Ratings
* Filtering for verified engagement ($\ge 1,000$ reviews) surfaces apps that sustain near-perfect scores ($4.9$ to $5.0$) independent of whether they have 10,000 or 10,000,000 installs.
* Across genres, **Events, Word, Puzzle, Art & Design, and Books & Reference** maintain the highest average user satisfaction scores.

---

## 📊 Visualizations Used

The EDA leverages statistical plotting techniques built via Matplotlib and Seaborn:
* **Univariate Distributions:** Histograms and KDE plots for app size, prices, and ratings.
* **Categorical Proportions:** Donut and pie charts for monetization ratios and content ratings.
* **Comparative Distributions:** Box plots and violin plots analyzing rating spread across content ratings and price buckets.
* **Multivariate Relationships:** Scatter plots and binned bar charts assessing installs against ratings and reviews.
* **Temporal Series:** Line charts tracking update velocity across calendar years.

---

## 📂 Project Structure

```text
Google-Play-Store-EDA/
│
├── google_play_store_eda.ipynb   # Complete step-by-step EDA and code execution
├── googleplaystore.csv            # Raw dataset
└── README.md                     # Project documentation and summary