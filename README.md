# Extreme Weather Events Analysis Project
The Extreme Weather Events Analysis Project! In This repository showcases the use of Python for data analysis and visualization to explore the impact of extreme weather events in the United States since 2000. We employ advanced data processing and analytical techniques to uncover trends, assess damages, and examine the most significant weather events.

#### Table of Contents
1. [Introduction](#introduction)
2. [Project Components](#project-components)
3. [Python code overview](#python-code-overview)
4. [Analysis and Insights](#analysis-and-Insights)

## Introduction
This project utilize Python to Analyze 1.26 million records of NOAA data on U.S. extreme weather events since 2000, focusing on trends, property damage, and fatalities. Utilized advanced data cleaning, geospatial analysis, and inflation-adjusted economic assessment techniques to reveal increasing frequency and impact of severe weather.

Primary Dataset: NOAA Storm Events Database

## Project Components
The project is structured around Python analysis and visualization in Jupyter notebooks:

1. Data Collection and Exploration:
Loaded and examined NOAA's storm events data using Python libraries.
Conducted initial exploratory data analysis (EDA) to understand the dataset's structure and content.

2. Data Cleaning and Processing:
Cleaned and processed the data to focus on relevant columns and rows.
Standardized formats and adjusted for inflation in property damage values.

3. Advanced Data Analysis:
Applied Python's data manipulation and statistical tools to analyze trends and correlations.
Conducted in-depth analysis of specific events such as Hurricane Katrina and the 2011 Tornado Outbreak.

4. Visualization and Reporting:
Created visualizations to present findings using Python's plotting libraries.
Compiled detailed reports and presentations to effectively communicate the insights.

## Python code overview
#### Data Collection and Exploration
**Data Loading:** Utilized pandas to load CSV data files and inspect the dataset.
```python
import pandas as pd
data = pd.read_csv('event_type.csv')
```

**Exploratory Data Analysis (EDA):** Conducted initial data exploration using pandas and numpy to understand distributions, missing values, and data types.
```python
data.info()
data.describe()
```

#### Data Cleaning and Processing
**Data Cleaning:**
- Managed missing values and handled duplicates to ensure data quality.
- Converted categorical data into numerical formats where necessary.
- Adjusted financial figures for inflation using U.S. Bureau of Labor Statistics data.
```python
data['damage_property'] = data['damage_property'].str.replace('K', '000').astype(float)
```

**Feature Engineering:**
- Created new features such as event categories and combined related data for enhanced analysis.
```python
data['event_group'] = data['event_type'].apply(lambda x: categorize_event(x))
```

#### Advanced Data Analysis
**Statistical Analysis:**
Employed scipy and statsmodels for statistical analysis to explore correlations and trends.
```python
from scipy import stats
correlation = stats.pearsonr(data['property_loss'], data['fatalities'])
```

**Time Series Analysis:**
Analyzed trends over time using pandas time series functionality to detect changes in the frequency and impact of events.
```python
data['date'] = pd.to_datetime(data[['year', 'month', 'day']])
data.set_index('date').resample('M').mean()
```

#### Visualization and Reporting
**Data Visualization:**
- Created a range of visualizations using matplotlib and seaborn to represent findings visually.
- Used plotly for interactive charts and maps to better engage with the data.
```python
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10,6))
sns.barplot(data=data, x='state', y='property_loss')
plt.xticks(rotation=90)
plt.title('Property Loss by State')
```

**Reporting:**
- Summarized the findings into detailed reports and presentations using the results from the Jupyter notebooks.

## Analysis and Insights:
1. Property Loss Analysis:
- Hurricanes have caused the highest property losses, with Hurricane Katrina being the most devastating event.
- Rainstorms and strong winds are frequent but less financially destructive compared to hurricanes.

2. Trends in Weather Events:
- There is an increasing trend in the frequency of rainstorms, strong winds, and hurricanes over the past two decades.
- High-cost disasters, however, remain relatively steady in number.

3. Geographic Impact:
- Texas, Louisiana, and Florida are the most affected states in terms of property losses due to extreme weather.
- Wildfires in California represent a significant portion of recent high-cost events.

4. Fatalities and Specific Events:
- Louisiana, Texas, and Arizona have the highest number of deaths from extreme weather events.
- Detailed case studies on Hurricane Katrina and the 2011 Tornado Outbreak show the severe impact on human life and property.

