#Audit-Ready Credit Risk Engine (Alternative Data & Explainable AI)

Project Overview
This project develops a production-grade credit risk model using the FICO HELOC dataset. Moving beyond traditional credit scoring, I engineered alternative data features to simulate modern financial behaviors (Gig-economy volatility and Utility consistency).

To meet the high transparency standards of the financial industry, the engine implements Monotonic Constraints to ensure logical decision-making and uses SHAP (SHapley Additive exPlanations) to automate "Reason Code" generation for adverse action notices.

<img width="790" height="940" alt="SHAP waterfall plot" src="https://github.com/user-attachments/assets/31e52f4d-6b79-4978-9f5a-09770ebab7e6" />






Key Achievement: Reached an ROC-AUC of 0.7787, successfully discriminating between high-risk (73.3% default rate) and low-risk (31.2% default rate) segments.


Data Engineering & Innovation
Traditional models often fail "thin-file" applicants. This project injects three synthetic data streams to provide a more holistic risk profile:

Utility Consistency Score: A proxy for reliability using non-credit payment history.

Gig-Income Volatility: Modeled to quantify the unpredictability of freelancer cash flows.

Subscription Burden: Analyzes recurring digital expenditures as a percentage of disposable income.

Regulatory Compliance & Modeling
In banking, a model must be defensible. I utilized XGBoost with specific architectural constraints:

Monotonic Constraints: I enforced strict rules (e.g., as Income increases, Risk must decrease). This prevents the model from finding "spurious correlations" that would fail a regulatory audit.

Model Parsimony: Limited tree depth to ensure the model remains interpretable and avoids overfitting.



Explainability & Transparency (XAI)
Under the Equal Credit Opportunity Act (ECOA), lenders must explain why a customer was denied. I integrated a SHAP layer to transform "Black Box" predictions into human-readable insights.

Global Importance
The model prioritizes ExternalRiskEstimate while finding significant signal in my engineered Utility_Consistency_Score.

Local Rejection Reasons (Adverse Action)
For every individual applicant, the system generates specific "Reason Codes." For example, a rejection might be driven by:

Low External Risk Estimate

High Gig-Income Volatility

Low Utility Consistency



How to Run
Upload heloc_dataset_v1.csv to your environment.

Run the Data_Engineering.py script to inject alternative features.

Execute Model_Training.py to train the constrained XGBoost model.

Use Explainability_Suite.ipynb to generate SHAP visualizations and reason codes.



Results
Model Accuracy: Robust performance with an AUC of 0.7787.

Operational Impact: Automated the generation of legally required "Adverse Action" reasons, reducing manual compliance review time.

Risk Segmentation: Clear separation between risk cohorts, providing a reliable foundation for automated lending.

Author: Dhruv Shekar 
Role: Financial Analyst 
Technologies/libraries used : Python, XGBoost, SHAP, Scikit-learn, Pandas, Streamlit
