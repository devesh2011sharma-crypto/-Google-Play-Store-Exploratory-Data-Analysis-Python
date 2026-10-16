# -Google-Play-Store-Exploratory-Data-Analysis-Python

📊 Project Overview
This project performs an Exploratory Data Analysis (EDA) of Google Play Store applications using Python, Pandas, NumPy, Matplotlib, and Seaborn.

The analysis explores app characteristics, user engagement, ratings, installs, reviews, pricing, categories, genres, content ratings, app size, and update patterns.

The goal is to understand the factors and patterns associated with app popularity and user ratings and to extract meaningful insights from the Google Play Store dataset.

image
🎯 Project Objectives
The analysis focuses on answering questions such as:

What is the average rating of apps?
How many app categories are available?
What is the distribution of app sizes?
How many apps are free versus paid?
What is the most common content rating?
Which apps have the highest number of installs?
How many apps have a rating of 4.0 or above?
Do free or paid apps receive more reviews?
Which categories have the largest average app size?
How have app updates changed over time?
Is there a relationship between installs and ratings?
Does app size affect the number of installs?
How does price relate to app ratings?
Which genres have the highest-rated apps?
Which categories have the highest total installs?
📂 Dataset
The project uses a Google Play Store dataset containing 10,841 app records and 13 columns before cleaning.

Key Columns
Column	Description
App	Name of the application
Category	App category
Rating	User rating
Reviews	Number of reviews
Size	Application size
Installs	Number of installs
Type	Free or Paid
Price	Application price
Content Rating	Target audience/content rating
Genres	App genre
Last Updated	Date of the last update
Current Ver	Current application version
Android Ver	Required Android version
🧹 Data Cleaning & Preparation
Before performing the analysis, the dataset was cleaned and transformed using Pandas.

Cleaning Steps
1. Rating Validation
Identified ratings greater than 5.0.
Removed the invalid rating record.
Removed rows with missing ratings.
After cleaning, the dataset contained 9,366 records.

2. Reviews Conversion
The Reviews column was converted from object/string format into numeric format.

3. App Size Conversion
The Size column contained values in MB and KB.

The values were converted into a consistent MB-based numerical format.

Values such as "Varies with device" were treated as missing and replaced using the median app size.

4. Installs Conversion
The Installs column was cleaned by removing:

+
,
The resulting values were converted into numeric format.

5. Price Conversion
The $ symbol was removed from the Price column and the values were converted into numeric format.

6. Missing Values
Missing values in:

Type
Content Rating
were filled using the respective mode.

7. Date Conversion
The Last Updated column was converted into a Pandas datetime format.

🔍 Exploratory Data Analysis
1. Overall App Rating
The average rating across the cleaned dataset is:

⭐ 4.19 / 5

This indicates that the apps in the dataset generally have positive user ratings.

2. App Categories
The dataset contains:

33 unique app categories

This demonstrates a diverse Google Play Store ecosystem spanning areas such as games, communication, productivity, education, social applications, and more.

3. App Size Distribution
The average app size is approximately:

21.39 MB

The median app size is:

14.0 MB

Most applications are relatively small, although the distribution contains a significant range of application sizes.

4. Free vs Paid Apps
The Google Play Store dataset is heavily dominated by free applications.

App Type	Percentage
Free	93.1%
Paid	6.9%
This highlights the prevalence of the free-app business model in the dataset.

5. Content Rating
The most common content rating is:

Everyone

This indicates that applications targeted toward a general audience make up the largest portion of the dataset.

6. Highly Installed Apps
The analysis identifies the top installed applications.

Applications such as:

Instagram
Facebook
Google Photos
appear among the applications with extremely high install counts, reaching more than one billion installs.

7. Apps Rated 4.0+
The analysis found:

7,368 apps

with a rating of 4.0 or higher.

8. Free vs Paid Reviews
Free applications receive substantially more reviews on average than paid applications.

Approximate averages from the analysis:

Free apps: ~551K reviews
Paid apps: ~14K reviews
This suggests that free applications generally have much greater user engagement in terms of review volume.

9. Average App Size by Category
Some categories tend to contain larger applications.

The analysis identifies:

GAME: ~41.83 MB
FAMILY: ~28.95 MB
among the categories with relatively larger average app sizes.

10. App Updates
The dataset shows a significant increase in application updates toward 2018.

The analysis found:

6,508 apps were last updated in 2018.

The available data covers last-update dates from:

2010-05-21 to 2018-08-08

Since the dataset only contains the most recent update date, it cannot be used to calculate the actual frequency between individual app updates.

📈 Advanced Analysis
11. Installs vs Rating
The correlation between installs and ratings is:

