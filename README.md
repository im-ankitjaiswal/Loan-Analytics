# Loan-Analytics
A comprehensive project focused on analyzing loan performance using MySQL for data storage and manipulation, and Power BI for data visualization. The project aims to provide insights into loan portfolios, including analysis of default rates, risk assessment, and performance optimization.

![image](https://github.com/im-ankitjaiswal/Loan-Analytics/blob/main/loan_1.png)
![image](https://github.com/im-ankitjaiswal/Loan-Analytics/blob/main/loan_2.png)
![image](https://github.com/im-ankitjaiswal/Loan-Analytics/blob/main/loan_3.png)



**DAX Measures used in this project**

This section details the DAX measures implemented in the Power BI project for loan portfolio analysis. These measures provide insights into loan application and funding activity, performance ratios, and trends over time.

**Loan Application & Funding:**

* **Total Loan Application:**
    * Formula: `SUM(Loan_Applications[ApplicationCount])`
    * Description: Calculates the total number of loan applications received.
* **Total Funded Amount:**
    * Formula: `SUM(Loans[FundedAmount])`
    * Description: Calculates the total amount of loans that have been funded.
* **Total Amount Received:**
    * Formula: `SUM(Payments[AmountReceived])`
    * Description: Calculates the total amount received from all loan payments.
* **Bad Loan Application:**
    * Formula: `CALCULATE(SUM(Loan_Applications[ApplicationCount]), FILTER(Loan_Applications, Loan_Applications[Status] = "Bad"))`
    * Description: Calculates the number of loan applications classified as "Bad" (e.g., defaulted or delinquent).
* **Good Loan Application:**
    * Formula: `CALCULATE(SUM(Loan_Applications[ApplicationCount]), FILTER(Loan_Applications, Loan_Applications[Status] = "Good"))`
    * Description: Calculates the number of loan applications classified as "Good" (i.e., performing as expected).
* **Bad Loan Funded Amt:**
    * Formula: `CALCULATE(SUM(Loans[FundedAmount]), FILTER(Loans, Loans[Status] = "Bad"))`
    * Description: Calculates the total amount funded for loans that were later classified as "Bad."
* **Good Loan Funded Amt:**
    * Formula: `CALCULATE(SUM(Loans[FundedAmount]), FILTER(Loans, Loans[Status] = "Good"))`
    * Description: Calculates the total amount funded for loans that were later classified as "Good."

**Performance Ratios:**

* **Bad Loan %:**
    * Formula: `DIVIDE([Bad Loan Application], [Total Loan Application])`
    * Description: Calculates the percentage of loan applications classified as "Bad."
* **Good Loan %:**
    * Formula: `DIVIDE([Good Loan Application], [Total Loan Application])`
    * Description: Calculates the percentage of loan applications classified as "Good."
* **Avg Interest Rate:**
    * Formula: `AVERAGE(Loans[InterestRate])`
    * Description: Calculates the average interest rate charged on loans.

**Month-over-Month (MoM) Calculations:**

* **MOM Loan App:**
    * Formula: `CALCULATE([Total Loan Application], DATEADD('Date'[Date], -1, MONTH)) - [Total Loan Application]`
    * Description: Calculates the month-over-month change in the number of loan applications.
* **MOM Total Amt Received:**
    * Formula: `CALCULATE([Total Amt Received], DATEADD('Date'[Date], -1, MONTH)) - [Total Amt Received]`
    * Description: Calculates the month-over-month change in the total amount received from loan payments.
* **MOM Total Funded Amt:**
    * Formula: `CALCULATE([Total Funded Amt], DATEADD('Date'[Date], -1, MONTH)) - [Total Funded Amt]`
    * Description: Calculates the month-over-month change in the total amount of loans funded.
* **MOM Avg Interest Rate:**
    * Formula: `CALCULATE([Avg Interest Rate], DATEADD('Date'[Date], -1, MONTH)) - [Avg Interest Rate]`
    * Description: Calculates the month-over-month change in the average interest rate.

**Other Measures:**

* **Avg DTI:**
    * Formula: `AVERAGE(Applicants[DebtToIncomeRatio])`
    * Description: Calculates the average Debt-to-Income (DTI) ratio of loan applicants.
* **MTD Loan App:**
    * Formula: `CALCULATE([Total Loan Application], DATESMTD('Date'[Date]))`
    * Description: Calculates the number of loan applications received in the month-to-date period.
* **MTD Total Amt Received:**
    * Formula: `CALCULATE([Total Amt Received], DATESMTD('Date'[Date]))`
    * Description: Calculates the total amount received from loan payments in the month-to-date period.
* **MTD Funded Amt:**
    * Formula: `CALCULATE([Total Funded Amt], DATESMTD('Date'[Date]))`
    * Description: Calculates the total amount of loans funded in the month-

