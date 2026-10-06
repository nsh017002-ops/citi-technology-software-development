# Credit Risk Modeling Proposal

Integrating a machine learning-powered credit risk modeling system into Citi’s loan management workflow streamlines the evaluation process between the **Under Review** and **Approved/Rejected** states. By automating risk scoring, Citi can significantly reduce manual review bottlenecks, minimize loan default rates, ensure regulatory compliance, and accelerate decision-making while maintaining high portfolio quality.

## Data Requirements

To build a robust predictive model, the system will leverage historical and real-time applicant data, including:

- **Borrower Financial Metrics:** Annual income, Debt-to-Income (DTI) ratio, existing liabilities, and liquid assets.
- **Credit History:** Credit bureau scores (e.g., CIBIL/FICO), past loan repayment history, defaults, and credit utilization rates.
- **Employment & Demographic Data:** Employment status, years at current job, industry stability, and professional background.
- **Loan Application Details:** Requested loan amount, loan purpose, requested tenure, and collateral or asset valuation details.

## Data Outputs

The model will generate actionable insights to assist loan officers during the review phase:

- **Probability of Default (PD):** A statistical percentage indicating the likelihood that the borrower will default on the loan.
- **Risk Grading Score:** A categorized risk tier (e.g., Low, Medium, High Risk) mapped to internal lending policies.
- **Automated Recommendation:** A preliminary decision suggestion (e.g., Fast-track approval, manual review required, or recommended rejection) to guide the **Under Review** state.
- **Recommended Credit Limit / Pricing:** Suggested interest rate adjustments or maximum safe lending caps based on the calculated risk profile.

## Architecture

- **Common Choices:** Traditional Logistic Regression (for high interpretability and regulatory baseline), Decision Trees, and advanced ensemble methods like Gradient Boosting Machines (XGBoost, LightGBM).
- **Recommended Architecture:** **Gradient Boosting Machines (XGBoost/LightGBM)** paired with SHAP (SHapley Additive exPlanations) values typically perform best for tabular financial datasets. They capture complex non-linear relationships and interactions between financial variables while offering robust predictive accuracy.

## Risks and Challenges

- **Model Interpretability (Explainability):** Regulatory frameworks require financial institutions to explain *why* a loan was rejected. Black-box models must be paired with explainability tools (like SHAP or LIME) to satisfy compliance and fair lending laws.
- **Data Bias and Fairness:** Historical training data may contain inherent biases, risking unfair denial or discriminatory lending practices. Regular bias audits and fairness constraints are essential.
- **Economic Concept Drift:** Macroeconomic shifts (inflation, interest rate changes, market volatility) can alter borrower behavior, requiring continuous model monitoring and periodic retraining.
- **Data Security and Privacy:** Handling sensitive financial records demands strict encryption, adherence to data protection regulations (such as GDPR/local banking laws), and secure data pipelines.
