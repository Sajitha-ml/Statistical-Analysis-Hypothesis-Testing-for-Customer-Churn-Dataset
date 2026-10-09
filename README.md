# Statistical-Analysis-Hypothesis-Testing-for-Customer-Churn-Dataset
# Customer Churn Statistical Analysis and Hypothesis Testing

## Project Overview

This project applies statistical analysis and hypothesis testing to a cleaned customer churn dataset containing 10,000 customer records. The objective is to identify statistically significant relationships between customer satisfaction, contract type, and customer churn.

Using Python, three statistical tests were performed to compare customer groups, investigate associations, and evaluate differences in satisfaction scores. Visualizations were created to communicate the results and support data-driven business recommendations.

## Objectives

* Analyze customer satisfaction differences between churned and non-churned customers.
* Investigate the relationship between contract type and customer churn.
* Determine whether average satisfaction differs across contract types.
* Apply statistical hypothesis testing and interpret p-values and effect sizes.
* Communicate findings through clear visualizations and business insights.

## Dataset Description

The cleaned dataset contains **10,000 records and 16 columns**.

| Dataset characteristic        | Details                |
| ----------------------------- | ---------------------- |
| Total customer records        | 10,000                 |
| Customers who did not churn   | 7,740 (77.4%)          |
| Customers who churned         | 2,260 (22.6%)          |
| Missing values after cleaning | 0                      |
| Target variable               | `Churn`                |
| Churn = 0                     | Customer did not churn |
| Churn = 1                     | Customer churned       |

Key variables used in the analysis include `Churn`, `Satisfaction_Score`, and `Contract_Type`.

## Tools and Technologies

* **Python** — statistical analysis and data processing
* **Pandas** — data manipulation
* **NumPy** — numerical calculations
* **SciPy** — statistical hypothesis testing
* **Matplotlib** — data visualization
* **Jupyter Notebook / VS Code** — development environment

## Statistical Methods

### 1. Independent-Samples Welch t-Test

**Research question:** Do average satisfaction scores differ between customers who churned and those who did not?

* Null hypothesis (H₀): The mean satisfaction scores are equal.
* Alternative hypothesis (H₁): The mean satisfaction scores differ.
* Significance level: 0.05

**Results**

| Measure                                     |             Result |
| ------------------------------------------- | -----------------: |
| Mean satisfaction — non-churned             |             6.8833 |
| Mean satisfaction — churned                 |             6.2987 |
| t-statistic                                 |           -20.0563 |
| p-value                                     |     6.6833 × 10⁻⁸⁵ |
| 95% confidence interval for mean difference | [-0.6418, -0.5275] |
| Cohen's d                                   |            -0.4874 |

**Conclusion:** The null hypothesis was rejected. Customers who churned had significantly lower average satisfaction scores than customers who did not churn.

### 2. Chi-Square Test of Independence

**Research question:** Is customer churn associated with contract type?

* Null hypothesis (H₀): Contract type and churn are independent.
* Alternative hypothesis (H₁): Contract type and churn are associated.
* Significance level: 0.05

**Results**

| Contract type  | Total customers | Churned customers | Churn rate |
| -------------- | --------------: | ----------------: | ---------: |
| Month-to-Month |           5,596 |             1,715 |     30.65% |
| One Year       |           2,413 |               354 |     14.67% |
| Two Year       |           1,991 |               191 |      9.59% |

| Measure              |          Result |
| -------------------- | --------------: |
| Chi-square statistic |        486.4445 |
| Degrees of freedom   |               2 |
| p-value              | 2.3438 × 10⁻¹⁰⁶ |
| Cramér's V           |          0.2206 |

**Conclusion:** The null hypothesis was rejected. Contract type was significantly associated with customer churn. Month-to-Month customers had the highest observed churn rate.

### 3. One-Way ANOVA

**Research question:** Does mean satisfaction differ among Month-to-Month, One Year, and Two Year contract customers?

* Null hypothesis (H₀): All three groups have equal mean satisfaction scores.
* Alternative hypothesis (H₁): At least one group has a different mean.
* Significance level: 0.05

**Results**

| Measure                              |   Result |
| ------------------------------------ | -------: |
| Levene's test statistic              |   0.8744 |
| Levene's test p-value                |   0.4171 |
| ANOVA F-statistic                    |   1.9750 |
| ANOVA p-value                        |   0.1388 |
| Eta-squared (η²)                     | 0.000395 |
| Variation explained by contract type |  0.0395% |

**Conclusion:** The null hypothesis was not rejected. There was insufficient statistical evidence of a difference in mean satisfaction across contract types. The eta-squared effect size was negligible.

## Visualizations

The project includes three visualizations:

1. **Customer Satisfaction by Churn Status** — compares satisfaction scores between churned and non-churned customers.
2. **Churn Rate by Contract Type** — highlights differences in observed churn rates across contract groups.
3. **Mean Satisfaction by Contract Type** — compares average satisfaction scores among the three contract groups.

The charts help communicate statistical findings in a clear and accessible way.

## Key Findings

* Churned customers had lower average satisfaction scores than customers who stayed.
* Month-to-Month customers had the highest churn rate at **30.65%**.
* Two Year customers had the lowest churn rate at **9.59%**.
* Contract type was significantly associated with churn.
* Mean satisfaction did not differ significantly across contract types.
* Contract type explained only **0.0395%** of the variation in satisfaction scores in the ANOVA.

## Business Recommendations

* Investigate customer experience issues associated with lower satisfaction and churn.
* Consider targeted retention strategies for Month-to-Month customers.
* Monitor churn rates and satisfaction scores regularly.
* Combine these findings with additional customer characteristics before making retention decisions.

These recommendations are areas for further investigation; the statistical tests do not establish causation.

## Project Structure

A suggested repository structure is:

```text
Customer-Churn-Statistical-Analysis/
│
├── README.md
├── Customer_Churn_Statistical_Analysis_Report.docx
├── customer_churn_analysis.ipynb
├── customer_churn_cleaned.csv
│
└── visualizations/
    ├── satisfaction_by_churn.png
    ├── churn_rate_by_contract.png
    └── satisfaction_by_contract.png
```

*Update the filenames to match the files you actually upload. Do not upload the dataset if you do not have permission to share it.*


## Limitations

* The findings describe statistical associations and differences, not causal relationships.
* Results are based on one dataset and may not generalize to every customer population.
* The chi-square test does not control for other variables that may influence churn.
* Statistical significance does not necessarily imply a large practical effect.

## Conclusion

This project demonstrates the application of statistical hypothesis testing to customer churn analysis. Welch's t-test identified a significant difference in satisfaction between churned and non-churned customers. The chi-square test identified a significant association between contract type and churn. The one-way ANOVA found no statistically significant difference in satisfaction across contract types, with a negligible effect size.

The project strengthens practical skills in Python, statistical analysis, hypothesis testing, data visualization, and translating analytical findings into business insights.
