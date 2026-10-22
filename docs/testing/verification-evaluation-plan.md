
# Verification and Evaluation Plan

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Prepared by:** Mirasbek Idiatulla  
**Team Members:** Ayan Matayev, Mirasbek Idiatulla  
**Supervisor:** Tomiris Zhaksylyk  
**Project:** RMM — Roommate Matching Application  
**YouTrack Task:** RMM-10  
**Date:** October 22, 2026  
**Version:** 1.0  
**Status:** Planned — Pre-Defense 1

---

## 1. Introduction

This document describes the proposed verification and evaluation strategy for the Roommate Matching Application.

The application aims to help university students find potentially compatible roommates through lifestyle questionnaires and a supervised Machine Learning recommendation system.

Testing is necessary to determine whether the application performs its intended functions, protects student information, provides understandable recommendations, and produces meaningful ML predictions.

This document defines test objectives, methods, conditions, evaluation metrics, acceptance criteria, baselines, responsibilities, and expected evidence.

The system is currently in the research and design phase. The results of the proposed tests have not yet been collected.

## 2. Verification and Evaluation Objectives

The project has five main evaluation objectives.

### Objective 1 — Functional Correctness

Verify that the application supports registration, authentication, profiles, questionnaires, filtering, and roommate recommendation workflows.

### Objective 2 — ML Prediction Quality

Evaluate how well supervised learning models predict mutually acceptable roommate pairs from lifestyle and preference information.

### Objective 3 — Baseline Comparison

Determine whether an ML model performs better than a weighted rule-based compatibility method on the same evaluation data.

### Objective 4 — Mobile Usability

Evaluate whether university students can understand and complete the application's main tasks.

### Objective 5 — Security, Privacy, and Reliability

Verify that the system protects personal information and handles invalid inputs and service failures appropriately.

## 3. Testing Scope

The following system components are included:

| Component | Technology | Planned Verification |
|---|---|---|
| Mobile application | React Native + Expo | UI, navigation, usability |
| Backend | NestJS | API and business logic tests |
| Database | PostgreSQL | Data integrity and access control |
| ML service | Python + FastAPI | Input validation and prediction tests |
| ML models | scikit-learn | Classification and ranking evaluation |
| System integration | REST APIs | End-to-end workflow tests |

Optional features such as integrated messaging will be tested if implemented.

The initial evaluation does not aim to prove that recommended students will have successful long-term roommate relationships.

## 4. Functional Testing Plan

Functional testing will be based on the requirements in RMM-7.

### 4.1. Functional Test Cases

| Test ID | Related Requirement | Test Scenario | Expected Result |
|---|---|---|---|
| FT-01 | FR-01 | Register with valid information | Account is created |
| FT-02 | FR-01 | Register using an existing email | Duplicate account is rejected |
| FT-03 | FR-02 | Sign in with correct credentials | User is authenticated |
| FT-04 | FR-02 | Sign in with incorrect credentials | Access is denied |
| FT-05 | FR-03 | Create and update student profile | Profile information is saved |
| FT-06 | FR-04 | Complete lifestyle questionnaire | Responses are saved |
| FT-07 | FR-04 | Submit incomplete required answers | Validation error is shown |
| FT-08 | FR-05 | Set accommodation restrictions | Preferences are stored |
| FT-09 | FR-06 | Request eligible candidates | Candidate list excludes ineligible users |
| FT-10 | FR-07 | Submit valid ML prediction input | Model returns documented prediction |
| FT-11 | FR-07 | Submit invalid ML prediction input | Request is rejected safely |
| FT-12 | FR-08 | Request recommendations | Eligible candidates are ranked |
| FT-13 | FR-09 | View compatibility explanation | Relevant factors are displayed |
| FT-14 | FR-10 | Open candidate profile | Permitted candidate information appears |
| FT-15 | FR-11 | Apply multiple filters | Results reflect selected filters |
| FT-16 | FR-12 | Update questionnaire answers | New requests use updated answers |
| FT-17 | FR-13 | Attempt unauthorized data access | Access is denied |
| FT-18 | FR-14 | Simulate ML service failure | Application shows an appropriate error |
| FT-19 | FR-06 | Search with no eligible candidates | Empty state is displayed |
| FT-20 | FR-02 | Sign out | Protected session is ended |

### 4.2. Execution Method

For each test case, the development team will:

