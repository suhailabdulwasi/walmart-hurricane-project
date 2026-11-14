# Walmart Hurricane Analytics

DS 2002 Midterm Project
Author: Suhail Abdulwasi

Introduction

This project analyzes synthetic Walmart transaction data from September 2024 alongside real historical weather data. It covers data cleaning, SKU consolidation, weather API integration, SQLite analysis, and hurricane preparedness recommendations.

Final notebook

[Open final notebook on Colab](https://colab.research.google.com/drive/1D4Kz10acMvPeoYiRhf1YbQaWoqmivR-1)

The notebook includes all five analytical questions, supporting charts, five reflection answers, and the final recommendation. Other notebooks in this repository are earlier checkpoints.

How to run

1. Open the final notebook in Google Colab.
2. Connect to a Python runtime.
3. Restart the session and run all code cells from top to bottom.

An internet connection is required. The notebook downloads the CSVs and SQLite database from the course repository and retrieves historical weather data from Open-Meteo. No API key or manual file upload is needed.

The notebook uses pandas, matplotlib, numpy, requests, and Python’s built-in sqlite3, pathlib, and re modules. These are available in the standard Google Colab environment.

Data sources

- [Project brief and provided data](https://github.com/jasontpv/DS2002FA26/tree/main/notebooks/06-midterm-walmart)
- [Open-Meteo Historical Weather API](https://archive-api.open-meteo.com/v1/archive)
- [NHC Helene forecast issued September 24, 2024](https://ftp.nhc.noaa.gov/atcf/archive/2024/messages/al092024.discus.005)

The notebook loads walmart_transactions.csv, product_catalog.csv, store_locations.csv, distribution_centers.csv, and inventory_and_sales.db.

Findings

- Breakfast Foods had the largest relative category increase at 4.08 times baseline.
- Reviewing all 45 catalog SKUs reduced the catalog to 38 canonical product identifiers while preserving total recorded sales quantities at 49,584.
- Exploratory wind correlations were strongest when sales preceded weather by approximately two days.
- The store analysis compared surge magnitude, timing, outliers, and approximate distance to the forecast centerline.
- Average daily board-game package sales increased by 141.86%, while SQLite and transaction totals disagreed.

The baseline period was September 5–18, 2024, and the surge period was September 19–25. Comparisons use average daily sales to account for the unequal window lengths.

Recommendations and limitations

Prioritize Emergency Supplies and Breakfast Foods, consolidate equivalent SKU demand, and replenish stock based on verified store inventory needs. Increase board-game stock cautiously while reconciling sales sources and package definitions.

Transactions are synthetic, weather represents one location and month, and correlations do not establish causation. The geographic comparison uses approximate distances to a forecast issued after the measured purchasing onset. Missing timestamps, inconsistent package sizes, and incomplete inventory snapshots limit the findings.

Reflections

All five reflection answers are included in the final notebook under Reflection.
