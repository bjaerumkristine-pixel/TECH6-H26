# Lending Club loan data

This dataset contains information about 10,000 consumer loans issued through
Lending Club, a US lending platform, between January and March 2018. Each row
describes one loan and the applicant's financial situation. We can use these data
to study how loan terms and borrower characteristics relate to interest rates.

## Files

| File | Contents |
| --- | --- |
| `lending_club.csv` | All 10,000 loans, with 19 variables. |
| `lending_club_20pct.csv` | A random subset of 2,000 loans, with the same variables. |

The smaller file contains loans that also appear in the full file. The two files
are alternative versions of the dataset, rather than separate training and test
sets.

## Variables

For interest-rate prediction, `interest_rate` is the outcome and the other 18
variables are potential predictors. Dollar amounts are in US dollars (USD).

| Variable | Meaning |
| --- | --- |
| `interest_rate` | Annual interest rate, in percent. |
| `loan_amount` | Amount borrowed, in USD. |
| `term` | Loan duration: 36 or 60 months. |
| `annual_income` | Applicant's annual income, in USD. |
| `debt_to_income` | Monthly debt payments as a percentage of monthly income. |
| `emp_length` | Completed years in the current job, capped at 10. |
| `homeownership` | Housing status: `RENT`, `MORTGAGE`, or `OWN`. |
| `homeowner` | 1 for `MORTGAGE` or `OWN`; 0 for `RENT`. |
| `verified_income` | Income verification status; see below. |
| `income_verified` | 1 for `Source Verified` or `Verified`; 0 for `Not Verified`. |
| `application_type` | `individual` or `joint` application. |
| `loan_purpose` | Stated purpose of the loan; see below. |
| `credit_history_years` | Loan issue year minus the year of the first credit line. |
| `inquiries_last_12m` | Number of credit inquiries in the preceding 12 months. |
| `open_credit_lines` | Number of open credit accounts. |
| `total_credit_limit` | Existing credit limit excluding mortgages, in USD. |
| `credit_utilization` | Existing credit balance / limit, excluding mortgages. |
| `delinq_2y` | Number of credit-line delinquencies in the preceding two years. |
| `bankruptcy` | Number of bankruptcies listed in the applicant's public record. |

An `interest_rate` of 12 means 12% per year. A `debt_to_income` value of 25 means
monthly debt payments equal 25% of monthly income. `credit_utilization` is a
fraction: 0.5 means 50% of the credit limit is in use. Both the balance and the
limit exclude mortgages, but include more than credit cards. Some reported
utilization values exceed 1.

These two variables describe the applicant's existing credit accounts across
lenders, including accounts outside Lending Club. We interpret them as the
applicant's credit position at application, before the loan in that row is issued.
Utilization describes existing borrowing relative to existing credit limits;
it does not describe subsequent use or repayment of the new loan.

OpenIntro does not explicitly timestamp the underlying balance and limit fields.
The application-time interpretation follows [Lending Club's description of
underwriting][credit-timing], which uses credit-report utilization when assigning
the loan's pricing grade.

A credit line is an account through which someone can borrow, such as a credit
card or loan. A credit inquiry occurs when a lender checks an applicant's credit
history. A delinquency means a payment is overdue. `delinq_2y` and `bankruptcy`
measure different events: overdue payments do not necessarily involve bankruptcy.
`bankruptcy` takes values from 0 to 3 in this dataset, and its definition does not
specify a two-year window.

`verified_income` has three categories: `Not Verified`, `Source Verified`, and
`Verified`. These distinguish whether the lender verified the source of income,
the income amount, or neither. `homeownership` distinguishes renting, owning a
home with a mortgage, and owning a home outright. The two binary indicators
combine categories for exercises using numeric predictors. `income_verified`
means that the source or amount was verified, rather than necessarily both.
The original categorical columns retain the more detailed distinctions.

`loan_purpose` has the categories `car`, `credit_card`, `debt_consolidation`,
`home_improvement`, `house`, `major_purchase`, `medical`, `moving`, `other`,
`renewable_energy`, `small_business`, and `vacation`. Debt consolidation means
combining existing debts into a new loan.

## Interpretation and missing values

The full file contains 8,505 individual and 1,495 joint applications. For joint
applications, `annual_income` and `debt_to_income` describe the individual
applicant, rather than the applicants' combined finances.

In the full file, `emp_length` is missing for 817 loans and `debt_to_income` for 24
loans. `credit_utilization` is missing for two loans with a reported credit limit
of zero. The other variables are complete. Blank entries represent missing
values, rather than zeros. `credit_history_years` measures age at calendar-year
precision, and `emp_length = 10` includes employment lasting more than 10 years.

All observations are loans that were actually issued. The data do not include
rejected applications, so we cannot use them to study loan approval decisions.
The sample covers a short period and does not represent all US borrowers.
Relationships in these data describe associations; they do not establish that
changing a borrower characteristic would cause the interest rate to change.

## Source and license

The original loan records come from Lending Club. This teaching dataset is based
on [OpenIntro's `loans_full_schema` dataset][openintro-data], obtained through the
[Rdatasets collection][rdatasets].
The 10,000 loans constitute OpenIntro's complete teaching sample, a small part of
Lending Club's historical lending records.

The [OpenIntro package][openintro-package]
declares the GNU General Public License, version 3 (GPL-3). This teaching extract
is distributed under the same license; the full terms are in
[LICENSE.txt](LICENSE.txt).

Suggested attribution:

> Lending Club loan data, from OpenIntro's `loans_full_schema` dataset via
> Rdatasets. Teaching extract. Distributed under GPL-3.

[openintro-data]:
  https://openintrostat.github.io/openintro/reference/loans_full_schema.html
[rdatasets]: https://vincentarelbundock.github.io/Rdatasets/
[openintro-package]:
  https://github.com/OpenIntroStat/openintro/blob/master/DESCRIPTION
[credit-timing]:
  https://www.sec.gov/Archives/edgar/data/1409970/000095012311057017/c18482e424b3.htm
