# Walmart Hurricane Analysis: Project Charter

## Project scope
Analyze Walmart transaction and weather data to investigate demand changes around hurricane-related conditions. This is a week one checkpoint, with preliminary findings documented in the project notebook.

## Project member
Suhail Abdulwasi (`suhailabdulwasi`) is currently working individually. Instructor approval is pending.

## Responsibilities and coordination
Notebook owner this week: Suhail Abdulwasi

Meeting time: Not applicable while working individually

Responsibilities: Source data profiling, cleaning, SKU consolidation, weather integration, exploratory visualization, and documentation.

## Research questions and owners

| Question | Owner | Status |
| --- | --- | --- |
| Q1: Demand surge | Suhail Abdulwasi | In progress |
| Q2: SKU consolidation | Suhail Abdulwasi | In progress |
| Q3: Weather correlation | Suhail Abdulwasi | Not started |
| Q4: Store and geography | Suhail Abdulwasi | Not started |
| Q5: Signal or artifact | Suhail Abdulwasi | Not started |

## Data quality risks to investigate
1. Exact duplicate transactions were confirmed and 30 were removed.
2. Unit prices were converted from text to numeric values.
3. A total of 130 negative quantity records were flagged for review.
4. A total of 884 timestamps remained unparseable after mixed format parsing.
5. Store identifiers and date or timezone alignment still require join validation.

## Cleaning decisions
The initial cleaning function removes exact duplicates, converts unit prices to numeric values, parses mixed timestamp formats, standardizes store identifiers, and flags negative quantities without silently deleting them. A six entry decision log is recorded in the notebook. Some entries count rows processed rather than values actually changed and will be refined during further validation.

## Progress at checkpoint
The project repository and charter have been established. Initial cleaning reduced the transaction dataset from 25,562 to 25,532 rows after removing 30 exact duplicates. The pipeline identified 130 negative quantity records and 884 unparseable timestamps for further review.

Initial SKU consolidation reduced 45 catalog SKUs to 43 canonical products by grouping three equivalent strawberry Pop Tarts 4 pack SKUs while keeping the 6 pack separate.

Preliminary demand analysis found that average daily transaction record volume was approximately 3.06 times the selected baseline during September 23 to 25, 2024, ahead of Hurricane Helene's September 26 landfall. A daily volume chart was generated. These are preliminary counts based on records with valid timestamps, not a fully validated unique order measure.

An Open Meteo API request retrieved 30 days of historical weather data. Weather and sales integration and correlation analysis have not yet been completed.

## Risks and next steps
The largest remaining technical risk is unreliable joins between Walmart transactions, store information, and weather data due to inconsistent identifiers, missing timestamps, or timezone differences. By October 28, 2026, Suhail will review unresolved timestamp and quantity issues, standardize store identifiers, and test a weather and sales join before expanding the analysis.

Individual work approval remains pending. The assignment specifies teams of 2 to 4 students.