1. Prepare the necessary test data.
2. Establish the required initial system state.
3. Execute the test steps.
4. Record actual behavior.
5. Compare actual behavior with the expected result.
6. Mark the test as Passed, Failed, or Blocked.
7. Record relevant defects.

Tests will be executed after the required functionality has been implemented.

### 4.3. Functional Acceptance Criteria

Proposed completion requirements:

- All implemented Must Have requirements have corresponding test cases.
- No critical functional test remains failed.
- Registration, questionnaire, profile, and recommendation workflows pass end-to-end testing.
- Known non-critical defects are documented with their impact.

These criteria may be refined after supervisor review.

## 5. Backend API Testing

Backend testing will verify:

- Correct HTTP response codes.
- Request validation.
- Authentication and authorization.
- Profile ownership restrictions.
- Database persistence.
- Error handling.
- ML service communication.

### Sample API Test Cases

| Test ID | Scenario | Expected Result |
|---|---|---|
| API-01 | Valid registration request | Successful account creation |
| API-02 | Invalid registration body | 4xx validation response |
| API-03 | Request private profile without authorization | Access denied |
| API-04 | Update another user's questionnaire | Access denied |
| API-05 | Save valid questionnaire responses | Data stored correctly |
| API-06 | Request recommendations with valid input | Structured response |
| API-07 | ML service timeout | Controlled backend error |
| API-08 | Malformed ML output | Invalid result is rejected |

The final endpoint paths and response schemas will follow the implemented API contract.

## 6. Machine Learning Evaluation

### 6.1. ML Task Definition

The proposed ML task is supervised binary classification.

Each example represents a pair of students.

**Input:** Pairwise lifestyle and accommodation preference features.

**Label:**
- 1 — Both students indicate willingness to consider living together.
- 0 — At least one student indicates that the pair is unsuitable.

The label represents mutual stated acceptance, not verified long-term roommate satisfaction.

### 6.2. Candidate Models

The following models will be evaluated:

1. Logistic Regression.
2. Random Forest.
3. Gradient Boosting.

The final model will be selected based on experimental results rather than model complexity alone.

### 6.3. Dataset Requirements

The evaluation requires independently collected, consent-based labeled student pairs.

The dataset should include:

- Pseudonymized participant identifiers.
- Lifestyle questionnaire responses.
- Pairwise compatibility features.
- Pairwise compatibility labels.
- Information about the collection method.

The dataset collection procedure must be reviewed for privacy and ethical considerations.

Five previously conducted exploratory interviews are useful for defining requirements but are not sufficient for ML training or valid quantitative performance evaluation.

Synthetic data may be used to test the ML pipeline, but any results obtained only from synthetic labels must be identified as technical demonstrations rather than real predictive validation.

### 6.4. Dataset Splitting

The proposed initial approach is to separate data into training, validation, and held-out test sets.

An illustrative split is:

- Training: approximately 70%.
- Validation: approximately 15%.
- Testing: approximately 15%.

These proportions may change depending on available data.

Because one student may appear in multiple candidate pairs, random pair-level splitting can cause information leakage.

The preferred evaluation of generalization to new students will use participant-disjoint subsets, where no participant appears in both training and held-out test pairs.

Pairs crossing subset boundaries must be handled explicitly, rather than accidentally reintroducing shared participants.

If the dataset is too small for a meaningful participant-disjoint evaluation, the project will report this limitation and avoid unsupported performance claims.

### 6.5. Evaluation Metrics

| Metric | Purpose | Interpretation |
|---|---|---|
| Precision | Correctness of positive compatibility predictions | Higher values mean fewer false positive recommendations |
| Recall | Identification of mutually acceptable pairs | Higher values mean fewer missed compatible pairs |
| F1-score | Balance Precision and Recall | Useful when both types of error matter |
| ROC-AUC | Discrimination across classification thresholds | Used when both classes and sufficient data are available |
| PR-AUC / Average Precision | Precision-recall trade-off | Useful when positive examples are uncommon |
| Precision@K | Quality of top-ranked candidates | Requires suitable ranking relevance labels |
| Probability calibration | Reliability of predicted probabilities | Determines whether scores can be interpreted probabilistically |

### 6.6. Primary ML Success Criterion

The primary planned comparison metric is F1-score for the mutually acceptable class.

Secondary metrics will include Precision, Recall, and relevant ranking performance.

