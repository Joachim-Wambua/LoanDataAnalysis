# Part I - Data Exploration of Loan Data from Prosper
## by Joachim Wambua


## Dataset

The Prosper Loan Dataset is a financial dataset with data related to loans and their characteristics such as interest rates, borrower information, lender information and more. The data was sourced from [Prosper Marketplace Inc](https://www.prosper.com/). which is a San Francisco, California based company offering loans at low interest rates to the borrowers. This dataset comprised of 81 variables and contains 113937 loan entries which can provide meaningful insights into the trends and patterns of Prosper's loans.


## Summary of Findings

The exploration performed on Prosper's Loan Data was conducted to give insight into the characteristics of Loans and their borrowers and the feature relationships influence crucial aspects of a Loan.

#### Steps taken in data exploration.
During the initial stages of data exploration the following steps were taken to prepare the data for further exploration and visualisation.
1. Data cleaning for column names for some features of interest such as `ProsperRating (numeric)': "ProsperRating` to more convenient feature names to make analysis more convenient.
2. Data was also cleaned with respect to data types as initial exploration exposed some features that had wrong data types. For example, the features `CreditGrade` & `IncomeRange` were given the object data type while they should have the categorical datatype due to an inherent order in their structure.
3. Initial exploration also exposed missing data for some features of interest such as `CreditGrade` which gave a lot of outliers in some visualisations.
4. The Question-Visualisation-Observation approach was taken in analysing and visualising data to understand its underlying trends and patterns.


#### Data Exploration Findings:

1. What is the frequency distribution for Borrowers' Annual Percentage Rates(BorrowerAPR) in the Prosper Loan Dataset?

The univariate distribution for the `BorrowerAPR` (Annual Percentage Rate) feature demonstrated a multimodal structure with multiple number of peaks. Across the distribution of Borrowers' Annual Percentage Rate, `BorrowerAPR`. There are peaks observed at around x = 0.09, x = 0.2, x = 0.3 and x = 0.35. A majority of the loans in this dataset have a Borrower's APR Greater than 0.1% but less than 0.3%.I do not intend to carry this finding forward into the explanatory analysis


2. What is the most frequent EmploymentStatus in the dataset?

Having investigated the `EmployementStatus` distribution for Prosper's borrowers, I found that a vast majority of loan borrowers(67322) in the dataset were employed at the time of acquiring the loan, with Full-Time employment following in second with 26355 of the borrowers and in a distant third, 6134 Self-Employed Borrowers. This shows that most Prosper loan borrowers are employed. I do not intend to carry this finding forward into the explanatory analysis


3. What is the most preferred loan duration (Term) among borrowers based on the dataset?

77.04% of Loan Borrowers preffered middle term, __3 Year Loans(36 Months)__ making up __87753(77.04%)__ loan listings. followed by __5 Year__ (60 Month) loan spells with __24545(21.55%) listings__ and lastly __1 Year__ (12 Month) loan spells has __1614(1.42%)__ loan listings. Most Prosper Loanees perfer mid-long term loans. I do not intend to carry this finding forward into the explanatory analysis.


4. What is the distribution of StatedMonthlyIncome for Prosper's Loan Borrowers?

The univariate distribution visualization for the numerical feature `StatedMonthlyIncome` showed that most Loan Borrowers earn less than 10000 with majority of Borrowers earning between 3000 and 6000 as Monthly earnings. The most outrageous borrower earns about a million units with about 1,750,003 units. I do not intend to carry this finding forward into the explanatory analysis.


5. What are the most dominant Loan Statuses for Prosper's Loan Listings?

The status of most Loans(`LoanStatus`) at Prosper were (Current Loans with 56576 listings) followed closely by 38049 Completed Loan listings that were fully paid off. 11992 Loan Listings were Charged Off meaning that the lendor(Propser) considered these loans uncollectable for various reasons such as an agreement not to collect an amount, an account being many months past due, or failure to perform a settlement agreement. There were 5018 Loan Defaulters who did not pay their Loans. Most Loan Borrowers who Paid their loans when after were past due often paid within two weeks(1-15 days) after the Loan's due date. I do not intend to carry this finding forward into the explanatory analysis.


6. What is the distribution of IncomeRange for Prospers' borrowers?

A majority of the borrowers making up __28.26% (32192)__ borrowers earn between 25,000-49,999 USD, followed closely by borrowers earning between 50,000-74,999 USD making up __27.26%(31050)__ of available loan listings and those earning +100,000 USD making up __15.22%(17337)__. This implies that a vast majority of loan borrowers at Prosper are Middle to High Income Earners. I do not intend to carry this finding forward into the explanatory analysis


7. What are the pairwise correlations for the numeric features of interest in this dataset?

Positive correlations were notice between the following variables based on the correlation heatmap; `BorrowerAPR` & `BorrowerRate` = 0.990, `BorrowerAPR` & `EstimatedLoss` = 0.950, `BorrowerRate` & `EstimatedLoss` = 0.0.945, `BorrowerRate` & `EstimatedReturn` = 0.818, `EstimatedReturn` & `EstimatedLoss` = 0.591. On the other hand, negative correlations were noticed between; `BorrowerAPR` & `ProsperScore` = -0.668, `EstimatedLoss` & `ProsperScore` = -0.674, `BorrowerRate` & `ProsperScore` = -0.650. I intend to carry this finding forward into the explanatory analysis.


8. Does a Loan Borrower's Interest Rate have any impact on the Loan's Estimated Returns?

An investigation on the relationship between a Loan's `BorrowerRate` & `EstimatedReturn` also depicted a positive correlation as data points were closely clustered together creating a slope that increases as values of the x and y axes increase. A line of best fit was also added to this visualisation to show the general trend of the data points which is generally positive. This means the higher a Loan's Borrower Interest Rate, the higher the Estimated Returns. I do not intend to carry this finding forward into the explanatory analysis


9. How does a borrower's IncomeRange & CreditGrade affect their loans' interest rates(BorrowerRate)?

- BorrowerRate vs CreditGrade.
When comparing numerical variable `BorrowerRate` vs categorical variable `CreditGrade` on a boxplot, the medians and inter-quartile ranges for BorrowerRate reduced as CreditGrades moved towards higher Credit Score classes (HR - AA). The Median values of `BorrowerRate` also decrease from Class HR through Class AA. This could mean that the Borrower Interest Rates are usually lower for higher ranked `CreditGrade` classes. I intend to carry this finding forward into the explanatory analysis

-  BorrowerRate vs IncomeRange
A general trend noticed from the visualisaton to the top left is that The median BorrowerRate(Interest Rate) decreases as a borrower's Income Range increases. Loan Borrowers under the IncomeRange category, 'Not Employed' have the highest BorrowerRate median while this value keeps on decreasing across Income Ranges '1−24,999' to '100,000+'. The '$0' IncomeRangecategory has outliers beyond the maximum value which should be handled before explanatory analysis. The inter-quartile ranges across the IncomeRange categories. I do not intend to carry this finding forward into the explanatory analysis

10. What was the distibution of loan listings amongst the different classes in CreditGrade & LoanStatus for each unique EmploymentStatus class?

a. Frequency of loan listings by EmploymentStatus and CreditGrade.
Amongst full-time employees, the majority of this sample population were under CreditGrade C, followed by CreditGrade D then CreditGrade B. This illustrate that many of Prospers' borrowers who are employed full-time are often part of CreditGrade D and above(C, B, A, AA). Amongst the population of self employed borrowers, majority of borrowers are part of CreditGrade C and above. For borrowers who did not provide their EmploymentStatus information, most of them were in the lower CreditGrade classes HR, E and D. The 'Employed' status has no values plotted in it which is rather strange and could mean missing CreditGrade values for the 'Employed' Employment Status. I do not intend to carry this finding forward into the explanatory analysis

b. Frequency of loan listings by EmploymentStatus and LoanStatus.
This visualisation showed that amongst Employed borrowers, a great majority have active/Current Loans meaning their loans are active with the second-most populated category as Completed meaning borrowers had completed their loan payments. As for borrowers with Full-Time employment most of them had completed their Loan Payments with the second most populated group in this category(Full-Time borrowers) being those whose loans were CharedOff meaning the bank considered those loans uncollectable. I do not intend to carry this finding forward into the explanatory analysis


11. How does a Borrower's ProsperRating influence their Borrower's Interest Rates and Borrower's annual percentage rates?

Having established the strong positive correlation between `BorrowerRate` & `BorrowerAPR`, a third variable, Term/Loan duration, was introduced to investigate whether Loan Durations may have an impact on Loan Rates. The trend observed in the data implied that the longer the duration(Term) of the loan, the lower the interest and annual percentage rates tend to become., Longer Term Loans rend to have lower interest & annual percentage rates between 0.05% to just over 0.15% followed by Middle Term Loans which have interest & annual percentage rates between just over 0.15% to about 0.32%. Short Term Loans tend to have higher interest & annual percentage rates between 0.32% to just over 0.40%.

12. What are the pairwise correlations for Numeric features; 'LoanOriginalAmount', 'StatedMonthlyIncome', 'BorrowerRate', 'BorrowerAPR', 'Term', 'ProsperRating', 'TotalProsperLoans' and which features have strong correlations?

Interesting relationships were observed which I intend to carry forward into the explanatory explanation. The relationships include;

        - `ProsperRating` vs `LoanOriginalAmount`: Borrowers with lower prosper rating(numerical for of ranking CreditScores) often take Loans lower than 10,000 units. As a Borrower's Prosper Rating Increases, then they are more likely to acquire greater Loan Amounts. This shows that their is a positive correlation between the features `ProsperRating` vs `LoanOriginalAmount`. There is a point of interest in this visualisation between ProsperRating A and AA when the data trend depicts a slight negative correlation, this might be worth investigating further.

        - `ProsperRating` vs `BorrowerAPR` & `BorrowerRate`: Loan Borrowers with higher Prosper Ratings(Credit Scores) often received lower annual interest rates(BorrowerAPR) & Interest Rates (BorrowerRate) in comparison to those with Lower ProsperRatings(Credit Scores) who often get higher Interest Rates(BorrowerAPR & BorrowerRate). This means that these features exhibit a negative correlation meaning that the Higher a borrower's ProsperRating (Credit Score), the higher their Borrower's Annual Percentage Rate.

        - `LoanOriginalAmount` & `BorrowerRate` and `BorrowerAPR` - These features exhibit a negative correlation As a borrower's borrowed LoanOriginalAmount increases, their Borrower Interest Rates & Annual Percentage rate often tend to decrease. This means that loans of higher amounts usually get higher Interest Rates.


## Key Insights for Presentation

During the analysis and visualization of Prosper's Loan Data, I found it imperative to evaluate the stand-out features that offered meaningful insight into the trends and patterns in the data. 

1. Features `CreditGrade` & `BorrowerRate` gave great insight into how a Loan borrower's Credit Score/ `CreditGrade` could impact their Loan's interest rates. These features exhibited a negative correlation as it was observed that the higher a borrower's Credit Score the lower the interest rates they receive in their loans.

2. The features `LoanOriginalAmount` & `BorrowerRate` also exhibited a negative correlation as I found that higher borrower Loan Amounts mean that users received lower interest rates on their loans. Borrowers of higher amounts from Prosper often get the best/lowest interest rates.

3. There is evidence of positive correlation between the features `ProsperRating` which is a numerical format of the Credit Score rating and `LoanOriginalAmount` as borrowers with higher CreditScores/ ProsperRatings often borrowed large amounts of money compared to their lower rated counterparts.