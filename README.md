# EDA Movies Project (TMDb + IMDb)

This repository contains a **comprehensive Exploratory Data Analysis (EDA)** on a large movies dataset (~1,100,000 movies) combining TMDb and IMDb information. The project follows a structured 7-step EDA pipeline, providing insights into movie trends, genres, runtimes, budgets, revenues, and IMDb ratings across decades.


## Project Overview  

**Objective:**  
Understand the evolution and characteristics of movies over time, examining both **numerical features** (budget, revenue, runtime, ROI, IMDb rating) and **qualitative features** (genres, production countries), and extract actionable insights without using any machine learning.


## EDA Pipeline  

### Step 1: Data Import  
- Loaded TMDb and IMDb datasets.  
- Verified proper data types and formats for critical columns.  

### Step 2: Data Inspection  
- Explored dataset shape, null values, and unique counts.  
- Identified inconsistencies (e.g. missing values).  

### Step 3: Data Cleaning  
- Split dataset into two dataframes for targeted analysis:  
  - **Movies evolution & genre trends** (kept ~640,000 movies with valid release dates and genres and ~13,000 with valid economical data)  
  - **IMDb ratings & weighted analysis** (kept ~285,000 movies with IMDb rating and vote count)  
- Handled missing values carefully to preserve maximum data.  
- Removed exact duplicates after verification.  

### Step 4: Feature Engineering  
- Created new features:  
  - `decade` from `release_date`  
  - `ROI = revenue / budget` (where available)  
  - A kind of `weighted_rating = (imdb_rating * vote_count)` for better evaluation across movies which represents total score  
  - Simplified genres into `genres_simplified` for clarity  
- Constrct runtime bins and more   

### Step 5: Statistical Analysis  
- Filtered the dataframe with ~13,000 to remove the outliers for economical analysis.  
- Explored trends across decades (e.g., average runtime, budgets, revenue, ROI).  
- Grouped by decade and genre to identify evolution of production and popularity.  

### Step 6: Visualization  
- Barplots per decade for runtime, budget, revenue, and ROI.
- Top movies per genre and decade visualized using weighted rating (better said: total score).

### Step 7: Conclusion  
**Key Insights:**  
- Geometric increase in movie production from 1990s to 2010s.  
- Shift in most common genres over decades (e.g. Documentary-Comedy-Drama → Documentary-Drama-Comedy).  
- Longest runtime movies produced in 1980s-1990s; median runtime decreased in later decades.  
- Highest budgets and revenues in 1990s; most profitable decade was 1970s.  
- Highest ROI observed in 1910s; genre-specific ROI highlights the efficiency of “TV Movies” and low-budget productions.  
- Weighted IMDb rating allowed identification of top movies per genre and decade, accounting for both rating and vote count.  

## Tools & Libraries  
- Pandas  
- Numpy  
- OS  
- Matplotlib  
- Seaborn  
- Kagglehub  

## Summary
This project demonstrates **data handling, feature engineering, statistical analysis and visualization** on a large-scale movies dataset. The structured 7-step pipeline ensures clarity, reproducibility, and meaningful insights into movie trends, financials, and audience ratings across decades.

## Author  
Panagiotis Kardatos,  
Mathematician, Aspiring ML Engineer
