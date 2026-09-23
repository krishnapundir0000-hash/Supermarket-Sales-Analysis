# Supermarket Sales & Profitability Optimization

## 1. Project Overview

This project develops an interactive data analytics application for supermarket sales and gross-income performance.

The application analyzes sales performance across branches, product lines, customer types, purchasing periods, payment methods, and transaction characteristics. The goal is to convert transaction-level data into business insights, risks, opportunities, and actionable management decisions.

**Domain:** Supermarket / Retail Analytics  
**Primary Users:** Regional/Branch Sales Management  
**Secondary Users:** Branch Managers, Sales & Marketing, Business Management

---

## 2. Business Problem

Supermarket management needs a data-driven approach to understand variations in sales and profitability across branches, product lines, customer segments, and purchasing periods, identify key performance drivers and areas requiring attention, and translate those findings into actionable business decisions.

The core decision framework is:

**Performance → Trends → Drivers → Risks & Opportunities → Actions**

---

## 3. Project Objectives

- Measure overall sales and gross-income performance.
- Compare performance across branches.
- Compare product-line performance.
- Analyze Member vs Normal customer performance.
- Identify monthly, weekday, and time-period trends.
- Analyze observable performance drivers.
- Identify business risks and opportunities.
- Translate findings into practical management actions.
- Assess whether contextual transaction features can predict high-value transactions.
- Provide an interactive decision-support interface.

---

## 4. Dataset

The project uses a cleaned supermarket transaction dataset maintained in Google Sheets.

**Dataset:** Supermarket transaction data  
**Rows:** 1,000  
**Columns:** 17  
**Date coverage:** January–December 2019  
**Transactions:** 1,000  
**Missing values:** 0 in the original 17 columns

### Dataset Source

Google Sheets:

https://docs.google.com/spreadsheets/d/1IHsqV1qRNCvOk_IenUlxgmynPRVTTJv3tyfdJiStKTg/edit?usp=sharing

CSV export used by the notebook:

https://docs.google.com/spreadsheets/d/1IHsqV1qRNCvOk_IenUlxgmynPRVTTJv3tyfdJiStKTg/export?format=csv&gid=1992415326

---

## 5. Dataset Features

The final analytical dataset contains:

- `Invoice ID`
- `Branch`
- `City`
- `Customer Type`
- `Gender`
- `Product Line`
- `Unit Price`
- `Quantity`
- `Tax 5%`
- `Sales`
- `Date`
- `Time`
- `Payment`
- `Cogs`
- `Gross Margin %`
- `Gross Income`
- `Rating`

---

## 6. Data Preparation

The dataset was reviewed and cleaned before analysis.

Key preparation steps included:

1. Quantity values were verified as whole-number transaction quantities.
2. Tax values were cross-verified against the 5% calculation.
3. Dates were standardized.
4. Time values were standardized.
5. COGS and Gross Income were cross-verified.
6. Rating values were retained without modification.
7. Date formatting was corrected.
8. Calculation mismatches were checked.
9. No records were removed during cleaning.
10. Invoice IDs were checked for uniqueness.

There are 1,000 unique Invoice IDs and no duplicate Invoice IDs.

Matching transaction attributes were not automatically removed because transactions with similar attributes can still represent legitimate separate invoices.

---

## 7. Key Performance Indicators

The project uses the following core KPIs.

### Total Sales

`SUM(Sales)`

### Total Gross Income

`SUM(Gross Income)`

### Gross Margin %

`Total Gross Income / Total Sales × 100`

### Total Transactions

`COUNT(Invoice ID)`

### Average Order Value (AOV)

`Total Sales / Total Transactions`

### Gross Income per Transaction

`Total Gross Income / Total Transactions`

Supporting metrics include:

- Quantity
- COGS
- Tax
- Unit Price

The dataset does not contain operating expenses, so the project does **not** use Net Profit as a KPI.

---

## 8. Overall KPI Results

| KPI | Result |
|---|---:|
| Total Sales | 322,967.43 |
| Total Gross Income | 15,379.92 |
| Gross Margin % | 4.762065% |
| Total Transactions | 1,000 |
| Average Order Value | 322.96743 |
| Gross Income / Transaction | 15.37992 |

---

## 9. Analytical Methodology

The analysis follows:

**DATA → CLEANING → ANALYSIS → BUSINESS INSIGHT → DECISION → ACTION**

The application evaluates:

### Performance
- Total Sales
- Gross Income
- Gross Margin
- Transactions
- AOV

### Trends
- Monthly performance
- Day-of-week performance
- Time-period performance

### Drivers
- Branch
- Product Line
- Customer Type
- Quantity
- Unit Price Band
- Payment Method

### Business Decision Areas
- Risks
- Opportunities
- Recommended actions
- Monitoring KPIs

---

## 10. Key Findings

### Monthly Performance

January recorded the highest monthly sales at **86,562.76**.

April recorded the lowest monthly sales at **7,957.65**.

January's sales were therefore substantially higher than April's, but the dataset has an irregular distribution of transactions across months. Therefore, the analysis does not claim conventional seasonal behavior from this dataset alone.

