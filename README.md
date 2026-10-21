# Causal Impact of PMJDY on Formal and Informal Borrowing in India

An econometric study of whether the **Pradhan Mantri Jan Dhan Yojana (PMJDY)**—launched in 2014 to expand banking access—changed formal and informal borrowing in India.

The project combines NSSO's All India Debt and Investment Survey (AIDIS) with Census population statistics and PMJDY beneficiary counts to evaluate whether greater banking access translated into greater use of formal credit.

## Research question

Did districts in states with higher initial PMJDY implementation intensity experience a greater increase in formal borrowing and a decrease in informal borrowing after the scheme began, especially in predominantly rural districts?

## Data

- **AIDIS / NSSO survey rounds:** 2003, 2013 and 2019. The 2003 round is used for pre-treatment trend checks; 2013 and 2019 form the main pre/post comparison.
- **2011 Census:** State population counts used to normalize PMJDY beneficiaries.
- **PMJDY administrative records:** State-level beneficiary totals used to define implementation intensity.

The analysis focuses on **new loan amounts** reported in the reference years, rather than outstanding debt stocks. Survey records are cleaned, matched and aggregated to the district level; formal and informal credit sources are classified from the survey's lender categories. States are categorized as high or low intensity using the median beneficiary-to-population ratio (approximately **22%**).

**Unit of analysis:** District-level observations, with districts classified as predominantly rural or urban using their sampled rural-household share. The main 2013–2019 regressions use **1,253 observations**.

## Methodology

The analysis first examines aggregate borrowing trends and differences between high- and low-intensity states. Since a conventional difference-in-differences comparison has problematic pre-treatment trends, the main specification uses **difference-in-difference-in-differences (DDD)**:

- Before versus after PMJDY (2013 versus 2019)
- High- versus low-intensity states
- Predominantly rural versus urban districts

The model includes state and year fixed effects and estimates **state-clustered standard errors**. It also checks pre-treatment patterns with the 2003–2013 data and conducts placebo tests using a randomly assigned pseudo-treatment among low-intensity states and a demographic outcome (average household size).

## Main findings

| Outcome | DDD estimate | p-value | Interpretation |
| --- | ---: | ---: | --- |
| Formal borrowing | +₹76.61 lakh | 0.121 | Positive estimate, not statistically significant at the 5% level |
| Informal borrowing | −₹5.60 lakh | 0.354 | Negative estimate, not statistically significant at the 5% level |

The formal-credit pre-trend check was statistically insignificant (**p = 0.696**); the household-size placebo was also insignificant (**p = 0.615**). These results are consistent with the research design's assumptions but do not prove them.

**Takeaway:** The analysis does not find statistically significant evidence that higher PMJDY rollout intensity shifted district-level new borrowing from informal to formal sources during the study period. Expanding access to bank accounts does not necessarily imply immediate growth in formal credit usage.

## Repository contents

- `Analysis.ipynb` — Data preparation, descriptive statistics, DDD estimation, and robustness checks.
- `Report.pdf` — Research motivation, identification strategy, findings, limitations and references.

> The notebook currently references **absolute local file paths** for source CSVs. To reproduce the results, obtain the relevant survey and administrative datasets, update the paths in the notebook, and run the cells in order. These source files are not included in this README.

## Tools

Python, Pandas, NumPy, SciPy, Statsmodels, Matplotlib, Jupyter Notebook.

## Limitations

District-level borrowing totals may conceal effects on loan counts or smaller borrowers. The high/low treatment split uses an early snapshot of PMJDY intensity; later implementation may differ. The DDD interpretation relies on parallel trends in **rural–urban differences** across intensity groups, along with other identification assumptions. Statistically insignificant tests do not establish those assumptions conclusively.