The model will be compared with the rule-based baseline using the same held-out evaluation data.

**Proposed success condition:** The selected ML model should improve the primary metric over the rule-based baseline while maintaining acceptable Precision and without serious data leakage.

No guaranteed numeric ML accuracy threshold is assumed before understanding the dataset and label distribution.

Performance values will be reported only after actual experiments.

## 7. Baseline Comparison

A baseline is necessary to determine whether Machine Learning provides measurable value.

### 7.1. Baseline A — Weighted Rule-Based Matching

A traditional compatibility approach will calculate similarity using manually defined lifestyle weights.

Potential factors include:

- Sleep schedule similarity.
- Cleanliness similarity.
- Noise preference similarity.
- Guest preference compatibility.
- Budget compatibility.

Mandatory restrictions will be handled consistently across the baseline and ML approaches.

Weights and decision thresholds must be defined using training or validation information, not the held-out test results.

### 7.2. Baseline B — Simple Majority Classifier

A second baseline may predict the most common label in the training dataset.

This provides a basic reference for interpreting performance, especially when labels are imbalanced.

### 7.3. Comparison Procedure

The evaluation will:

1. Train the ML candidates on the designated training data.
2. Configure the baseline using the same permitted training information.
3. Select hyperparameters using validation data.
4. Evaluate all approaches on the same held-out test examples.
5. Report the metrics in a comparison table.
6. Explain observed performance differences and limitations.

### 7.4. Planned Results Table

| Approach | Precision | Recall | F1-score | ROC-AUC | Status |
|---|---|---|---|---|---|
| Majority Classifier | TBD | TBD | TBD | TBD | Not evaluated |
| Weighted Rule-Based | TBD | TBD | TBD | TBD | Not evaluated |
| Logistic Regression | TBD | TBD | TBD | TBD | Not evaluated |
| Random Forest | TBD | TBD | TBD | TBD | Not evaluated |
| Gradient Boosting | TBD | TBD | TBD | TBD | Not evaluated |

**TBD** means that no experimental result is currently available.

## 8. Recommendation Ranking Evaluation

Classification accuracy alone does not fully evaluate recommendation quality.

Students will normally see a ranked list of candidate roommates.

The team will therefore investigate top-K recommendation metrics.

### Proposed Ranking Test

For each eligible student in the evaluation dataset:

1. Identify candidate profiles with available independent relevance labels.
2. Apply the same mandatory restrictions to every compared method.
3. Rank candidates using the baseline and ML models.
4. Calculate Precision@K for a predefined K where enough labeled candidates exist.
5. Compare the quality of the top-ranked results.

Relevance labels must not be generated from the same compatibility formula being evaluated.

If sufficient independently labeled candidate lists are unavailable, ranking evaluation will be postponed and the limitation documented.

## 9. ML Robustness and Explainability Testing

### 9.1. Robustness

The team will test:

- Missing questionnaire fields.
- Unsupported categorical values.
- Out-of-range numeric features.
- Inconsistent data types.
- Missing model files.
- Unexpected model output formats.
- Deterministic inference for the same fixed input and model.

Invalid input must not produce fabricated compatibility percentages.

### 9.2. Explainability

Compatibility explanations should:

- Reflect actual questionnaire values or validated model attribution methods.
- Identify meaningful similarities and differences.
- Avoid unsupported causal claims.
- Clearly distinguish observed preferences from model predictions.

A separate usability question will assess whether participants understand why a roommate was recommended.

## 10. Mobile Usability Evaluation

The usability study will investigate whether representative university students can complete the main workflows.

### 10.1. Participants

The initial planned usability study will involve approximately 5–8 university students recruited voluntarily.

This is an exploratory usability test rather than a statistically representative study.

Participants will receive an explanation of the test and the use of collected feedback.

### 10.2. Usability Tasks

| Task ID | Task | Success Condition |
|---|---|---|
| UX-01 | Register or sign in | Participant reaches the authenticated interface |
| UX-02 | Complete lifestyle questionnaire | Responses are submitted successfully |
| UX-03 | Set accommodation preferences | Preferences are saved |
| UX-04 | Find potential roommates | Participant opens recommendations |
| UX-05 | Review compatibility details | Participant identifies at least one similarity and one difference |
| UX-06 | Apply a search filter | Candidate list updates correctly |
| UX-07 | Edit own profile | Updated profile is saved |