### Branch Performance

Branch sales:

- Alex: 106,200.57
- Cairo: 106,198.00
- Giza: 110,568.86

Giza recorded the highest branch sales and an AOV of approximately **337.10**.

### Product Line

**Food And Beverages** recorded the highest sales at **56,144.96**.

**Health And Beauty** recorded the lowest sales at **49,193.84**.

**Home And Lifestyle** recorded the highest product-line AOV at approximately **336.64**.

### Customer Type

Member customers generated:

- Sales: **189,695.16**
- AOV: **335.74**

Normal customers generated:

- Sales: **133,272.27**
- AOV: **306.37**

Members therefore represented approximately **58.74% of total sales**.

### Weekday Performance

Tuesday recorded the highest weekday sales.

Monday recorded the lowest weekday sales at **35,048.96**.

Monday also recorded the lowest AOV at approximately **289.66**.

### Time Period

Afternoon represented approximately:

- **45.83% of sales**
- **45.40% of transactions**

This makes afternoon activity an important operational period for staffing and inventory readiness.

### Quantity

Transactions with quantity 10 had the highest average sales, approximately **587.64**.

### Unit Price

The **80–100** unit-price band recorded the highest sales at **122,737.25**.

---

## 11. Risks

### April Low Sales

April recorded the lowest monthly sales at **7,957.65**, creating a clear area for management review.

**Suggested review:** April-specific transaction volume, product mix, branch activity, and customer activity.

**Monitoring KPIs:** Monthly Sales, Transactions, AOV.

### Member Sales Concentration

Members contribute approximately **58.74% of total sales**.

**Suggested review:** Member purchasing patterns and customer engagement.

**Monitoring KPIs:** Member Sales Share, Member AOV, Transactions.

### Monday Performance

Monday recorded the lowest weekday sales and AOV.

**Suggested review:** Monday transaction volume, product mix, and customer activity.

**Monitoring KPIs:** Monday Sales, Monday AOV, Transactions.

### Health And Beauty Performance

Health And Beauty recorded the lowest product-line sales at **49,193.84**.

**Suggested review:** Demand, transaction volume, product-level performance, and customer mix.

**Monitoring KPIs:** Product Sales, Transactions, AOV.

---

## 12. Opportunities

### Afternoon Operations

Afternoon contributes approximately 45.83% of total sales.

**Action area:** Align staffing and inventory readiness with afternoon demand.

### Giza Branch

Giza recorded the highest branch sales and an AOV approximately 4.33% above the branch average.

**Action area:** Examine its product and customer mix to identify observable practices that may be useful for comparison with other branches.

### Food And Beverages

Food And Beverages recorded the highest product-line sales.

**Action area:** Review transaction volume, quantity, and customer mix to understand its performance pattern.

### Member Customers

Members have a higher AOV than Normal customers.

**Action area:** Study member purchasing patterns and membership engagement.

---

## 13. Machine Learning Assessment

The project includes a controlled ML assessment for **Potential High-Value Transaction Classification**.

### Target

A transaction is classified as potentially high-value when:

`Sales >= Median Sales`

The median threshold is **253.85**.

This creates a balanced target:

- Lower-value transactions: 500
- High-value transactions: 500

### Features Used

- Branch
- Customer Type
- Gender
- Product Line
- Payment
- Day
- Time Period
- Rating

### Leakage Controls

The following direct transaction-value fields were excluded from the predictive feature set:

- Sales
- Tax 5%
- Cogs
- Gross Income
- Unit Price
- Quantity
- Invoice ID
- Raw Date
- Raw Time

### Train/Test Split

- Training data: 800 rows
- Test data: 200 rows
- Stratified split

### Model Results

| Model | Accuracy | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| Baseline | 50.0% | — | — | — |
| Logistic Regression | 50.0% | 50.0% | 53.0% | 51.46% |
| Decision Tree | 49.5% | 49.6% | 62.0% | 55.11% |

### ML Conclusion

The leakage-controlled contextual features did not demonstrate meaningful predictive improvement over the 50% baseline.

Therefore, the ML component is treated as a model assessment and negative finding rather than a successful prediction system.

No unsupported claim of predictive success is made.

---

## 14. Application Screens

The application contains six main screens.

### 1. Executive Overview

Provides:

- KPI cards
- Monthly sales trend
- Branch performance
- Product-line performance
- Dynamic observations

### 2. Sales & Trend Analysis

Provides:

- Monthly Sales
- Monthly Gross Income
- Monthly Transactions
- Monthly AOV
- Day-of-week Sales
- Day-of-week AOV
- Time-period Sales
- Time-period Transactions
- Monthly performance table
- Dynamic trend observations

### 3. Driver Analysis

Provides:

- Branch comparison
- Product-line comparison
- Customer-type comparison
- Quantity analysis
- Unit-price-band analysis
- Payment analysis
- Supporting KPIs
- Dynamic observations

The analysis describes observed differences and does not interpret association as causation.

### 4. Risks & Opportunities

Maps:

**Finding → Evidence → Implication → Action → KPI**

### 5. ML Assessment

Displays:

- High-value threshold
- Model comparison
- Leakage controls
- Evaluation metrics
- ML conclusion

### 6. Data & Methodology

Documents:

- Dataset
- Data preparation
- Feature engineering
- KPI definitions
- Analytical methodology
- ML methodology
- Limitations

---

## 15. Interactive Filters

The application provides global filters for:

- Branch
- Product Line
- Customer Type
- Payment
- Month
- Time Period

The filters are connected to the analytical views so that users can explore selected segments.

A reset option is also available.

---

## 16. Application Architecture

The logical application flow is:

**USER → Dashboard/Filters → Frontend Interface → Python Application Logic → Data Processing → Analytics Engine → ML Assessment → Charts/Tables/Insights → USER**

The implementation follows a single-code-file architecture.

Logical sections include:

1. Imports
2. Configuration
3. Data loading
4. Data validation
5. Data preparation
6. KPI calculations
7. Trend analysis
8. Driver analysis
9. Risk/opportunity logic
10. ML assessment
11. UI
12. Error handling
13. Application navigation

---

## 17. Error Handling

The application includes validation and user-facing error states.

### Dataset Error

> Unable to load or validate the dataset. Please verify the data source.

### Empty Filter Result

> No transactions match the selected filters. Please adjust your filters.

### Zero Transactions

AOV is displayed as unavailable when transaction count is zero instead of causing a division-by-zero error.

---

## 18. Technology Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- ipywidgets
- Google Colab / Jupyter Notebook
- GitHub

---

## 19. Installation

Install the required Python libraries:

```bash
pip install pandas numpy scikit-learn matplotlib ipywidgets
```

The project can be executed in Google Colab or another compatible Jupyter environment.

---

## 20. How to Run

1. Open `IBM.ipynb` in Google Colab or Jupyter Notebook.
2. Run the notebook cells in order.
3. Allow the notebook to load the cleaned dataset from the configured Google Sheets CSV source.
4. Execute the application/navigation section.
5. Use the global filters to explore the dashboard.
6. Navigate between the six analytical screens.
7. Review KPI results, trends, drivers, risks, opportunities, and ML assessment.

---

## 21. Quality Assurance

The project was validated through five QA stages.

| QA Area | Result |
|---|---:|
| Data & KPI QA | 11/11 PASS |
| Analysis QA | 15/15 PASS |
| ML QA | 14/14 PASS |
| Application/UI QA | 10/10 PASS |
| Reproducibility & Error Handling QA | 10/10 PASS |

### QA Summary

The validation confirmed:

- Correct row count
- Required base columns
- No missing values in original fields
- Unique Invoice IDs
- KPI reproducibility
- Correct analytical outputs
- ML target and split validation
- Leakage controls
- Application navigation
- Global filters
- Error handling
- Reproducibility

---

## 22. Limitations

1. The dataset contains no persistent customer ID, so customer churn cannot be reliably modeled.
2. Gross Margin % is constant at approximately 4.76%, limiting profitability-driver analysis.
3. The dataset does not contain operating expenses, so Net Profit cannot be calculated.
4. Date coverage is uneven across months, so conventional seasonality claims should not be made from this dataset alone.
5. The ML model uses contextual transaction features and does not use direct transaction-value fields because those would introduce leakage.
6. Observed relationships are associations and should not be interpreted as causal effects without additional evidence.
7. The ML results do not demonstrate meaningful improvement over the balanced baseline.

---

## 23. Business Decision Framework

The project is designed to help management move from descriptive data to action:

**Performance**
→ What is happening?

**Trends**
→ When is it happening?

**Drivers**
→ Where do differences appear?

**Risks & Opportunities**
→ Which areas require attention?

**Actions**
→ What should management review or consider?

**Monitoring**
→ Which KPI should be tracked afterward?

---

## 24. Conclusion

The Supermarket Sales & Profitability Optimization project converts 1,000 supermarket transactions into an interactive analytical decision-support application.

The analysis identifies measurable differences across branches, product lines, customer types, weekdays, time periods, quantities, and unit-price bands. It also translates selected findings into risks, opportunities, recommended review areas, and monitoring KPIs.

The ML assessment found that the available leakage-controlled contextual features did not provide meaningful predictive improvement over the balanced baseline. This result is retained as a valid analytical finding rather than forcing a positive ML conclusion.

Overall, the project follows the decision chain:

**DATA → CLEANING → ANALYSIS → BUSINESS INSIGHT → DECISION → ACTION**

---

## 25. Repository Structure

```text
Supermarket-Sales-Analysis/
│
├── IBM.ipynb
├── requirements.txt
├── README.md
└── Project_Report.docx
```

The final repository should also include any required screenshots/assets only if they are explicitly needed by the submission instructions.

---

## 26. Project Status

The analytical application and QA stages have been completed.

The remaining submission workflow is:

1. Finalize `README.md`
2. Finalize `requirements.txt`
3. Create `Project_Report.docx` or `.pdf`
4. Capture required application screenshots
5. Create/prepare the public GitHub repository
6. Upload the required files
7. Verify repository contents and README rendering
8. Complete the official submission form

