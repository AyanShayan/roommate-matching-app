
# Machine Learning Model Research and Design

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Prepared by:** Mirasbek Idiatulla

**Team:** Ayan Matayev, Mirasbek Idiatulla

**Supervisor:** Tomiris Zhaksylyk

**Date:** October 19, 2026

**YouTrack Task:** RMM-6

**Status:** Research and Design Phase

---

## 1. Introduction

Our graduation project aims to develop a mobile application that helps university students find compatible roommates using Machine Learning.

The main technical component is a machine learning-based recommendation system that predicts compatibility between two students based on their lifestyle habits and accommodation preferences.

The application will collect information through a structured questionnaire and use a trained ML model to generate personalized roommate recommendations.

The supervisor requested that Machine Learning be used as the core matching approach rather than relying exclusively on manually defined compatibility rules.

This document describes the proposed ML design, input features, training data strategy, candidate algorithms, evaluation methods, and system integration.

## 2. Problem Definition

University students may experience difficulties when choosing roommates because they often have limited information about each other's daily habits and living preferences.

Differences in sleeping schedules, cleanliness, noise tolerance, guest preferences, and shared responsibilities may contribute to disagreements.

Traditional roommate searches frequently depend on acquaintances, advertisements, or informal communication.

Our proposed system aims to support this decision by predicting compatibility between potential roommates.

### Machine Learning Task

The initial ML task is binary classification.

**Input:** The lifestyle characteristics and preferences of two students.

**Output:** A model prediction indicating whether the student pair is likely to be mutually acceptable for shared accommodation.

The model may also produce a probability estimate that can be used for recommendation ranking after appropriate validation and calibration.

The prediction is not a guarantee that two students will successfully live together.

## 3. Proposed System Workflow

The proposed matching process contains the following steps:

1. A student registers in the mobile application.
2. The student creates a profile.
3. The student completes a lifestyle questionnaire.
4. Questionnaire responses are stored securely in the database.
5. When recommendations are requested, the backend identifies eligible candidates.
6. Mandatory accommodation restrictions are checked.
7. Pairwise compatibility features are constructed.
8. The trained ML model predicts compatibility.
9. Candidates are ranked by the selected recommendation method.
10. The application displays recommendations and relevant explanations.

The final roommate selection remains the responsibility of the users.

## 4. Lifestyle Questionnaire Design

The questionnaire will collect information relevant to roommate compatibility.

The initial feature categories are based on the project's student interviews and literature review.

| ID | Feature | Example Question | Representation |
|---|---|---|---|
| F01 | Sleep Schedule | What time do you usually go to sleep? | Time category |
| F02 | Wake-up Schedule | What time do you usually wake up? | Time category |
| F03 | Cleanliness | How important is room cleanliness to you? | Ordinal scale 1–5 |
| F04 | Noise Tolerance | How much noise can you tolerate? | Ordinal scale 1–5 |
| F05 | Study Environment | Do you prefer studying in a quiet environment? | Categorical |
| F06 | Guest Preferences | How often are guests acceptable? | Ordinal / categorical |
| F07 | Smoking Preferences | Are you comfortable living with a smoker? | Categorical |
| F08 | Budget | What is your acceptable monthly housing budget? | Numeric range |
| F09 | Shared Responsibilities | How do you prefer to divide household tasks? | Categorical |
| F10 | Communication Style | How do you prefer to resolve disagreements? | Categorical |

The final questionnaire will be reviewed and refined based on user feedback.

Sensitive personal attributes should not be collected unless clearly justified by the application's purpose and applicable privacy requirements.

## 5. Pairwise Feature Engineering

A single student's profile is not sufficient to describe the compatibility of a pair.

The ML model will use features derived from both students.

Examples include:

- Difference between preferred sleeping schedules.
- Difference in cleanliness expectations.
- Difference in noise tolerance.
- Compatibility of guest preferences.
- Agreement on smoking restrictions.
- Overlap between accommodation budgets.
- Compatibility of shared responsibility preferences.

For symmetric compatibility prediction, the feature representation should produce the same result when the two students are swapped, unless the model explicitly represents directional preferences.

The exact feature transformations will be determined during implementation and validation.

## 6. Training Data Collection

Supervised machine learning requires labeled training examples.

Each training example will represent a pair of students and their associated lifestyle characteristics.

### Proposed Dataset Structure

| Field | Description |
|---|---|
| student_a_id | Internal identifier of the first student |
| student_b_id | Internal identifier of the second student |
| sleep_difference | Difference in sleeping schedules |
| cleanliness_difference | Difference in cleanliness expectations |
| noise_compatibility | Compatibility of noise preferences |
| guest_compatibility | Compatibility of guest preferences |
| budget_overlap | Whether accommodation budgets overlap |
| smoking_compatibility | Agreement on smoking restrictions |
| responsibility_compatibility | Similarity of household responsibility preferences |
| compatibility_label | Collected compatibility outcome |

Identifiers will be pseudonymized for research use.

### Proposed Label Collection

The project will investigate collecting voluntary pairwise compatibility assessments.

