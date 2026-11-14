# Walmart Hurricane Analytics: Project Charter

Project member

Suhail Abdulwasi completed the project independently.

Project scope

Analyze synthetic Walmart transactions from September 2024 alongside real historical weather to investigate pre-hurricane purchasing patterns and develop evidence-backed stocking recommendations.

Responsibilities

Suhail handled data loading, cleaning, SKU consolidation, weather API integration, SQLite queries, visualizations, analysis, and documentation.

Research questions and final status

1. Demand surge identification — Completed. Compared average daily category sales during September 5–18 with September 19–25. Breakfast Foods had the largest relative increase at 4.08 times baseline.

2. SKU consolidation — Completed. Reviewed all 45 catalog SKUs and applied a conservative mapping that reduced the catalog to 38 canonical identifiers while preserving total recorded sales quantities at 49,584. Uncertain matches and conflicting package sizes remained separate.

3. Weather correlation — Completed. Retrieved real Open-Meteo precipitation, wind, and pressure data, validated daily joins, and examined correlations at different lags.

4. Store geography — Completed. Compared surge magnitude and timing across 12 stores, identified outliers, and examined approximate forecast-path proximity for 11 stores with available coordinates.

5. Signal versus artifact — Completed. Compared board-game and playing-card sales, investigated discrepancies between SQLite and transaction totals, reviewed inventory evidence, and provided a cautious stocking recommendation.

Data and cleaning

The notebook loads all four supplied CSV files and the SQLite database. Exact duplicate removal reduced transactions from 25,562 to 25,532 rows. Dates, quantities, prices, category labels, and store identifiers were standardized as needed for the analyses.

Daily category analysis excluded 1,011 records with unusable timestamps, categories, or quantities. Pop-Tarts daily analysis excluded 54 rows without usable timestamps. SKU consolidation included assertions confirming that total recorded quantities were preserved.

Analysis periods

Baseline: September 5–18, 2024, fourteen days.
Surge: September 19–25, 2024, seven days.
Landfall reference date: September 26, 2024.

Comparisons use average daily sales rather than period totals to account for unequal window lengths.

Weather and geographic integration

Historical Orlando weather was requested in America/New_York time and matched to daily sales under the assumption that transaction timestamps represent local time. The validated weather join preserved all 30 daily sales rows.

The geographic comparison uses Helene's September 24, 2024 NHC forecast as an external reference for the synthetic sales data. Tallahassee was excluded from distance calculations because its coordinates were missing.

Deliverables

The final notebook contains all five analytical answers, supporting visualizations, five reflection responses, and the final recommendation. The README explains the project, data sources, dependencies, and how to run the notebook.

Limitations

Transactions are synthetic, and weather represents one location and month. Correlations and selected lags do not establish causation. The forecast was issued after measured purchasing onset, and centerline distances are approximate.

Missing timestamps, uncertain package definitions, disagreements between SQLite and transaction totals, and incomplete inventory snapshots limit operational conclusions.

Final recommendation

Prioritize Emergency Supplies and Breakfast Foods, consolidate equivalent SKU demand, and allocate stock using verified store inventory needs. Increase board-game stock cautiously while reconciling sales sources, package definitions, and incoming inventory.
