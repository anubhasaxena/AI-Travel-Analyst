# AI Travel Analyst: Flight Price Exploration

## Project Overview
This project is built for the Data Science and Visualization track of the MIC AIML Department Recruitment Challenge. It serves as a data-driven solution to analyze flight prices, uncover the factors that drive costs, and help travelers make smarter booking decisions. This repository contains the code and insights for Part 1: Exploration.

## Problem Statement
Flight prices fluctuate based on numerous hidden variables, making it difficult for consumers to know when and how to book the cheapest fares. The goal of this project is to clean a raw dataset of flight details, visualize the data to identify major factors affecting flight prices, and present actionable recommendations for travelers.

## Dataset Used
The dataset used for this project was provided via the mandatory Google Drive link outlined in the challenge requirements. It includes features such as Airline, Source, Destination, Travel Class, Total Stops, Days Before Departure, and Price.

## Technologies Used
* **Python**: The core programming language used.
* **Pandas**: Used for data manipulation, cleaning, and preprocessing.
* **Matplotlib & Seaborn**: Used to generate data visualizations.
* **Google Colab**: The cloud-based notebook environment used for development.

## Methodology
To ensure accurate analysis, the raw data underwent strict preprocessing before visualization:
1. **Missing Value Handling:** Dropped all rows containing null values to ensure data integrity.
2. **Data Type Conversion:** Identified that the target variable (`Price`) was formatted as a string containing currency symbols and commas. Utilized Regular Expressions (Regex) to strip non-numeric characters and converted the column to a numeric data type (`float`).
3. **Standardization:** Standardized categorical text data by converting all `Airline` strings to uppercase to prevent duplicate categorizations (e.g., treating "Emirates" and "EMIRATES" as one entity). Replaced "non-stop" with "0" in the `Total_Stops` column and extracted the numeric values.
4. **Performance Optimization:** Due to the massive size of the dataset causing extreme latency in rendering visualizations, I implemented a data sampling technique. I extracted a random, reproducible sample of 10,000 rows (`random_state=42`) to generate fast, accurate exploratory charts.

## Results & Insights
Based on the exploratory data analysis, three major factors drive flight costs:
1. **Travel Class Dominates Price:** Travel class is the single largest factor driving flight costs. Stepping up from Economy to Premium Economy, Business, or First Class results in a massive, exponential price increase.
2. **Airline Tiers:** The carriers divide strictly into two pricing tiers. Premium/International carriers (like Emirates, Lufthansa, and British Airways) command baseline prices nearly five times higher than domestic budget carriers (like Indigo, GoFirst, and SpiceJet).
3. **The Booking Sweet Spot:** Price vs. Days Before Departure analysis shows highly volatile and peaked prices within 14 days of a flight. The optimal window to secure a low, stable fare is between 15 and 45 days prior to departure.

## Challenges Faced
* **Dirty Currency Data:** While converting string prices to integers, I encountered a `ValueError` (e.g., `Unable to parse string ".4534.73"`). This occurred because the original data contained formats like "Rs. 4,534.73". Stripping letters left multiple decimal points. I resolved this by isolating the numeric values using targeted string extraction before coercing them to numeric types.
* **Computational Limits:** Attempting to render a Seaborn histogram on the entire dataset took over four minutes. I solved this by utilizing a representative 10,000-row sample, reducing render times to under 3 seconds without losing statistical accuracy.

## Future Improvements
To expand on this project in the future, I plan to:
* Perform feature engineering (e.g., extracting the month from the departure date to analyze seasonality).
* Build a Machine Learning prediction model using Scikit-Learn to actively forecast ticket prices.
* Deploy the model in an interactive web application using Streamlit.

## Challenges Faced
The large dataset (42,000+ rows) froze the charts initially. I fixed this by using data sampling. The Price column was formatted as text with commas, which I fixed using Pandas string replacement.

## Future Improvements
As a first-year student, I want to learn machine learning next so I can predict exact future prices.