0.05

This represents a very weak positive correlation.

Therefore, the number of installs alone is not a strong predictor of an app's rating.

12. Highest-Rated Categories
The analysis identifies categories such as:

EVENTS
EDUCATION
ART_AND_DESIGN
BOOKS_AND_REFERENCE
among categories with higher average ratings.

13. Price vs Rating
App prices were grouped into price ranges to examine their relationship with ratings.

The analysis does not show a strong linear relationship between price and average rating.

Very expensive applications above $100 tend to have slightly lower average ratings, while the $50–$100 range shows relatively high average ratings.

However, the number of applications in some expensive price ranges is comparatively small.

14. Rating Distribution by Content Rating
The analysis compares app ratings across different content-rating groups using box plots.

The Everyone and Everyone 10+ categories show relatively concentrated rating distributions around the 4.0–4.5 range.

15. Genres with More Than 1 Million Installs
The analysis identifies genres containing the largest number of apps with at least one million installs.

Top genres include:

Tools
Action
Photography
Entertainment
Communication
16. App Size vs Installs
The correlation between app size and installs is:

0.04

This represents another very weak positive correlation.

Therefore, app size does not appear to be a major driver of install volume in this dataset.

17. Most Reviewed Apps
Applications such as:

Facebook
WhatsApp Messenger
Instagram
are among the applications with the highest review counts.

This reflects their large user bases and high levels of user engagement.

18. Free vs Paid Content Ratings
The Everyone content rating is the most common for both free and paid applications.

The analysis also shows that paid applications have a slightly higher proportion of Mature 17+ applications compared with free applications.

19. Top Categories by Total Installs
The five categories with the highest total install counts are:

GAME
COMMUNICATION
PRODUCTIVITY
SOCIAL
TOOLS
These categories represent some of the strongest areas of user adoption within the dataset.

📊 Advanced Insights
Highly Rated Popular Apps
To avoid apps receiving extremely high ratings from only a few reviews, the analysis considers applications with at least 1,000 reviews.

Among these popular applications, the highest-rated apps achieve ratings between approximately 4.9 and 5.0.

The analysis shows that highly rated apps can exist across very different popularity levels, from tens of thousands of installs to millions of installs.

Update Trends
The number of apps being updated increased significantly toward 2018, with the analysis showing a peak around July and August 2018.

No strong seasonal pattern was identified based on month or day of the week.

Genre vs Rating
Higher average ratings were observed among genres such as:

Events
Word
Puzzle
Art & Design
Books & Reference
Genres with comparatively lower average ratings included:

Card
Travel & Local
Entertainment
Lifestyle
This suggests that user satisfaction varies across different app genres.

Install Volume vs Rating
The binned install analysis indicates that average ratings generally increase as install volume increases.

The highest average rating occurs in the 100M–1B install range, followed by a slight decrease for applications exceeding one billion installs.

📊 Visualizations
The project uses multiple visualization techniques, including:

Histograms
Pie charts
Bar charts
Box plots
Scatter plots
Line charts
Grouped bar charts
Binned analysis
Time-series analysis
These visualizations are used to identify relationships and patterns that may not be immediately visible from summary statistics.

🛠️ Tools & Technologies
Programming Language
Python
Libraries
Pandas
NumPy
Matplotlib
Seaborn
Environment
Google Colab / Jupyter Notebook
💡 Skills Demonstrated
This project demonstrates practical skills in:

Exploratory Data Analysis
Data Cleaning
Data Preprocessing
Missing Value Handling
Data Type Conversion
Statistical Analysis
Correlation Analysis
Data Aggregation
Binning
Time-Series Analysis
Data Visualization
Business Insight Generation
Python Programming
Pandas Data Manipulation
🚫 Analysis Limitations
There are some limitations in the available dataset:

Review text is not available, so sentiment analysis cannot be performed.
Only the Last Updated date is available, so actual update frequency cannot be calculated.
Some categories and price ranges contain relatively few observations.
Correlation does not imply causation.
Install counts are available as aggregated values rather than exact user-level adoption data.
🚀 Future Improvements
Potential improvements to this project include:

Performing sentiment analysis using a dataset containing review text.
Building a predictive model for app ratings.
Creating an app recommendation system.
Performing statistical hypothesis testing.
Analyzing app popularity by category and genre in greater depth.
Investigating duplicate applications.
Performing outlier analysis on installs, reviews, and prices.
Building an interactive dashboard using Power BI or Looker Studio.
Performing NLP analysis on app descriptions and reviews.
📂 Project Structure
Google-Play-Store-EDA/
│
├── google_play_store_eda.ipynb
├── googleplaystore.csv
└── README.md
