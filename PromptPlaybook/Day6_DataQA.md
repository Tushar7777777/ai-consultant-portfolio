Prompt 1: Missing Values

Input Prompt:
You are a Data QA Analyst. Review the dataset below and list rows with missing values. Suggest what type of imputation or follow-up is needed.

Customer, Date, Amount
A001, 2024-01-10, 250
A002, , 300
A003, 2024-01-12, 
A004, 2024-01-15, 500


Sample Output:
Rows with missing values:

Row 2 → Missing Date for Customer A002

Row 3 → Missing Amount for Customer A003

Recommendations:

For missing dates → verify with transaction log (manual check needed, as dates are critical).

For missing amounts → impute with average of similar transactions OR request data correction from Finance.

Prompt 2: Outlier Detection

Input Prompt:
You are a Business Data Analyst. Review this dataset and identify anomalies or outliers in sales. Provide possible reasons and how to validate.

Month, Sales
Jan, 100
Feb, 120
Mar, 90
Apr, 1500
May, 110


Sample Output:

Outlier detected: April sales = 1500 (much higher than normal range 90–120).

Possible reasons:

Data entry error (extra zero added).

One-time bulk order.

Special event/seasonal spike.

Validation steps:

Cross-check April sales with order database.

Compare with regional sales breakdown to confirm if valid.

Prompt 3: Format Standardization

Input Prompt:
You are a Data QA Analyst. Check this dataset for inconsistent formats. Suggest a standardized format for dates and revenue, and provide the corrected dataset.

ID, Date, Revenue
C101, 01-02-2024, $200
C102, 2024/02/02, 300 USD
C103, Feb 2, 2024, 250


Sample Output:
Issues identified:

Date formats inconsistent: (DD-MM-YYYY, YYYY/MM/DD, MMM DD, YYYY).

Revenue formats inconsistent: ($200, 300 USD, 250).

Standardization proposal:

Dates → YYYY-MM-DD

Revenue → Numeric (USD)

Corrected dataset:

ID, Date, Revenue(USD)
C101, 2024-02-01, 200
C102, 2024-02-02, 300
C103, 2024-02-02, 250