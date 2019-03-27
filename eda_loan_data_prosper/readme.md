# (Prosper Loan Data Analysis)
## by (Arvind Sharma)


## Dataset

This is Exploratory Data Analysis (EDA) on a data set from Prosper, which is America’s first peer-to-peer, or marketplace, lending platform, with over $9 billion in funded loans. This data set contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, borrower employment status, borrower credit history, and the latest payment information.
This [data dictionary](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0) explains the variables in the data set.

The main purposes of this project are to summarize the characteristics of variables that can affect the loan status and to get some ideas about the relationships among multiple variables using data visualizations.

The outline of this project is:
- Introduction
- Univariate Exploration
- Bivariate Exploration
- Multivariate Exploration

### Main feature(s) of interest in the dataset

I'm most interested in understanding about how peer-to-peer, or marketplace lending works for Prosper. Two questions deserve our attention which are as mentioned below:

- What risk factors does Prosper consider before granting loans?
- What are the trends in returns for the granted loans by Prosper?

### I think the below mentioned features will help support investigation into feature(s) of interest

- CreditGrade: The Credit rating that was assigned at the time the listing went live
- Term: The length of the loan expressed in months
- LoanStatus: The current status of the loan: Cancelled,  Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue
- ClosedDate: Closed date is applicable for Cancelled, Completed, Chargedoff and Defaulted loan statuses
- BorrowerAPR: The Borrower's Annual Percentage Rate (APR) for the loan
- BorrowerRate: The Borrower's interest rate for this loan
- EstimatedLoss: Estimated loss is the estimated principal loss on charge-offs.
- ProsperScore: A custom risk score built using historical Prosper data. The score ranges from 1-10, with 10 being the best, or lowest risk score
- ProsperRating (numeric): The  Prosper Rating assigned at the time the listing was created: 0 - N/A, 1 - HR, 2 - E, 3 - D, 4 - C, 5 - B, 6 - A, 7 - AA.
- ListingCategory (numeric): The category of the listing that the borrower selected when posting their listing: 0 - Not Available, 1 - Debt Consolidation, 2 - Home Improvement, 3 - Business, 4 - Personal Loan, 5 - Student Use, 6 - Auto, 7- Other, 8 - Baby&Adoption, 9 - Boat, 10 - Cosmetic Procedure, 11 - Engagement Ring, 12 - Green Loans, 13 - Household Expenses, 14 - Large Purchases, 15 - Medical/Dental, 16 - Motorcycle, 17 - RV, 18 - Taxes, 19 - Vacation, 20 - Wedding Loans
- Occupation: The Occupation selected by the Borrower at the time they created the listing
- IsBorrowerHomeowner: A Borrower will be classified as a homowner if they have a mortgage on their credit profile or provide documentation confirming they are a homeowner
- DebtToIncomeRatio: The debt to income ratio of the borrower at the time the credit profile was pulled. This value is Null if the debt to income ratio is not available. This value is capped at 10.01 (any debt to income ratio larger than 1000% will be returned as 1001%)
- IsBorrowerHomeowner: A Borrower will be classified as a homowner if they have a mortgage on their credit profile or provide documentation confirming they are a homeowner.
- AvailableBankcardCredit: The total available credit via bank card at the time the credit profile was pulled.
- StatedMonthlyIncome: The monthly income the borrower stated at the time the listing was created
- MonthlyLoanPayment: The scheduled monthly loan payment
- LoanOriginalAmount: The origination amount of the loan
- LoanOriginationDate: The date the loan was originated

## Summary of Findings

- 'BorrowAPR' and 'BorrowerRate' have similar distributions with APR rate being higher than the interest rate.
- People mostly take loans from Prosper for debt consolidation, home improvement and business.
- Most monthly loan payment amounts fall under USD 1500 which seems to suggest that most Prosper loans fall under the personal loan category.
- We find that 'C' and 'D' are the most predominant 'CreditGrade' ratings by Prosper.
- The top 3 occupations granted loans by Prosper are 'Computer Programmer', 'Executive' and 'Teacher' respectively.
- There is a negative linear relationship between the features 'ProsperScore' (i.e. risk) and 'BorrowerRate'. It shows that loans with high borrower rate are most common with smaller prosper score (i.e. higher risk values) and loans with relatively low borrower rare are most common with higher prosper score.
- Higher monthly income tend to be identified with higher prosper score (better risk profile), even though there are a few outliers where higher monthly incomes are categorized with low prosper score (high risk profile).
- There is a negative linear relationship between 'AvailableBankcardCredit' and 'BorrowerRate' such that higher values of 'AvailableBankcardCredit' lowers the 'BorrowerRate' values and vice versa.
- Proportion of defaulted loans in the higher rating groups (i.e. 'ProsperRating (Alpha)) such as 'A' and 'AA' are lower in comparison to that in lower rating groups such as 'C', 'D', 'E' and 'HR'.
- Mean of 'MonthlyStatedIncome' for the group of borrowers who have completed their loans is higher than the mean of 'MonthlyStatedIncome' for the defaulting group.
- Borrowers who are also home owners are charged a relatively less borrower rate than those who are not.

To answer the main features of my interest which are the risk factor and trends in return for Prosper I plan to bring in the above observations to my explanatory presentations which contain the features namely 'ProsperRating (numeric)', 'DebtToIncomeRatio', 'BorrowerRate', 'StatedMonthlyIncome', 'LoanStatus' and 'EstimatedLoss'.

## Key Insights for Presentation

- There is a negative linear relationship between the features 'ProsperRating (numeric)' to evaluate risk and 'BorrowerRate'. Loans with high borrower rate are most common with smaller prosper rating (i.e. higher risk values) and vice versa.
- Higher monthly income tend to be identified with higher prosper score (better risk profile).
- There is a negative linear relationship between the features 'AvailableBankcardCredit' and the 'BorrowerRate' such that higher values of 'AvailableBankcardCredit' lowers the 'BorrowerRate' values.
- Lower 'DebtToIncomeRatio' and 'BorrowerRate' are key indicators for a higher Prosper rating i.e. 'ProsperRating (numeric)’.
- 'StatedMonthlyIncome' is a pretty good indicator of safe loans by Prosper.
- As the borrower moves from lower to higher income ranges, Prosper decreases the 'BorrowerRate' making it an important player in the lending market.
- Majority of Prosper loans fall under 36 to 60 months term owing to lower feature value of 'MonthlyLoanPayment' when compared to the 12 month term.
- As the number of recommendations increase the estimated loss shows a marked decrease indicating that Prosper has a good recommendation system at play.
- As the prosper rating increases the estimated loss shows a marked decrease indicating that Prosper has a strong rating mechanism to avoid defaulted or charged off loans which might result in loss. Prosper's success in the peer-to-peer, marketplace lending can attributed to its strong and robust rating system.