Students may review anonymized or consent-based candidate profiles and indicate whether they would consider sharing accommodation with the candidate.

A possible initial label definition is:

- **1 — Mutually acceptable:** Both students indicate willingness to consider living together.
- **0 — Not mutually acceptable:** At least one student indicates that the pairing is unsuitable.

This outcome measures stated willingness, not demonstrated long-term cohabitation success.

The team will define an appropriate survey procedure, obtain necessary consent, and review the labeling approach with the supervisor.

### Current Data Availability

Five exploratory student interviews were conducted on October 18, 2026.

These interviews support requirements analysis and feature identification.

They do not provide a sufficient labeled training dataset for a reliable supervised ML model.

A separate data collection stage is required.

Synthetic examples may be used to test the software pipeline, but they must not be presented as real student compatibility evidence.

## 7. Candidate Machine Learning Algorithms

Three supervised learning algorithms will be investigated.

### 7.1. Logistic Regression

Logistic Regression will serve as an interpretable classification baseline.

**Advantages:**
- Simple training process.
- Relatively interpretable coefficients.
- Useful for initial supervised classification.

**Limitations:**
- Nonlinear relationships may require feature engineering.
- Probability calibration may be necessary.

### 7.2. Random Forest

Random Forest combines multiple decision trees to generate predictions.

**Advantages:**
- Supports nonlinear relationships.
- Can model feature interactions.
- Suitable for structured tabular datasets.

**Limitations:**
- Lower direct interpretability.
- Requires hyperparameter tuning.
- Performance depends on dataset quality.

### 7.3. Gradient Boosting

Gradient Boosting combines sequential learners to improve prediction performance.

**Advantages:**
- Can capture complex feature relationships.
- Suitable for supervised classification on structured data.
- Supports comparison against simpler approaches.

**Limitations:**
- Requires careful tuning.
- Can overfit limited datasets.
- May need additional explanation methods.

### Algorithm Comparison

| Criterion | Logistic Regression | Random Forest | Gradient Boosting |
|---|---|---|---|
| Supervised classification | Yes | Yes | Yes |
| Nonlinear relationships | Limited without feature engineering | Yes | Yes |
| Interpretability | Relatively high | Moderate | Moderate–low |
| Training complexity | Low | Moderate | Moderate |
| Hyperparameter tuning | Limited | Required | Required |
| scikit-learn support | Yes | Yes | Yes |

The final model will be selected after experimentation.

Random Forest is a candidate, not a confirmed best-performing model.

## 8. Data Preprocessing

The ML pipeline will include:

1. Validation of questionnaire responses.
2. Identification and handling of missing values.
3. Encoding categorical features.
4. Scaling features where appropriate.
5. Construction of pairwise compatibility features.
6. Checking class balance and label quality.
7. Separating training, validation, and testing data.

Preprocessing transformations will be fitted only on the appropriate training data to prevent data leakage.

The project will also investigate whether certain questionnaire features provide meaningful predictive value.

## 9. Training and Evaluation Strategy

The project will compare all candidate models under consistent experimental conditions.

### Training Procedure

1. Prepare a consent-based labeled dataset.
2. Create pairwise feature representations.
3. Split data into training and evaluation subsets.
4. Train candidate supervised classifiers.
5. Tune hyperparameters using validation data.
6. Evaluate selected models on held-out data.
7. Compare results against a non-ML baseline.

Because the same student may appear in several candidate pairs, random pair-level splitting could leak student-specific information between datasets.

The team will investigate participant-disjoint evaluation splits when assessing generalization to unseen students.

### Planned Evaluation Metrics

| Metric | Purpose |
|---|---|
| Precision | Measure the proportion of predicted compatible pairs that are labeled compatible |
| Recall | Measure the proportion of labeled compatible pairs identified by the model |
| F1-score | Balance precision and recall |
| ROC-AUC | Evaluate classification discrimination where applicable |
| Precision@K | Evaluate relevant candidates among top-ranked recommendations |
| Calibration | Examine whether predicted probabilities reflect observed outcomes |

Metrics will be selected based on the final labeling procedure and dataset properties.

### Baseline Comparison

A weighted rule-based compatibility method will be implemented for comparison.

For example, the baseline may assign weights to sleep schedules, cleanliness, noise tolerance, and other factors.

The same evaluation dataset will be used to compare the baseline and ML models.

The ML model will not be considered better unless the experimental results support that conclusion.

## 10. Recommendation Generation

The proposed recommendation process contains two main stages.

### Stage 1 — Eligibility Filtering

Candidates will be checked against mandatory restrictions, such as:

- Acceptable accommodation budget.
- Smoking preferences.
- Accommodation availability.
- Other explicit user requirements.

### Stage 2 — ML Ranking

Eligible candidates will be evaluated using the trained ML model.

Candidates will then be ranked using the selected prediction output.

The recommendation results may include:

- Predicted compatibility score.
- Important areas of similarity.
- Important differences.
- Relevant accommodation preferences.

A displayed percentage must be accurately defined. An uncalibrated model score should not be described as the actual probability of successful cohabitation.

