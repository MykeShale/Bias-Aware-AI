## Summary

### Data Analysis Key Findings

* The COMPAS dataset was successfully loaded from a CSV file hosted online after an attempt to load from a local, empty SQLite database failed.
* The analysis focused on African-American and Caucasian individuals, as these groups are most frequently compared in fairness research on COMPAS.
* Data was preprocessed and formatted into an `aif360.datasets.StandardDataset` object, with 'race' as the protected attribute (Caucasian as privileged) and 'two_year_recid' as the target variable (0 as favorable).
* Several fairness metrics were calculated:
  - **Disparate Impact:** 1.0, indicating no disparate impact in the ratio of favorable outcomes between groups.
  - **Equal Opportunity Difference:** 0.0, suggesting similar true positive rates for both groups.
  - **Average Absolute Odds Difference:** 0.0, indicating overall accuracy is similar across groups.
  - **Theil Index:** ~0.058, showing some inequality in risk score distribution.
* A notable disparity was found in **False Positive Rates**: about 0.28 for African-Americans and 0.47 for Caucasians. This means Caucasian individuals who did not recidivate were more likely to be incorrectly labeled as high-risk compared to African-Americans.
* Visualizations, including bar charts and ROC curves, were generated to illustrate these disparities. The bar chart clearly shows the higher false positive rate for Caucasians, while ROC curves indicate similar predictive performance but different error distributions.

### Insights or Next Steps

* While most fairness metrics suggest equity (Disparate Impact, Equal Opportunity Difference, Average Absolute Odds Difference), the significant disparity in False Positive Rates highlights that the *types* of errors made by the COMPAS tool differ between racial groups. Specifically, Caucasians are more likely to be falsely labeled high-risk.
* This finding suggests that focusing solely on overall fairness metrics can miss important differences in how errors are distributed. It is crucial to consider error types (false positives vs. false negatives) when evaluating fairness.
* Future work should apply post-processing bias mitigation techniques, such as Equalized Odds Postprocessing, to reduce disparities in error rates. Additionally, further investigation into the features used by the COMPAS model may help identify sources of bias and guide improvements for