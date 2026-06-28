🔍 Bank Reconciliation Automation using Python

🔍 Project Overview

This project automates the reconciliation process between a company cashbook and bank statement using Python and Pandas.

The objective was to transform unstructured accounting records into a standardized reconciliation process capable of:
•	Matching transactions between two independent ledgers.
•	Identifying unreconciled transactions.
•	Detecting duplicate entries.
•	Producing audit-ready exception reports.
•	Generating reconciliation summaries.

The project simulates a real-world Bank Reconciliation Statement (BRS) process performed by finance and operations teams.
________________________________________

🔍 Business Problem

Organizations maintain two separate records of cash transactions:
  ✅ Internal Cashbook
  ✅ External Bank Statement

Differences often arise because of:

•	Outstanding cheques
•	Delayed bank postings
•	Bank charges
•	Missing entries
•	Timing differences
•	Duplicate transactions

Manual reconciliation is time-consuming and prone to error.

The objective was to automate the identification of exceptions while maintaining audit transparency.
________________________________________

🔍 Dataset

📌 Source file: Bank Reconciliation Sample.xlsx(kaggle)

The workbook contains:

📌 Company Cashbook
•	Parallel Debit and Credit sections.
•	Merged header cells.
•	Embedded opening and closing balances.
•	Non-standard structure.

📌 Bank Statement
•	Debit and Credit columns.
•	Running balance.
•	Verbose transaction descriptions.
•	Embedded cheque numbers.

📌 Manual W-1 and W-2 Schedules

📌 Summary Used for validation of reconciliation results.
________________________________________

🔍 Data Challenges

Several issues prevented direct reconciliation:

Issue	Impact
Merged cells	Difficult to parse
Duplicate headers	Column ambiguity
Different transaction descriptions	Matching failures
E  mbedded cheque numbers	Hidden matching keys
Balance rows inside transactions	False entries
Duplicate transactions	Audit concerns
________________________________________

🔍 Data Transformation

📌 Cashbook
•	Skipped merged headers.
•	Split Debit and Credit sections.
•	Converted to tidy format.
•	Standardized dates and amounts.
•	Extracted cheque numbers.

📌 Bank Statement
•	Removed unnecessary balance fields.
•	Standardized transaction records.
•	Extracted reference numbers.

📌 Final structure:
Date	Details	Amount	Type	ChequeNo
________________________________________

🔍 Reconciliation Logic

Transactions were reconciled using:
•	Amount
•	Cheque Number
•	Transaction Type

Cheque numbers proved to be the most reliable matching key because transaction descriptions differed significantly between the two ledgers.

Examples:
Cashbook	Bank Statement
Electricity - 7864	Electricity Bill Cheque #0007864
Mr. Ali - 7981	Receipt Cheque 7981
________________________________________

🔍 Output Generated

The automation produces the following sheets:

  Sheet	                      Purpose
Cashbook	              Cleaned cashbook data
Bank Statement	        Cleaned bank data
W-1	Bank                transactions not in cashbook
W-2	Cashbook            transactions not in bank
Cashbook Duplicates	    Duplicate cashbook records
Bank Duplicates	        Duplicate bank records
Summary	                Reconciliation metrics
________________________________________

🔍 Key Findings

✔	Direct text matching produced inflated mismatches.
✔	Cheque numbers were the actual business key.
✔	Duplicate transactions must be flagged rather than removed.
✔	Debit and Credit logic required careful treatment to avoid incorrect balances.
✔	Data normalization significantly improved reconciliation accuracy.
________________________________________

🔍 Challenges Solved

✅ Restructured non-tabular accounting data.
✅ Extracted hidden reference numbers.
✅ Standardized inconsistent transaction descriptions.
✅ Created automated mismatch schedules.
✅ Produced audit-ready duplicate reports.
✅ Generated reconciliation summaries.
________________________________________

🔍 Technologies Used
✔	Python
✔	Pandas
✔	OpenPyXL
✔	Jupyter Notebook
✔	Excel
________________________________________

🔍 Skills Demonstrated

✔	Financial Data Analysis
✔	Data Cleaning
✔	Data Transformation
✔	Reconciliation Automation
✔	Exception Reporting
✔	Process Automation
✔	Audit Analytics
✔	Python for Finance
________________________________________

🔍 Future Enhancements

✔	Fuzzy text matching.
✔	Date tolerance matching.
✔	Match confidence scores.
✔	Automated categorization of exceptions.
✔	Interactive Power BI reconciliation dashboard.
✔	Machine learning-based transaction matching.
________________________________________

🔍 Business Impact

This solution demonstrates how data engineering and analytics can automate traditionally manual finance processes, 
improve reconciliation accuracy, and support audit transparency.

The project highlights the importance of data normalization and exception management in financial operations.