## 11. Explainable Recommendations

Explainability is important because students should understand why a particular roommate is recommended.

The application may provide statements such as:

- Similar preferred sleeping schedules.
- Compatible noise preferences.
- Overlapping accommodation budgets.
- Different guest expectations.

These statements must be derived from actual questionnaire values or validated model explanations.

The project may investigate SHAP or other suitable explanation approaches if supported by the final trained model.

Explanation quality will be considered during usability testing.

## 12. Proposed ML Architecture

### Mobile Application

**Technology:** React Native + Expo

Responsibilities:
- Collect questionnaire responses.
- Display roommate recommendations.
- Show compatibility information.

### Application Backend

**Technology:** NestJS

Responsibilities:
- Manage authentication.
- Store and retrieve student information.
- Apply access permissions.
- Request ML predictions.
- Apply mandatory matching restrictions.

### Database

**Technology:** PostgreSQL + Prisma

Responsibilities:
- Store student profiles.
- Store questionnaire responses.
- Store accommodation preferences.
- Store recommendation-related records where needed.

### ML Service

**Technology:** Python + scikit-learn + FastAPI

Responsibilities:
- Load the trained model.
- Process prediction inputs.
- Generate compatibility predictions.
- Return model outputs to the backend.

### Data Flow

Mobile App
    |
    | HTTPS / REST
    v
NestJS Backend
    |
    | Database Access
    v
PostgreSQL

NestJS Backend
    |
    | Internal HTTP API
    v
Python ML Service
    |
    v
Trained ML Model

The ML inference service will be integrated into the backend architecture after the model and API contracts have been defined.

## 13. Expected ML Service Interface

The proposed internal API may include:

**Endpoint:**

POST /predict-compatibility

**Example Input:**

{
  "sleep_difference": 1,
  "cleanliness_difference": 0,
  "noise_compatibility": 0.8,
  "guest_compatibility": 0.9,
  "budget_overlap": 1,
  "smoking_compatibility": 1
}

**Illustrative Output:**

{
  "compatibility_score": 0.87,
  "model_version": "prototype"
}

These values are examples of the planned interface only.

They are not generated by a trained model.

Authentication, validation, additional features, and final output semantics will be defined during implementation.

## 14. Risks and Limitations

### Risk 1 — Insufficient Training Data

The model may not learn meaningful relationships without enough independently labeled student pairs.

**Mitigation:** Plan data collection early and discuss realistic sample requirements with the supervisor.

### Risk 2 — Self-Reported Information

Students may provide incomplete or inaccurate questionnaire responses.

**Mitigation:** Use clear questions, validation, and appropriate limitations in recommendation explanations.

### Risk 3 — Data Leakage

Student profiles may appear in multiple labeled pairs.

**Mitigation:** Use appropriate splitting strategies and prevent leakage during preprocessing.

### Risk 4 — Poor Model Generalization

A model may perform well on collected data but poorly on new students.

**Mitigation:** Evaluate on held-out participants and compare against a baseline.

### Risk 5 — Privacy and Security

Questionnaire responses may include personal lifestyle information.

**Mitigation:** Minimize data collection, pseudonymize research records, and restrict access to private information.

### Risk 6 — Integration Complexity

The NestJS backend and Python ML service may require additional configuration and deployment.

**Mitigation:** Define a clear API contract and develop integration tests.

## 15. Expected Outcomes

The expected results of this research and design stage are:

1. A defined ML prediction problem.
2. A preliminary lifestyle questionnaire.
3. An identified set of input features.
4. A proposed training data collection strategy.
5. A comparison of candidate ML algorithms.
6. A model evaluation plan.
7. A defined baseline approach.
8. A proposed ML service architecture.
9. Documentation of technical risks and limitations.

At the first pre-defense, the trained ML model and complete application are not yet required.

The immediate goal is to demonstrate a technically realistic and testable ML design.

## 16. Conclusion

This document presents the initial research and design of the machine learning-based roommate matching component.

The proposed approach uses lifestyle questionnaires, pairwise feature engineering, and supervised classification to estimate student compatibility.

Logistic Regression, Random Forest, and Gradient Boosting will be evaluated as candidate algorithms.

The project recognizes that meaningful labeled data is necessary and that five exploratory interviews are insufficient for reliable ML training.

Future work will focus on data collection, model training, validation, recommendation ranking, and integration with the mobile application.

The final model and system behavior will be determined through experiments and supervisor feedback.

## 17. Technical References

[1] scikit-learn — Supervised Learning  
https://scikit-learn.org/stable/supervised_learning.html

[2] scikit-learn — Model Selection and Evaluation  
https://scikit-learn.org/stable/model_selection.html

[3] scikit-learn — Pipeline and Preprocessing  
https://scikit-learn.org/stable/modules/compose.html

[4] scikit-learn — Probability Calibration  
https://scikit-learn.org/stable/modules/calibration.html

[5] FastAPI Documentation  
https://fastapi.tiangolo.com/

[6] NestJS Documentation  
https://docs.nestjs.com/

[7] Project Literature Review  
docs/literature-review/literature-review.md
