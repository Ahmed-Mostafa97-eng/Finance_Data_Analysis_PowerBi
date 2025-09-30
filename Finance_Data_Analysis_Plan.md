# Finance Data Analysis Plan

This document outlines a plan for analyzing the provided financial data to derive insights into revenue, spending, project performance, and payment methods. The analysis will be based on the `FinanceData.xlsx` file and will aim to reproduce and expand upon the key metrics and visualizations presented in the Finance Dashboard.

## 1. Data Understanding and Preparation

**Objective**: To load, inspect, clean, and prepare the `FinanceData.xlsx` for comprehensive analysis.

**Steps**:

1.  **Load Data**:
    *   Load `FinanceData.xlsx` (Sheet: `Sheet1`) into a DataFrame. The dataset contains the following columns:
        *   `Date`: Transaction date.
        *   `Department`: Department involved in the transaction.
        *   `Expense Category`: Classification of the expense (e.g., Equipment, Training, Travel).
        *   `Amount`: The amount of the expense.
        *   `Revenue`: Revenue generated (potentially per transaction or related to a project).
        *   `Region`: Geographical region.
        *   `Project`: Project associated with the transaction.
        *   `Vendor`: Vendor involved.
        *   `Currency`: Currency of the transaction.
        *   `Payment Method`: Method used for payment (e.g., Cash, Cheque, Bank Transfer, Credit Card).
        *   `Approval Status`: Approval status of the transaction.
        *   `City`: City where the transaction occurred.

2.  **Data Cleaning & Transformation**:
    *   **Date Conversion**: Convert the `Date` column to datetime objects.
    *   **Data Types**: Ensure numerical columns (`Amount`, `Revenue`) are correctly typed. Handle any non-numeric values that might prevent conversion.
    *   **Missing Values**: Inspect for and handle any missing values. Depending on the column, strategies might include imputation (e.g., mean, median), filling with 'Unknown', or dropping rows if missing data is minimal and non-critical.
    *   **Consistency**: Check for consistency in categorical columns (e.g., `Department`, `Expense Category`, `Region`, `Project`, `Payment Method`, `Approval Status`, `City`). Standardize if necessary.

3.  **Feature Engineering**:
    *   **Profit/Loss**: Calculate `Profit` for each transaction as `Revenue - Amount` (assuming `Amount` represents cost/spending).
    *   **Year and Month**: Extract `Year` and `Month` from the `Date` column for time-series analysis.

## 2. Dashboard Recreation and Validation

**Objective**: To reproduce the key metrics and visualizations from the provided Finance Dashboard using the prepared data.

**Steps**:

1.  **Key Performance Indicators (KPIs)**:
    *   **Total Revenue**: Sum of the `Revenue` column.
    *   **Total Spendings**: Sum of the `Amount` column.

2.  **Visualizations**:
    *   **Most Spending Goes Per Category**: Pie chart showing the percentage distribution of `Amount` by `Expense Category`.
    *   **Sum of Revenue by Expense Category**: Bar chart showing the sum of `Amount` (spending) by `Expense Category`. (Note: The dashboard labels this as 'Sum of Revenue by Expense Category', but given the context of 'Most Spending Goes Per Category', it is interpreted as spending).
    *   **Count of Currency by Payment Method**: Donut chart showing the distribution of `Payment Method`.
    *   **Sum of Revenue by Month**: Line chart showing the sum of `Revenue` over `Month`.
    *   **Sum of Revenue by City**: Bar chart showing the sum of `Revenue` by `City`.
    *   **Total Profit Per Project**: Bar chart showing the sum of `Profit` (Revenue - Amount) for each `Project`.

