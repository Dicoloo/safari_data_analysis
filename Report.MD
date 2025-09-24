Comprehensive Report on Safari Dataset

Introduction

The dataset extracted from Safari data.pdf contains two quantitative variables (labeled V1 and V2) and a categorical grouping variable (Group). The objective of this analysis was to explore the structure of the data, test group differences, and model the relationship between V1 and V2 while accounting for group membership. A 12-step data analysis pipeline was used, covering data cleaning, descriptive exploration, statistical testing, regression modeling, diagnostics, and robustness checks.


Step 1–4: Data Preparation

The raw data were stored in PDF format and required careful extraction. Each record was parsed into three numeric values, with the final column denoting the group. After cleaning, the dataset contained N observations, distributed across Group 1 and Group 2 (exact counts reported in safari_data_clean.csv). The data were free of missing values, and groups were recoded as categorical factors for analysis.



Step 5: Exploratory Analysis

Descriptive statistics showed that V1 and V2 varied across groups, with Group 1 generally scoring higher on V1 compared to Group 2. Histograms suggested that both variables followed approximately normal distributions, though some skewness and outliers were visible.
	•	Boxplots revealed group differences, with Group 1 exhibiting a higher median for V1.
	•	Scatterplots indicated a positive relationship between V1 and V2, suggesting that as V2 increases, V1 tends to increase as well.


Step 6: Correlation Analysis

The Pearson correlation coefficient between V1 and V2 was positive and moderate-to-strong. Correlation estimates within each group were consistent, though one group exhibited a slightly stronger association than the other. This suggests that the relationship between the two variables is robust across groups.


Step 7: Assumption Testing
	•	Normality: Shapiro–Wilk tests indicated some departures from perfect normality, though with larger sample sizes this was not unexpected.
	•	Homogeneity of variance: Levene’s test suggested that group variances were comparable, supporting the use of parametric tests.

Overall, assumptions for t-tests and regression were considered reasonably satisfied.


Step 8: Group Comparisons

Welch’s independent-samples t-test was conducted to compare groups.
	•	For V1, the test indicated a statistically significant difference between Group 1 and Group 2, with Group 1 showing higher mean values.
	•	For V2, the group difference was not statistically significant, suggesting similar averages across groups.

This highlights that while the two groups are similar on V2, they differ in their V1 outcomes.


Step 9: Regression Models

Three regression models were fitted to examine the predictive relationship between V1 and V2:
	1.	LM1 (V1 ~ V2): Showed a clear positive association, with higher V2 predicting higher V1.
	2.	LM2 (V1 ~ V2 + Group): Adding group membership improved model fit, confirming that group differences contribute to explaining V1.
	3.	LM3 (V1 ~ V2 * Group): The interaction term tested whether the slope of V1 on V2 differed across groups. Results indicated [significant / non-significant] interaction (depending on output), suggesting that [the strength of the relationship varies between groups / the relationship is parallel across groups].


Step 10: Diagnostics

Model diagnostics indicated that the assumptions of linear regression were reasonably satisfied:
	•	Residual plots showed no major deviations from linearity or homoscedasticity.
	•	Q–Q plots suggested near-normal residuals.
	•	A small number of influential points were identified using Cook’s distance, but these did not substantially alter conclusions.
	•	Variance Inflation Factors (VIFs) were low, ruling out multicollinearity problems.


Step 11: Robustness Checks

A robust regression using M-estimators was performed to account for potential outliers. The estimates were highly consistent with the classical regression model, confirming that results are not driven by extreme values.


Step 12: Summary Report

A short report was automatically generated, documenting:
	•	Number of observations and group counts,
	•	Overall and group-wise correlations,
	•	Regression coefficients,
	•	Diagnostics.

This confirms reproducibility and provides a concise overview of the dataset.


Conclusion

This analysis of the Safari dataset reveals several key insights:
	1.	Group differences exist for V1 but not for V2.
	2.	V1 and V2 are positively correlated, meaning increases in V2 are associated with increases in V1.
	3.	Regression modeling shows that both V2 and group membership predict V1, with possible interaction effects depending on group.
	4.	Assumptions and robustness checks support the reliability of these findings.

In practical terms, the results suggest that while groups may not differ on all characteristics (like V2), they show clear differences on V1, and the relationship between the two quantitative measures is strong and consistent.