# econ3916-lab17-classification
# Classification: When 90% Accurate Is Worthless

## Objective

In this lab, I used logistic regression to predict loan defaults and explored why high accuracy does not always mean a good model.

## Methodology

- I worked with 6,000 simulated loan applications with a default rate of 9.6%.
- I fitted a logistic regression model and compared its accuracy with a baseline that approves everyone.
- I interpreted the model coefficients using log-odds and odds ratios.
- I tested six different thresholds to compare precision, recall, and accuracy.
- I calculated the costs of false positives and false negatives and selected a threshold that minimized the expected cost.
- I wrote a function called `precision_recall_at()` to calculate precision and recall for any model, dataset, and threshold.

## Key Findings

- The baseline model had 90.4% accuracy by approving everyone.
- At the default threshold of 0.5, logistic regression also had 90.4% accuracy but predicted 0 defaults.
- One more prior default had an odds ratio of 1.63. The probability increased from 2% to 3.2%, from 10% to 15.3%, and from 40% to 52.0%.
- The cost-minimizing threshold was 0.121, close to the closed-form threshold of 0.118.
- At the selected threshold, the expected cost was $944 per applicant, compared with $1,147 at the default threshold of 0.5.
- At the closed-form threshold of 0.118, precision was 0.181 and recall was 0.477.

Overall, I learned that accuracy alone can be misleading when the classes are imbalanced. Choosing a threshold based on the costs of different errors can make the model more useful for real decisions.
