# Walmart Hurricane Analysis — Project Charter

## Project scope
Analyze Walmart transaction and weather data to investigate demand changes around hurricane-related conditions. This is a week-one checkpoint; results will be reported only after running analysis.

## Project member
- Suhail Abdulwasi (`suhailabdulwasi`) — working individually, instructor approval pending.

## Responsibilities and coordination
- Notebook owner this week: Suhail Abdulwasi
- Meeting time: Not applicable while working individually
- Responsibilities: source-data profiling, cleaning, SKU consolidation, weather integration, exploratory visualization, and documentation.

## Research questions and owners
| Question | Owner | Status |
|---|---|---|
| Q1 — Demand surge | Suhail Abdulwasi | Not started |
| Q2 — SKU consolidation | Suhail Abdulwasi | Not started |
| Q3 — Weather correlation | Suhail Abdulwasi | Not started |
| Q4 — Store and geography | Suhail Abdulwasi | Not started |
| Q5 — Signal or artifact | Suhail Abdulwasi | Not started |

## Data-quality risks to investigate
The following are issues indicated by the lab prompt, not yet verified against this project's data:
1. Duplicate transaction records.
2. `unit_price` stored as text, including values prefixed by `$`.
3. Negative `quantity` entries requiring a documented handling rule.
4. Sales timestamps requiring parsing and timezone alignment.
5. Inconsistent `store_id` values that may prevent joining to store reference data.

## Proposed cleaning decisions
Implement functions to standardize prices, quantities, timestamps, store IDs, and duplicate handling. Record row counts before and after and maintain a decision log with counts of affected rows. The negative-quantity policy will be determined after inspecting examples.

## Progress at checkpoint
Repository and charter initialized. No cleaning, SKU-mapping, API, or visualization outputs are claimed until verified in the notebook.

## Risks and next steps
The largest near-term technical risk is unreliable store or weather joins caused by incompatible keys, dates, or timezones. This week, Suhail will profile keys and timestamps, implement cleaning functions, and test a small join before expanding the analysis. Individual-work approval is still pending; the assignment specifies teams of 2–4 students.