### 10.3. Usability Metrics

The team will measure:

- Task completion rate.
- Time on task.
- Number of navigation errors.
- Number of assistance requests.
- User-reported clarity of recommendations.
- Qualitative comments and improvement suggestions.

### 10.4. Proposed Acceptance Targets

The initial usability targets are:

- At least 80% of participants complete each core task without moderator assistance.
- Major navigation problems are documented and addressed.
- Participants can distinguish ML predictions from confirmed personal information.
- Critical problems preventing core workflows are resolved before final demonstration.

These are proposed engineering targets, not measured results.

## 11. Performance Testing

Performance testing will evaluate API response time and recommendation latency.

### 11.1. Test Conditions

The following initial workload is proposed for the prototype:

- Development or staging backend deployment.
- A documented test dataset with at least 100 candidate profiles, if feasible.
- Sequential requests and a small concurrent workload.
- At least 30 repetitions per tested endpoint and workload condition.
- Recorded device, server environment, dataset size, and model version.

The workload may be adjusted to available infrastructure.

### 11.2. Proposed Performance Targets

| Measurement | Proposed Target |
|---|---|
| Standard API response time | 95th percentile below 2 seconds |
| Recommendation response time | 95th percentile below 5 seconds under the defined prototype workload |
| Application stability | No crashes during planned core workflow tests |
| Invalid request handling | Consistent controlled error responses |

These targets must be verified under documented testing conditions.

## 12. Security and Privacy Testing

The application will process student profiles and lifestyle information.

The security evaluation will be informed by the OWASP Mobile Application Security Verification Standard.

### Proposed Security Tests

| Test ID | Scenario | Expected Result |
|---|---|---|
| SEC-01 | Access private API without authentication | Request denied |
| SEC-02 | Modify another student's data | Request denied |
| SEC-03 | Submit malformed questionnaire values | Server rejects invalid data |
| SEC-04 | Inspect password storage | Passwords are securely hashed |
| SEC-05 | Inspect repository configuration | No committed real credentials |
| SEC-06 | Inspect public profile response | Private fields are excluded |
| SEC-07 | Test expired session credentials | Access denied |
| SEC-08 | Inspect production transport | HTTPS protects client-server traffic |
| SEC-09 | Inspect ML service access | Untrusted clients cannot bypass backend controls |
| SEC-10 | Review account deletion process | Documented deletion procedure is available |

The team will document limitations where a complete security audit is not feasible.

## 13. End-to-End Integration Tests

End-to-end tests will verify communication among the application components.

### Integration Scenario 1 — Registration and Profile

1. Register a new account.
2. Authenticate successfully.
3. Create a student profile.
4. Retrieve the saved profile.
5. Verify database consistency.

### Integration Scenario 2 — Questionnaire and Matching

1. Authenticate a test student.
2. Submit valid lifestyle answers.
3. Store questionnaire responses.
4. Request recommendations.
5. Retrieve eligible candidates.
6. Send valid compatibility features to the ML service.
7. Receive documented ML predictions.
8. Display the ranked recommendations.

### Integration Scenario 3 — Failure Handling

1. Disable the ML prediction service.
2. Request roommate recommendations.
3. Verify that the backend handles the failure.
4. Verify that the mobile application displays an appropriate message.
5. Confirm that no invented prediction value appears.

## 14. Test Environment and Tools

| Purpose | Proposed Tool |
|---|---|
| Frontend testing | Jest / React Native Testing Library |
| Backend unit testing | Jest |
| API testing | Postman or automated HTTP tests |
| ML experiments | Python, pandas, scikit-learn |
| Model evaluation | scikit-learn metrics |
| Database verification | PostgreSQL test database |
| Performance measurement | API timing scripts / k6 if needed |
| UX testing | Figma prototype and mobile builds |
| Issue tracking | YouTrack |
| Version control | GitHub |

Tool selection may change according to implementation constraints.

Testing should use test accounts and non-sensitive data whenever possible.

## 15. Requirements Traceability

| Requirement Group | Verification Method |
|---|---|
| FR-01–FR-05 | Registration, authentication, profile, and questionnaire tests |
| FR-06–FR-08 | Candidate discovery and ML recommendation tests |
| FR-09–FR-11 | Compatibility details and filter tests |
| FR-12–FR-14 | Data update, privacy, and error handling tests |
| NFR-01 | Performance tests |
| NFR-02–NFR-03 | Security and privacy tests |
| NFR-04 | Usability tests |
| NFR-05–NFR-08 | Reliability, architecture, compatibility, and data integrity tests |
| NFR-09 | ML evaluation and baseline comparison |
| NFR-10 | Explanation review and usability feedback |

