<p align="center">
  <img src="assets/banner.png" alt="EXPENSE-TRACKER Banner" width="100%">
</p>

# ◈ Expense Tracker

[![CI](https://github.com/ISBANDURAHUMAN-R/Expense-Tracker/actions/workflows/ci.yml/badge.svg)](https://github.com/ISBANDURAHUMAN-R/Expense-Tracker/actions/workflows/ci.yml)

## ◆ About the Project
Expense Tracker is a Python command-line utility for tracking and organizing personal financial expenditures. It allows users to record daily spending, classify transactions by category, review full transaction histories, and analyze overall spending metrics stored in a local CSV file.

## ❖ Key Features
- Add new expense records with timestamps, categories, amounts, and descriptions.
- Tabular display of all logged expenditures.
- Automated calculation of cumulative spending.
- Category-wise expense grouping and summary generation.
- Persistent local storage using `expenses.csv`.

## ◆ System Architecture
```mermaid
graph TD
    subgraph CLI ["Console User Interface"]
        Menu[Interactive Menu Loop] --> Option{Selected Operation}
        Option -- 1 --> AddExp[Add New Expense]
        Option -- 2 --> ViewExp[View All Records]
        Option -- 3 --> CalcTotal[Calculate Cumulative Total]
        Option -- 4 --> GroupCat[Category-wise Summary]
    end

    subgraph AnalyticsEngine ["Expenditure Processing Engine"]
        AddExp --> InputVal[Date & Amount Input Validator]
        InputVal --> RecordFormat[Format Tuple: Date | Category | Amount]
        ViewExp --> TabularFormat[Tabular Console Formatter]
        CalcTotal --> SumAggregator[Accumulator Sum Engine]
        GroupCat --> CatAggregator[Category Dictionary Aggregator]
    end

    subgraph FileStore ["Data Persistence Layer"]
        RecordFormat --> CSVWriter[CSV Append Stream]
        CSVWriter --> CSV[(expenses.csv)]
        CSV --> CSVReader[CSV Read Stream]
        CSVReader --> TabularFormat
        CSVReader --> SumAggregator
        CSVReader --> CatAggregator
    end
```

## ⬢ Technologies Used
- Python 3
- Python Standard Library (`csv`, `datetime`)

## § Requirements
- Python 3.8 or higher

## ▲ Installation & Execution
```bash
# Run the application
python main.py
```

## ※ Developer
Developer: ISBANDU RAHUMAN R  
GitHub: https://github.com/ISBANDURAHUMAN-R
