## Project Overview
This project is part of the MIC AIML Department Recruitment Challenge for the Data Science track. It is an AI Travel Analyst built to explore flight data and find what drives ticket costs.

## Problem Statement
The goal is to analyze flight prices, uncover pricing factors, and help travelers make smarter booking decisions.

## Installation Instructions
1. Download the Jupyter Notebook (`.ipynb`) file.
2. Open it in Google Colab.
3. Upload the required flight dataset to Colab and run the cells.

## Dataset Used
The mandatory flight pricing dataset provided in the task guidelines.

## Methodology
1. Loaded the dataset using Pandas.
2. Cleaned missing values by dropping empty rows.
3. Cleaned the Price column by removing commas and converting text to numeric data.
4. Used a random sample of 5,000 rows to optimize visualization rendering speed.
5. Generated 5 charts to analyze pricing trends.

## Technologies Used
Python, Pandas, Matplotlib, Seaborn, Google Colab.

## Results
* Last-minute bookings are significantly more expensive.
* Flights with 2 stops cost the most on average.
* **Recommendation:** Book well in advance and look for direct or 1-stop flights to save money.

## Challenges Faced
The large dataset (42,000+ rows) froze the charts initially. I fixed this by using data sampling. The Price column was formatted as text with commas, which I fixed using Pandas string replacement.

## Future Improvements