This traceability matrix links the verification plan to the Software Requirements Specification.

## 16. Evidence and Reporting

The team will save test evidence in the repository or an appropriately restricted location.

Planned evidence includes:

- Test case execution records.
- Unit and integration test results.
- API response examples.
- ML model evaluation tables.
- Model training configurations.
- Baseline comparison results.
- Usability test summaries.
- Defect records in YouTrack.
- Screenshots of non-sensitive test results.

Private participant information and raw sensitive research records will not be included in a public repository.

Actual test results will be added only after execution.

## 17. Roles and Responsibilities

### Ayan Matayev — Frontend and UI/UX

Responsibilities:

- Mobile interface testing.
- Navigation testing.
- Questionnaire interaction testing.
- Usability study preparation.
- Student feedback collection.
- Frontend defect resolution.

### Mirasbek Idiatulla — Backend and ML

Responsibilities:

- API testing.
- Database and backend verification.
- ML dataset validation.
- ML model evaluation.
- Baseline comparison.
- ML service integration tests.
- Backend defect resolution.

Both developers will review test results and maintain documentation.

## 18. Proposed Testing Stages

| Stage | Planned Activity | Deliverable |
|---|---|---|
| Pre-Defense 1 | Define verification and evaluation methods | Evaluation plan |
| Early implementation | Establish unit and API tests | Initial test suite |
| ML development | Collect data and train models | Model evaluation report |
| Integration stage | Test end-to-end workflows | Integration test results |
| Prototype refinement | Conduct student usability tests | UX feedback report |
| Final validation | Resolve critical defects and consolidate evidence | Final verification summary |

The schedule will be refined after supervisor feedback.

## 19. Limitations and Risks

### Limited Labeled Data

Without sufficient reliable pairwise labels, supervised ML evaluation may be inconclusive.

**Mitigation:** Plan data collection, report sample sizes, and avoid unsupported accuracy claims.

### Data Leakage

The same student may appear in multiple pairwise examples.

**Mitigation:** Use participant-disjoint testing where appropriate and carefully manage cross-subset pairs.

### Self-Reported Preferences

Students may provide inaccurate or incomplete answers.

**Mitigation:** Use clear questionnaire wording and document this source of uncertainty.

### Small Usability Sample

A small group can reveal usability problems but cannot represent all university students.

**Mitigation:** Describe the study as exploratory and avoid population-level conclusions.

### Limited Testing Infrastructure

Available devices and hosting resources may restrict realistic performance testing.

**Mitigation:** Document the environment and interpret results within the tested conditions.

### Limited Real-World Outcome Evidence

Mutual willingness to live together does not demonstrate successful long-term cohabitation.

**Mitigation:** Distinguish predicted compatibility from observed roommate outcomes.

## 20. Conclusion

This document defines the proposed verification and evaluation strategy for the Roommate Matching Application.

The evaluation covers functional correctness, backend integration, Machine Learning prediction quality, recommendation ranking, usability, performance, security, and privacy.

A key part of the project is comparing supervised ML algorithms against a weighted rule-based compatibility baseline using appropriate independent data.

The plan also identifies limitations relating to dataset size, self-reported information, potential data leakage, and real-world validation.

The results of these activities will be reported during later development stages. At Pre-Defense 1, the objective is to demonstrate a clear, realistic, and measurable evaluation plan.

## 21. References

[1] scikit-learn — Model Evaluation  
https://scikit-learn.org/stable/modules/model_evaluation.html

[2] scikit-learn — Cross-validation  
https://scikit-learn.org/stable/modules/cross_validation.html

[3] scikit-learn — Common Pitfalls and Data Leakage  
https://scikit-learn.org/stable/common_pitfalls.html

[4] OWASP — Mobile Application Security Verification Standard  
https://mas.owasp.org/MASVS/

[5] Project Software Requirements Specification  
docs/requirements/software-requirements-specification.md

[6] Project ML Model Research and Design  
docs/ml-research/ml-model-design.md

**Document Status:** Prepared for Pre-Defense 1 and supervisor review.
