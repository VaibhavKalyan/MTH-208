# Used Car Market Analytics Dashboard 

[![Built with R](https://img.shields.io/badge/Built_with-R-blue.svg)](https://www.r-project.org/)
[![Built with Shiny](https://img.shields.io/badge/UI-Shiny-lightgrey.svg)](https://shiny.rstudio.com/)
[![Deployed on shinyapps.io](https://img.shields.io/badge/Deployed-shinyapps.io-blueviolet.svg)](https://unsaidvolcano.shinyapps.io/mth208proj/)

> An interactive data product designed to analyze the Indian used car resale market, identifying key financial drivers, modelling depreciation, and uncovering geographic pricing inefficiencies.

## Live Application
The dashboard is publicly deployed and accessible here: **[Used Car Insights Dashboard](https://unsaidvolcano.shinyapps.io/mth208proj/)**

##  Overview
This project delivers a comprehensive exploratory data analysis (EDA) of the Indian used car market. By combining live web-scraped listings with existing datasets, this application models vehicle depreciation across segments and provides actionable, data-driven recommendations for prospective buyers.

### Key Insights Discovered
* **Primary Price Predictors:** Vehicle age and kilometers driven were identified as the strongest negative price predictors.
* **Geographic Variations:** Significant pricing disparities exist at the city level (e.g., CNG hatchbacks command higher median prices in certain metropolitan areas).
* **Segment Depreciation:** High mileage penalizes smaller vehicle segments (Hatchbacks) much more severely than utility segments (MUVs).

## Features
* **Global Dynamic Filtering:** Filter the entire dataset instantly by City, Brand, Market Segment, Fuel Type, Price Range, Mileage, and Age.
* **Recommendation Engine:** A "Best Value" screening algorithm that flags listings priced at least 20% below their model-level average.
* **Depreciation Modeling:** Visualizes per-year depreciation rates by fuel type using linear regression.
* **Market Overview:** Univariate and bivariate visual analysis of pricing structures across different geographic and structural factors.

## Project Structure
```text
├── app/
│   ├── app.R                   # Main Shiny Dashboard application script
│   ├── cars_cleaned_v3.csv     # Cleaned analytical dataset (~2,000 records)
│   └── scraping/
│       ├── scraping.R          # Web scraping script (rvest) for CarDekho
│       └── cleaning.R          # Data cleaning and transformation pipeline
├── report.pdf                  # Detailed course project report
├── requirements.R              # R package dependencies
└── Readme.md                   # Project documentation
```

## Installation & Usage

### Prerequisites
Ensure you have R and RStudio installed. You will need to install the required dependencies by running the `requirements.R` script, or by manually installing the following packages:
```r
install.packages(c("shiny", "shinydashboard", "ggplot2", "dplyr", "forcats", "scales", "DT", "tidyr"))
```

### Running Locally
1. Clone this repository to your local machine.
2. Navigate to the `app/` directory.
3. Open `app.R` in RStudio.
4. Click the **"Run App"** button in the top right corner of the script editor.

### Recreating the Dataset (Optional)
The repository includes the fully cleaned dataset (`cars_cleaned_v3.csv`). If you wish to recreate the dataset from scratch:
1. Navigate to the `app/scraping/` directory.
2. Execute `scraping.R` to fetch live data (respects rate limits).
3. Execute `cleaning.R` to process the raw output into the final analytical format.

## Team Members
This project was developed as part of the **MTH-208** course by:
* Yatin Preetam Bhojwani (241211)
* Vaibhav Kalyan (241125)
* Vaibhav Khare (251080109)
* Kaustabh Roy (251080071)
