# A/B Testing Analytics and Statistical Evaluation

## Project Overview

This project investigates whether a redesigned e-commerce landing page improves user sign-up conversion compared with an existing landing page.

Using A/B testing techniques, the analysis evaluates the performance of two experimental groups, applies statistical hypothesis testing and translates the findings into actionable business recommendations.

## Business Problem

An e-commerce company introduced a redesigned landing page with the intention of increasing user sign-ups. However, the company needs evidence to determine whether the new design performs better than the existing version.

The main business question is:

**Does the redesigned landing page increase the proportion of website visitors who sign up compared with the existing landing page?**

## Project Objectives

- Assess and prepare the experimental dataset for analysis.
- Investigate data quality issues, including repeated user records and inconsistent group-page assignments.
- Compare visitor distribution and conversion performance between experimental groups.
- Calculate conversion rates and examine daily performance trends.
- Conduct statistical hypothesis testing to determine whether the observed difference is statistically significant.
- Calculate a 95% confidence interval for the difference in conversion rates.
- Develop evidence-based business recommendations.

## Dataset Description

The dataset contains experimental observations for users assigned to either the control or treatment group.

| Column | Description |
|---|---|
| `USER_ID` | Unique identifier assigned to a user |
| `TIMESTAMP` | Date and time of the recorded observation |
| `GROUP` | Experimental group: control or treatment |
| `LANDING_PAGE` | Landing page recorded for the user: old_page or new_page |
| `CONVERTED` | Binary conversion outcome: 1 = converted, 0 = not converted |

The original dataset contained 294,478 records.

Following data quality assessment and the exclusion of all records belonging to repeated users, the cleaned analytical dataset contained 286,690 records.

## Methodology

The project followed these analytical stages:

1. **Data Understanding and Quality Assessment:** Examined dataset structure, data types, missing values, duplicate records and inconsistencies between experimental groups and landing pages.

2. **Data Cleaning:** Investigated repeated user records and excluded users with multiple observations from the primary analysis.

3. **Exploratory Data Analysis:** Examined experimental group distribution, conversion counts and conversion rates.

4. **Statistical Hypothesis Testing:** Applied a two-proportion z-test to determine whether the difference in conversion rates was statistically significant.

5. **Confidence Interval Estimation:** Calculated a 95% confidence interval to assess the plausible range of the difference in conversion rates.

6. **Time-Based Analysis:** Compared daily conversion rates, daily performance differences and visitor distribution throughout the experiment.

7. **Business Recommendations:** Interpreted the findings and developed recommendations based on the statistical evidence.

## Key Findings

| Metric | Result |
|---|---:|
| Control conversion rate | 12.02% |
| Treatment conversion rate | 11.87% |
| Difference (Treatment - Control) | -0.1447 percentage points |
| Z-statistic | -1.1945 |
| P-value | 0.2323 |
| Significance level | 0.05 |
| 95% Confidence Interval | [-0.3821, 0.0927] percentage points |

### Statistical Conclusion

The p-value of 0.2323 exceeds the significance level of 0.05. Therefore, the null hypothesis was not rejected.

The 95% confidence interval also includes zero, indicating insufficient statistical evidence to establish a difference in population conversion rates between the two landing pages.

The existing landing page recorded a slightly higher observed conversion rate than the redesigned page.

### Business Recommendation

The company should retain the existing landing page for now rather than immediately adopting the redesigned version.

Further experimentation and evaluation of the redesigned page are recommended before making an implementation decision.

## Tools and Technologies

- **Python** – Data analysis and statistical computation.
- **Pandas** – Data manipulation and preparation.
- **NumPy** – Numerical operations.
- **Matplotlib** – Data visualisation.
- **Seaborn** – Statistical visualisation.
- **Statsmodels** – Statistical hypothesis testing and confidence interval estimation.
- **Google Colab** – Notebook development and execution.

## Repository Structure

```text
ab-testing-analytics/
│
├── AB_Testing_Analysis.ipynb
├── README.md
│
└── data/
    └── README.md
```

The dataset is not included in this repository. Refer to the notebook and dataset instructions for information on obtaining and loading the data.

## How to Run the Project

The analysis was developed in Google Colab.

1. Clone or download this repository.
2. Open `AB_Testing_Analysis.ipynb` in Google Colab.
3. Obtain the original dataset and upload `ab_data.xlsx` to the Colab session.
4. Execute the notebook cells sequentially to reproduce the analysis.

The notebook contains the complete workflow, including code, explanations, statistical results and visualisations.

## Project Scope and Limitations

- The analysis is based on the available experimental dataset and its recorded variables.
- Repeated user records were excluded from the primary analysis because their multiple observations made it difficult to establish a reliable experimental exposure for each user.
- Excluding repeated users may introduce selection bias if their occurrence was not random.
- The dataset does not contain device or demographic information, so device-based and demographic segmentation was outside the scope of this investigation.
- The exact conversion event is not explicitly defined in the dataset documentation; sign-up conversion is the interpretation adopted for this project.
- The findings do not establish that the two landing pages perform identically. They indicate that the experiment did not provide sufficient evidence of a statistically significant difference.

## Conclusion

This project demonstrates the application of data analytics and statistical testing to evaluate an A/B experiment and support evidence-based business decisions.

It combines data preparation, exploratory analysis, statistical inference, visualisation and business interpretation to assess whether a product change delivers measurable improvement.
