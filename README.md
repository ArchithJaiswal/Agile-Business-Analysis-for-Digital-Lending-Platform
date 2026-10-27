
**Lending Default Risk Analytics Dashboard**

A 4-page Power BI report that shows where default risk sits in a lending book and which signals actually predict it. Built on the Home Credit Default Risk dataset, with SQL for data preparation and cleaning.

**Business problem**

The lending team wants to understand default risk patterns: which applicant, credit-history and repayment signals separate defaulters, and what a simple policy rule (a credit-to-income cap) would cost in good customers turned away.

**Key findings**
Book size and risk: 308K applicants, 184.21bn exposure, 8.07% default rate, 13.85bn exposure at risk.
Credit history separates risk sharply: high bureau overdue defaults at 36.26% vs 7.62% with none, rising to 40.82% with 2+ prior refusals.
Loan size does not: a credit-to-income cap performs about the same as random rejection (11.07 good customers blocked per default stopped at a 2x cap, 12.55 at 5x, vs 11.39 for random).
Repayment behaviour gives an early warning: applicants who were never late default least, and those late on over half of their instalments default most.
Age shows a pattern: default falls from 12.35% (under 25) to 5.21% (55+). Used to understand the pattern, not as a decision input.

**Report pages**
Page	Focus
1. Lending Portfolio	Exposure, concentration, and a Credit Policy Simulator (what-if slider with a random-rejection baseline)
2. Application Risk Pattern	Default rate and weight of evidence by income type; bureau overdue by prior refusals
3. Credit and Repayment	On-time rate, delay bands, default rate by late-payment frequency
4. Findings and Recommendations	Recommendations by topic: Late Payments, Historical Credit Behaviour, Borrowing Volume, Age Group

**Data and approach**
Source: Home Credit Default Risk (Kaggle) using application_train, bureau, previous_application and installments_payments.
SQL: dropped unneeded columns, aggregated history tables to one row per applicant, removed impossible payment rows, and named blank groups such as "No bureau record".
Power BI: applicant-level data model, DAX measures, bands, a what-if parameter and a dark navy theme.

**Tech stack**

SQL (MySQL), Power BI (DAX, what-if parameters, custom theme), Confluence(Documentation)


**Screenshots**

<h3>Credit Risk Dashboard</h3>

<img width="900" alt="Credit Risk Dashboard Overview" src="https://github.com/user-attachments/assets/d52b8464-ef44-41a1-89a7-1069c1aef6a1" />

<img width="1264" height="716" alt="Screenshot (127)" src="https://github.com/user-attachments/assets/8bfdc3a3-854f-40c5-bb26-36dd3d5511a5" />
<img width="1270" height="716" alt="Screenshot (126)" src="https://github.com/user-attachments/assets/bca23860-cff0-4cd0-a915-6da76126349c" />

<img width="1269" height="714" alt="Screenshot (128)" src="https://github.com/user-attachments/assets/d3a400a5-04f9-43a8-a23a-d81a2f82ffd8" />


Author

Archith Jaiswal
