# ML + Product Exercise: Churn Prediction as a PM

## Business Context

You are a Product Manager at TeamFlow, a subscription-based SaaS platform.

**Goal**

Predict whether a user will churn in the next 30 days so the marketing team can take action.

**Business Constraints**

* Missing a churned user (False Negative) is very costly
* Contacting a non-churn user (False Positive) is cheap
* Model must be explainable to stakeholders

---

## Dataset Description

**Company Overview**

TeamFlow is a subscription-based SaaS platform that helps teams collaborate on projects.
TeamFlow sells individual and premium subscriptions, and earns revenue from recurring monthly payments.

The company wants to predict churn (that is, which users are likely to cancel their subscription in the next 30 days) so that the growth and marketing teams can proactively engage at-risk customers with retention offers.

To do this, they have collected behavioural and support data from current and past users. Your team will build and evaluate simple ML models (e.g., logistic regression, KNN, decision trees) to forecast churn, while making product trade-offs.

### Feature Explanations

Below is a breakdown of each feature in the dataset, expressed in business terms. The **Description** is what the column measures; the **Product context** is why it might matter for churn.

| Feature               | Description                                                                       | Product context                                                                                   |
| --------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `tenure_months`     | Number of months the user has been active on the platform.                        | How long the user has been exposed to the product and how embedded it may be in their workflow.   |
| `sessions_per_week` | Average number of times the user accesses the product in a typical week.          | A proxy for engagement and how regularly the product is part of the user's routine.               |
| `feature_usage`     | Count of distinct product features the user has interacted with.                  | The breadth of the product the user has explored, not how well they used any single feature.      |
| `support_tickets`   | Total number of customer support tickets raised by the user.                      | Moments where users needed help, clarification, or resolution.                                    |
| `is_premium`        | Whether the user is on a paid plan:`1` = Premium (paid), `0` = Free or basic. | Subscription tier reflects the level of commitment and investment a user has made in the product. |

---

### Target Variable: `churn`

**Description:** Whether the user cancelled or stopped using the product within the defined time window.

- `1` → User churned
- `0` → User retained

---

## From the company's perspective

* Predicting churn allows proactive retention
* Saves marketing spend by targeting only high-risk users
* Improves customer experience by personalising engagement
* Helps PMs understand behavioural drivers of churn

---

### Important Note

- Feature descriptions provide **business context only**
- They do **not** imply how strongly a feature affects churn
- Your models and evaluation metrics should reveal those relationships
- This is intentionally a small dataset: our goal is to practice PM decisions, metric trade-offs, and risk assessment, not to build a production-grade model.

---

## Your Task

Work through the analysis in `02_churn_prediction.ipynb`, then answer the reflection questions below.

1. Load the dataset from `data/synthetic_customer_churn.csv` and explore it: check the class balance, the feature distributions, and how each feature relates to `churn`.
2. Prepare the data: separate the features from the target and split them into training and test sets. Apply scaling where a model needs it.
3. Train different models, like logistic regression, KNN, and a decision tree.
4. Evaluate each model on the test set. Report recall, precision, and F1, and inspect the confusion matrix so you can see the false negatives and false positives.
5. Compare the models against the business constraints above, and pick the one you would recommend.
6. Answer the reflection questions, framing each answer from a product perspective.

---

## Post-Exercise Reflection Questions

### Model Choice & Business Fit

1. Which model would you recommend deploying for TeamFlow and **why**?
2. Which business constraint mattered most in your decision:recall, explainability, or false-positive cost?
3. Would your recommendation change if TeamFlow were an early-stage startup vs a mature company? Why?

### Metrics & Trade-offs

4. Which evaluation metric did you prioritise and why?
5. What are the **real business consequences** of:
   - a false negative in this problem?
   - a false positive?
6. If leadership demanded higher accuracy but lower recall, how would you respond?

### Bias-Variance as Product Risk

7. Did any model show signs of overfitting or underfitting?What **product risks** does that introduce?
8. Would you prefer a slightly underfit or overfit model for this use case? Why?

### Decision Trees & Explainability

9. How does tree depth or number of leaf nodes affect:
   - user experience?
   - stakeholder trust?
10. What is the maximum model complexity you would feel comfortable explaining to a non-technical stakeholder?

### Feature Interpretation & Product Insight

11. Which features appeared most useful in predicting churn?
12. Did any feature surprise you in its impact?What product hypothesis might explain that?
13. How could product or UX changes reduce churn for high-risk users identified by the model?

### Feature Engineering (Optional Section)

14. Did scaling or normalisation change model performance?
15. From a PM perspective, when would changing feature treatment be acceptable vs risky?

### Threshold & Policy Decisions

16. How would you choose a decision threshold for contacting users?
17. Would you use different thresholds for premium vs free users? Why or why not?

### Shipping & Ethics

18. Would you ship this model today? If not, what is missing?
19. What safeguards would you put in place before using this model in production?
20. Who should be accountable if the model makes a bad decision?

---

### Final Question

**In one paragraph:**
Explain how you would present this model and its trade-offs to the Head of Marketing.
