# Place Matters: Regional Risks in Breast Cancer Mortality
The Influence of Clinical and Structural Factors on In-Hospital Breast Cancer Mortality Among Black Women

### Overview
This project examines how clinical severity and structural determinants of health jointly influence in-hospital breast cancer mortality among non-Hispanic Black women in the United States. Despite advances in screening and treatment, Black women continue to experience disproportionately higher mortality rates compared to other racial groups.
Using the 2021 National Inpatient Sample (NIS), this study employs statistical and machine learning techniques to identify the most significant predictors of in-hospital death. The findings demonstrate that geographic region, insurance status, and socioeconomic context can influence survival outcomes as strongly as clinical disease severity, highlighting the critical role of structural inequities in shaping health outcomes.
### Research Question
Which clinical and structural factors most significantly increase the likelihood of in-hospital breast cancer mortality among Black women in the United States?
### Objectives
Quantify the impact of clinical severity (e.g., metastatic disease, comorbidities) on in-hospital mortality.
Assess the influence of structural determinants such as insurance type, neighborhood income, and geographic region.
Develop a predictive machine learning model to estimate mortality risk.
Introduce a Structural Inequity Gap to measure disparities attributable to systemic factors.
Provide policy-relevant insights to reduce racial disparities in breast cancer outcomes.
### Data Source
National Inpatient Sample (NIS) – 2021
Provider: Agency for Healthcare Research and Quality (AHRQ), Healthcare Cost and Utilization Project (HCUP)
Sample: 5,933 hospitalizations of non-Hispanic Black women with breast cancer.
Design: Nationally representative inpatient database using discharge weights.
Access: https://www.hcup-us.ahrq.gov/nisoverview.jsp
(Note: HCUP data require a Data Use Agreement and are not publicly distributable.)
#### Variables Used
 Outcome Variable
DIED: Binary indicator of in-hospital mortality.
 Clinical Predictors
Metastatic Disease: ICD-10-CM codes C77–C80.
Age
Congestive Heart Failure (CHF)
Chronic Kidney Disease (CKD)
Diabetes and Hypertension
Breast Cancer as Principal Diagnosis (C50)
 Structural Predictors
Primary Payer (PAY1): Medicare, Medicaid, Private/HMO, Self-pay, Other.
ZIP Code Income Quartile (ZIPINC_QRTL): Proxy for socioeconomic status.
Hospital Census Division (HOSP_DIVISION): Geographic variation.
Elective vs. Non-Elective Admission (ELECTIVE)
Weekend Admission (AWEEKEND)
## Methodology
1. Data Preparation
Extraction of breast cancer hospitalizations using ICD-10 code C50.
Cleaning and recoding of clinical and structural variables.
Application of discharge weights to produce nationally representative estimates.
Handling of categorical variables through encoding and normalization.
2. Exploratory Data Analysis
Descriptive statistics of demographic, clinical, and structural variables.
Comparative analysis across geographic regions and socioeconomic strata.
3. Statistical & Machine Learning Models
Six predictive models were trained and compared:
Model	Purpose
Logistic Regression (L1/L2)	Baseline statistical inference
Elastic Net (Best Model)	Handles multicollinearity and feature selection
Random Forest	Captures nonlinear relationships
Gradient Boosting (GBM)	Enhances predictive performance
XGBoost	Optimized ensemble learning
Training/Validation Split: 70% / 30%
Evaluation Metric: Area Under the ROC Curve (AUC)
Best Performance: Elastic Net (AUC ≈ 0.69)
Feature Importance: Assessed using permutation importance.
#### Technologies Used
Python
Jupyter Notebook
 Key Libraries
pandas – Data manipulation
numpy – Numerical computation
scikit-learn – Machine learning modeling
matplotlib & seaborn – Data visualization
statsmodels – Statistical analysis
Data Source
AHRQ HCUP National Inpatient Sample (NIS)
#### Key Features
Race-Specific Analysis: Focus exclusively on non-Hispanic Black women.
Nationally Representative Estimates: Use of NIS discharge weights.
Integration of Clinical and Structural Determinants.
Machine Learning–Driven Risk Prediction.
Structural Inequity Gap: Quantifies mortality differences attributable to systemic factors.
Regional Analysis: Highlights disparities across U.S. Census divisions.
## Results Highlights
In-Hospital Mortality Rate: 5.3% among Black women.
Strongest Clinical Predictor:
Metastatic disease (OR ≈ 2.18).
Key Structural Predictors:
Geographic Region: Highest risk in the Deep South (Division 6) and lowest in Division 8.
Insurance Status: Self-pay and Medicaid associated with higher mortality.
Socioeconomic Status: Lower ZIP income quartiles linked to increased risk.
Admission Type: Non-elective admissions significantly increase mortality.
Structural Inequity Gap: Up to a 37-percentage-point difference in predicted mortality between high- and low-risk regions.
### Social Justice & Policy Implications
The findings underscore that breast cancer mortality disparities are not solely biological but deeply rooted in structural inequities. Key implications include:
Investment in Oncology Infrastructure in high-mortality regions, particularly the Deep South.
Targeted Screening Initiatives in low-income communities.
Standardization of Inpatient Cancer Care to mitigate the “place effect.”
#### How to Run the Project
1. Clone the Repository
git clone https://github.com/yourusername/place-matters-breast-cancer.git
cd place-matters-breast-cancer
2. Install Required Packages
Using pip:
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels jupyter
Or using conda:
conda install numpy pandas matplotlib seaborn scikit-learn statsmodels jupyter
3. Launch Jupyter Notebook
jupyter notebook
4. Run the Analysis
Open the main notebook file:
Place_Matters_Breast_Cancer_Mortality.ipynb
