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

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/ecs-case-study.git
   cd ecs-case-study
