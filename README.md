# CloudWalk Technical Case: The Empathic Credit System (ECS)

## Project Overview

This project analyzes a fictional dataset from CloudWalk's **Empathic Credit System (ECS)**, a credit system designed to use emotional and contextual data to offer personalized credit to users. The dataset contains emotional data, loan details, and user information, providing a rich basis for analyzing emotional patterns, loan outcomes, and lending policy effectiveness.

### Key Tasks:
- Explore and preprocess the dataset.
- Analyze emotional patterns over time and their relation to loan terms.
- Provide recommendations for improving the ECS's effectiveness and fairness.
- Visualize key metrics in a dashboard.
- Optionally, propose improvements to the emotional data collection and loan approval algorithms.

## Dataset Overview

The dataset (`ecs_data.db`) contains the following tables:

### Users Table:
| Column       | Type   |
|--------------|--------|
| user_id      | TEXT   |
| score        | REAL   |
| approved_date| TEXT   |
| denied_date  | TEXT   |
| credit_limit | REAL   |
| interest_rate| REAL   |
| loan_term    | INTEGER|

### Emotional Data Table:
| Column          | Type   |
|-----------------|--------|
| user_id         | TEXT   |
| timestamp       | TEXT   |
| intensity       | REAL   |
| time_of_day     | TEXT   |
| primary_emotion | TEXT   |
| relationship    | TEXT   |
| situation       | TEXT   |
| location        | TEXT   |
| weather         | TEXT   |
| physical_state  | TEXT   |
| preceding_event | TEXT   |
| grade           | REAL   |

### Loans Table:
| Column             | Type   |
|--------------------|--------|
| loan_id            | INTEGER|
| user_id            | TEXT   |
| loan_amount        | REAL   |
| total_amount       | REAL   |
| issue_date         | TEXT   |
| due_date           | TEXT   |
| paid_date          | TEXT   |
| installment_amount | REAL   |
| loan_amount_paid   | REAL   |
| status             | TEXT   |

## Prerequisites and Setup

### Required Tools and Libraries:
1. **SQLite** - Database used to store the ECS data.
2. **Python** - Used for data preprocessing, analysis, and visualization.
3. **Jupyter Notebook** - Chosen for interactive data analysis.
4. **Pandas** - For data manipulation.
5. **Matplotlib/Seaborn** - For data visualization.
6. **DBeaver** (optional) - To inspect the SQLite database.

## Key Findings:

1. **Database Structure Discrepancy:**
   - The actual structure of the dataset differed from the description provided in the case study. Below is the structure found for each table:

   ### Description of `df_users`:

   | Column        | Type    |
   |---------------|---------|
   | user_id       | int64   |
   | score         | float64 |
   | approved_date | object  |
   | denied_date   | object  |
   | credit_limit  | float64 |
   | interest_rate | float64 |
   | loan_term     | float64 |

   ### Description of `df_loans`:

   | Column             | Type    |
   |--------------------|---------|
   | loan_id            | int64   |
   | user_id            | int64   |
   | loan_amount        | int64   |
   | total_amount       | float64 |
   | issue_date         | object  |
   | due_date           | object  |
   | paid_date          | object  |
   | installment_amount | float64 |
   | loan_amount_paid   | float64 |
   | status             | object  |

   ### Description of `df_emotional_data`:

   | Column          | Type    |
   |-----------------|---------|
   | user_id         | int64   |
   | timestamp       | object  |
   | intensity       | float64 |
   | time_of_day     | object  |
   | primary_emotion | object  |
   | relationship    | object  |
   | situation       | object  |
   | location        | object  |
   | weather         | object  |
   | physical_state  | object  |
   | preceding_event | object  |
   | grade           | float64 |

   The discrepancies between the expected and actual data structures should not severely impact the analysis. However, they do highlight the need for careful data validation before proceeding with in-depth analysis.

2. **Suspicious Payment Timeliness:**
   - In the `loans` table, the difference between the `due_date` and `paid_date` is always negative, indicating that no payments were late. This anomaly could be a result of data collection or registration errors and should be addressed before evaluating loan performance.

3. **Identical Emotional Patterns Across Loans:**
   - A time series plot of emotion intensity vs. loan amount over time shows identical patterns for all emotions, raising concerns about data accuracy. This suggests an issue with data collection or registration, which could affect any analysis correlating emotions with loan performance.

## Next Steps:

1. **Data Validation:**
   - Validate the data thoroughly, paying particular attention to the discrepancies in the `loans` and `emotional_data` tables.
   
2. **Alternative Analyses:**
   - Proceed with analyses on reliable variables like loan amounts, repayment terms, and user credit scores.

3. **Recommendations for Data Collection:**
   - Review CloudWalk's data collection processes to prevent future inconsistencies, especially in emotional and loan repayment data.

## Conclusion:

While initial analysis reveals significant data quality issues, these insights provide direction for improving the ECS system. Future analyses should focus on resolving data discrepancies and exploring alternative pathways to generate actionable insights.

## License
This project is licensed under the MIT License.

