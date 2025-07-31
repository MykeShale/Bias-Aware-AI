# Case Study 1: Amazon's Biased Hiring Tool

## Scenario
Amazon developed an AI recruiting tool that showed bias against female candidates.

## Tasks

### 1. Identify the source of bias

The primary source of bias in Amazon's hiring tool was:
- Historical data: The AI was trained on resumes submitted to Amazon over a 10-year period, which were predominantly from male candidates due to male dominance in the tech industry.

### 2. Propose three fixes to make the tool fairer

1. Balanced dataset:
   - Ensure the training data has an equal representation of male and female candidates.
   - If historical data is imbalanced, use techniques like oversampling or synthetic data generation for underrepresented groups.

2. Remove gender-specific features:
   - Identify and remove features that directly or indirectly indicate gender (e.g., pronouns, names of women's colleges).
   - Use blind screening techniques to focus on skills and qualifications rather than demographic information.

3. Implement bias detection and mitigation algorithms:
   - Regularly audit the model's output for gender bias using tools like AI Fairness 360.
   - Apply pre-processing, in-processing, or post-processing techniques to mitigate detected biases.

### 3. Suggest metrics to evaluate fairness post-correction

1. Demographic Parity: Ensure equal selection rates across gender groups.
2. Equal Opportunity: Verify that qualified candidates have equal chances of being selected, regardless of gender.
3. Disparate Impact Ratio: Monitor the ratio of selection rates between gender groups, aiming for a ratio close to 1:1.
4. False Positive/Negative Rate Parity: Check if error rates are consistent across gender groups.
5. Representation Index: Measure how well the selected candidates represent the applicant pool's diversity.