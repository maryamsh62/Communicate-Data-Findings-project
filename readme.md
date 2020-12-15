# Loan Data From Prosper Marketplace Exploration
## by Maryam Shakeri


## Dataset

> [Prosper Marketplace](https://en.wikipedia.org/wiki/Prosper_Marketplace), Inc. was founded in 2005 as the first peer-to-peer lending marketplace in San Francisco, California.
    Through Prosper, people can invest in each other in a way that is financially and socially rewarding. Borrowers apply online for a fixed-rate, fixed-term loan between 2,000 and 40,000. Individuals and institutions can invest in the loans and earn attractive returns. Prosper handles all loans servicing on behalf of the matched borrowers and investors. Prosper Marketplace is backed by leading investors including Sequoia Capital, Francisco Partners, Institutional Venture Partners, and Credit Suisse NEXT Fund (accessed on 11/11/2020, source: https://www.prosper.com/about)

> A small subset of data has been picked from [the origin prosper data](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0) to do some exploration on it. The cleaned subset (df_sub_clean) has *14* columns, and *83982* rows. The columns are *ListingKey*, *ListingCreationDate*, *Term*, *LoanStatus*, *BorrowerAPR*, *ProsperRating (numeric)*, *ListingCategory (numeric)*, *EmploymentStatus*, *CreditScoreRangeLower*, *InquiriesLast6Months*, *IncomeRange*, *StatedMonthlyIncome*, *MonthlyLoanPayment* and *Year_listingCreation* (created column includes the years of the 'ListingCreationDate') for each borrower. 


## Data Wrangling Process:

### Gathering:
Download and save CSV file of data ('prosperLoanData.csv'), then load data into a data frame
### Assessing:
Look through the data frame visually and programmatically
#### Quality issues
- Change the data type of the 'ListingCreationDate' column from the object to datetime.
- Change the data type of the 'Term' column to category.
- Drop null values from these columns: 'CreditScoreRangeLower', 'InquiriesLast6Months', 'ProsperRating (numeric)'.
- Change the data type for 'CreditScoreRangeLower', 'InquiriesLast6Months', 'ProsperRating (numeric)' columns from float to integer.
- Extract the year from the 'ListingCreationDate' column and create a new column for better exploration.
- Change the data type of the new column to category.
- Change the data type of the 'ListingCategory (numeric)' column to category.
- Drop duplicates.

### Cleaning:
Clean the data and do exploration on the cleaned data frame (df_sub_clean)


## Summary of Findings

The results of univariate graphs:

- A vast majority of loans were listed in 2013 with Current loan status.
- Most employed people with an income range of 50,000-74,999 and 25,000-49,999 dollars applied for 36-month loans that most of these applications were for  Debt Consolidation. 

The results of bivariate graphs:

- APRs (the annual cost of a loan to a borrower) were high in 2011 and low in 2014.
- With a higher credit score and fewer inquiries, the amount of Prosper rating increases, and APR reduces.
- The lowest APRs belong to people with an income range of higher than 100,000 dollars and then 75,000-99,999 dollars with Current loan status.
- People with loan status *Chargedoff* and *Defaulted* has The higher APRs.
- The *Current* and *Completed* loans have a higher credit score.
- From 2009 to 2011, most loan status was *completed*. From 2012 to 2014, it was *current*.

The results of multivariate graphs:

- The average of borrower APRs for loan status from 2009 through 2014 shows the highest APRs belong to Chargedoff across the years. Also, the amount of APRs was high in 2011 for all loan status. After 2011, the amount of APR had reduced for all. 
- In 12-month-term loans, the Current and Defaulted have a higher prosper-rating. Generally, most loan status is Completed with an income range of 50,000-74,999 dollars, then 100,000+, 25,000-49,999, and 75,000-99,999 dollars, respectively, which applied loan for Debt Consolidation, Other, Home Improvement, Business, Auto, and Household Expenses.
- In 36-month-term loans, the Current and Chargedoff have a higher prosper-rating. Also, all have a wider distribution compared to the other Terms. Most loan status is Current with income ranges of 50,000-74,999, and then 25,000-49,999 dollars. Most Current and then Completed status applied loan for Debt Consolidation and Other.
- In 60-month-term loans, the Completed, Charged off, and Defaulted loans have the same distribution in prosper-rating. Most loan status is Current with income ranges of 50,000-74,999, and then 25,000-49,999 dollars, which applied loan for Debt Consolidation.
- The graph of APR versus InquiriesLast6Months for Completed and Defaulted loan status shows Defaulted has fewer inquiries with higher APRs. - The graph of APR versus CreditScoreRangLower for Completed and Defaulted loan status displays APR and CreditScoreRangeLower are spread out for both. Most Defaulted has higher APR and less CreditScoreRangeLower compared to Completed one. Both with less CreditScoreRangeLower have higher APRs. By increasing CreditScoreRangeLower, their APRs were reduced.
- From 2009 through 2014, Full-time and Retired people have the lowest APR. APR had been reducing from 2009 through 2014 for Employed and Other people and increasing for Not employed ones. The highest APR was in 2013 for Not employed.
- In 12-month-term loans, Full-time people have a higher prosper-rating. Most employed people by income range of 50,000-74,999 and 100,000+ dollars applied to Debt Consolidation and Business loans.
- In 36-month-term loans, Other people have lower prosper-rating. The Employed, Self-employed and Not employed people have a high one (the Employed and Self-employed distribution is right-skewed and for Not employed, it is left-skewed). Most employed people with an income range of 50,000-74,999 dollars applied to loan for Debt Consolidation.
- In 60-month-term loans, the highest prosper-rating belongs to the Retired people. Most Employed people with an income range of 50,000-74,999 dollars applied to loan for Debt Consolidation.
- The graph of APR versus InquiriesLast6Months for Employed and Not employed people illustrates that Not employed people have fewer inquiries with higher APRs compared to Employed ones. 
- The graph of APR versus CreditScoreRangeLower for Employed and Not employed people displays Most Not employed people have higher APR and less    CreditScoreRangeLower compared to Employed ones. Also, for most Not employed people, their APR did not reduce by increasing their CreditScoreRangeLower.

## Key Insights for Presentation

> The vast majority of people applied for a loan from Prosper Marketplace was Employed (79.3%) with loan status Current and then Completed and Chargedoff, respectively. About 9.4% and 5.3% were Full-time ( loan status Completed) and Self-employed ( loan status Current), respectively.

> Full-time and Retired people had the lowest APR during the years. APR had been reducing from 2009 through 2014 for Employed and Other people and increasing for Not employed ones. The highest APR was in 2013 for Not employed. 

> Most Not employed people have fewer inquiries, higher APR and less CreditScoreRangeLower compared to Employed people. Also, for most Not employed people, their APRs did not reduce by increasing their CreditScoreRangeLower.

> For 12-month-term loans, Full-time people have a higher prosper-rating. 
For 36-month-term loans, the Other has less prosper-rating. The Employed, Self-employed, and Not employed people have higher values (the distribution of prosper-rating for the Employed and Self-employed is right-skewed and for Not employed is left-skewed).
For 60-month-term loans, the highest prosper-rating belongs to the Retired people.

> In all 12, 36, and 60 Terms, most Employed people have an income range of 50,000-74,999 and 25,000-49,999 dollars who applied for loans. Also, in Term 12, most of them that applied for a loan had an income range of 100,000+ dollars.

> The highest APRs belong to the Chargedoff across the years. All loan status had the highest APRs in 2011. After 2011, the amount of APR had reduced for all. 

> Defaulted loans have fewer inquiries with higher APRs compared to Completed loans. It seems that fewer inquiries do not have a strong influence on reducing the amount of APR.
 Most Defaulted loans have higher APR and less CreditScoreRangeLower compared to Completed. Both Completed and Defaulted loans with less CreditScoreRangeLower have higher APRs. By increasing CreditScoreRangeLower, their APRs are reducing.
 
> For 12-month-term loans, the Current and Defaulted loans have higher prosper-ratings. Also, the Current loan is more spread out in the prosper-rating compared to the others. 
For 36-month-term loans, the Current and Chargedoff loans have higher prosper-ratings. 
For 60-month-term loans, as seen, the distribution of prosper-rating is the same for the Completed, Chargedoff, and Defaulted loans.

> Most loans with Term 12 are Completed that have an income range of 50,000-74,999 dollars. Most loans with Term 36 and 60 are Current with an income range of 50,000-74,999, and 25,000-49,999 dollars. In 36-month loans, after the Current, the most is Completed loan with an income range of 25,000-49,999 and 50,000-74,999 dollars.

## Resources

- https://www.prosper.com/
- https://en.wikipedia.org/wiki/Prosper_Marketplace
- http://rstudio-pubs-static.s3.amazonaws.com/454305_3b7d26b7745742c28e15e960ec083214.html#average_loan_amount_for_each_listing_year_vs_loan_status
- https://matplotlib.org/api/pyplot_summary.html#colors-in-matplotlib
- https://stackoverflow.com/questions/21291259/convert-floats-to-ints-in-pandas
- https://stackoverflow.com/questions/55776571/how-to-split-a-date-column-into-separate-day-month-year-column-in-pandas
- https://stackoverflow.com/questions/50319614/count-plot-with-stacked-bars-per-hue/50319805
- https://stackoverflow.com/questions/27037241/changing-the-rotation-of-tick-labels-in-seaborn-heatmap
- https://stackoverflow.com/questions/28638158/seaborn-facetgrid-how-to-leave-proper-space-on-top-for-suptitle
- https://stackoverflow.com/questions/36573789/python-seaborn-facetgrid-change-xlabels
- https://stackoverflow.com/questions/51958177/unable-to-remove-yticks-from-pyplot-subplots
- https://stackoverflow.com/questions/47333227/pandas-valueerror-cannot-convert-float-nan-to-integer
- https://forum.onefourthlabs.com/t/regarding-datatype-dtype-m8-ns/7189
- https://www.geeksforgeeks.org/matplotlib-pyplot-errorbar-in-python/
- https://matplotlib.org/api/_as_gen/matplotlib.pyplot.axis.html?highlight=pyplot%20axis#matplotlib-pyplot-axisplt.axis('square')



