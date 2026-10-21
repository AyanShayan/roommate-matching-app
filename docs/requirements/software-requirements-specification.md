
# Software Requirements Specification (SRS)

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Prepared by:** Ayan Matayev  
**Team Members:** Ayan Matayev, Mirasbek Idiatulla  
**Supervisor:** Tomiris Zhaksylyk  
**Project:** RMM — Roommate Matching Application  
**YouTrack Task:** RMM-7  
**Date:** October 21, 2026  
**Version:** 1.0  
**Status:** Draft for Pre-Defense 1 and Supervisor Review

---

## 1. Introduction

### 1.1. Purpose

This Software Requirements Specification (SRS) defines the functional and non-functional requirements for a mobile application that helps university students find compatible roommates.

The application will use student lifestyle preferences and a Machine Learning-based matching algorithm to recommend suitable roommate candidates.

This document establishes the expected system behavior, development priorities, acceptance criteria, and technical constraints.

It will guide system architecture, mobile interface design, backend development, implementation, and testing.

### 1.2. Project Background

University students frequently share dormitory rooms or rented apartments.

However, differences in lifestyle preferences, sleep schedules, cleanliness, noise tolerance, and financial responsibilities can create conflicts.

Students may choose roommates through friends, social media, or accommodation advertisements without knowing enough about their daily habits.

Our project proposes a mobile application that collects structured lifestyle information and uses Machine Learning to support roommate selection.

The system will recommend potential roommates rather than automatically assigning students to accommodation.

### 1.3. Project Objectives

The main objectives are:

1. Develop a mobile application for university students.
2. Allow students to create and manage personal profiles.
3. Collect roommate-related lifestyle preferences through a questionnaire.
4. Implement a supervised ML-based compatibility prediction system.
5. Recommend and rank potential roommates.
6. Apply mandatory accommodation and lifestyle restrictions.
7. Explain important similarities and differences between potential roommates.
8. Protect student information and provide appropriate privacy controls.
9. Evaluate recommendation quality and mobile application usability.

### 1.4. Document Scope

This document covers:

- User authentication.
- Student profiles.
- Lifestyle questionnaires.
- Roommate discovery.
- Compatibility prediction.
- Recommendation ranking.
- Preference filters.
- Recommendation explanations.
- Privacy and security.
- Proposed communication and verification features.
- System performance and testing.

The requirements describe the intended product, not functionality that has already been implemented.

---

## 2. Overall System Description

### 2.1. Product Perspective

The proposed system is a cross-platform mobile application supported by backend services, a database, and a Machine Learning component.

The preliminary technology stack is:

| Component | Proposed Technology |
|---|---|
| Mobile application | React Native + Expo + TypeScript |
| Backend | NestJS + Node.js |
| Database | PostgreSQL |
| ORM | Prisma |
| Machine Learning | Python + scikit-learn |
| ML API | FastAPI |
| Interface design | Figma |
| Version control | GitHub |
| Task management | YouTrack |

The technology choices may be refined during implementation following supervisor feedback.

### 2.2. Target Users

The primary users are university students who:

- Are searching for a roommate.
- Currently live in shared accommodation.
- Plan to move into a dormitory or rented apartment.
- Want to compare potential roommates using lifestyle preferences.
- Need more information before deciding to live with someone.

### 2.3. User Roles

**Student**

A registered student can:

- Manage a profile.
- Complete a lifestyle questionnaire.
- Set roommate preferences.
- Search for candidates.
- View compatibility recommendations.
- Manage privacy settings.

**Administrator — Proposed Role**

An administrator may:

- Review reported accounts.
- Moderate inappropriate content.
- Manage account-related safety incidents.

Administration features are lower priority for the initial prototype.

**ML Service**

The ML service is a technical system component, not a human user.

It receives compatibility features and returns predictions for eligible roommate pairs.

### 2.4. Assumptions and Dependencies

The following assumptions are used during initial planning:

- Students will voluntarily provide lifestyle information.
- Internet access will be required for account-based functions.
- The backend and database will be available during application use.
- A separate labeled dataset will be required for supervised ML training.
- Questionnaire design will be reviewed using student feedback.
- University verification may require an additional verification mechanism.
- Final performance targets must be tested after implementation.

The five exploratory interviews already conducted are suitable for requirements analysis but are not sufficient for training a supervised ML model.

---

## 3. Requirements Prioritization

The MoSCoW prioritization method will be used.

| Priority | Meaning |
|---|---|
| Must Have | Essential functionality required for the core project |
| Should Have | Important functionality to implement if resources permit |
| Could Have | Additional functionality that improves the experience |
| Won't Have for Initial Version | Outside the current prototype scope |

The project must deliver a working ML-based recommendation workflow in the final system.

For Pre-Defense 1, the requirements and technical design are the expected deliverables rather than the completed application.

---

## 4. Functional Requirements

### FR-01 — User Registration

**Priority:** Must Have

**Description:** The system shall allow users to register using an email address and password.

**Acceptance Criteria:**
- A valid registration form can be submitted.
- Missing required fields produce validation messages.
- Duplicate email addresses cannot create duplicate accounts.
- Successful registration creates a user account.
- Invalid input does not create an account.

### FR-02 — User Authentication

**Priority:** Must Have

**Description:** The system shall allow registered users to sign in and sign out.

**Acceptance Criteria:**
- Valid credentials allow access to authenticated screens.
- Invalid credentials produce an appropriate error message.
- Protected user data cannot be accessed without authorization.
- Signing out invalidates the relevant session credentials.
- Authentication failures do not disclose password information.

### FR-03 — Student Profile Management

**Priority:** Must Have

**Description:** The system shall allow students to create, view, and update their profiles.

**Profile Fields May Include:**
- Display name.
- University.
- Study program or faculty.
- Short personal description.
- Accommodation preferences.
- Profile photo, if enabled.

**Acceptance Criteria:**
- A user can save a valid profile.
- Saved information is displayed correctly.
- Users can edit their own profiles.
- Users cannot edit another student's profile.
- Private information is not exposed without permission.

### FR-04 — Lifestyle Questionnaire

**Priority:** Must Have

**Description:** The system shall provide a questionnaire to collect roommate-related preferences and habits.

**Questionnaire Categories:**
- Sleep schedule.
- Wake-up schedule.
- Cleanliness.
- Noise tolerance.
- Study environment.
- Guest preferences.
- Smoking restrictions.
- Accommodation budget.
- Shared responsibilities.
- Communication preferences.

**Acceptance Criteria:**
- Users can answer required questions.
- Invalid responses are rejected.
- Completed responses can be saved.
- Users can update previously submitted responses.
- The backend can retrieve authorized questionnaire data for matching.

### FR-05 — Accommodation Preferences

**Priority:** Must Have

**Description:** The system shall allow students to specify their roommate search preferences.

**Examples:**
- Maximum accommodation budget.
- Preferred location.
- Smoking restrictions.
- Required lifestyle conditions.

**Acceptance Criteria:**
- Users can save valid search preferences.
- Users can edit their preferences.
- Mandatory restrictions are identified separately from optional preferences.
- Updated preferences affect subsequent searches.

### FR-06 — Candidate Discovery

**Priority:** Must Have

**Description:** The system shall provide a list of potential roommate candidates.

**Acceptance Criteria:**
- Eligible candidate profiles can be retrieved.
- Users do not appear in their own candidate lists.
- Candidates who violate required restrictions are excluded.
- Empty results display an understandable message.
- Private profile fields are not exposed.

### FR-07 — ML-Based Compatibility Prediction

**Priority:** Must Have

**Description:** The system shall use a trained supervised Machine Learning model to predict compatibility between eligible student pairs.

**Acceptance Criteria:**
- The prediction process uses an actual trained ML model.
- The model receives validated pairwise features.
- The service returns a documented prediction output.
- Invalid requests produce controlled errors.
- Model version information can be recorded.
- Results are not falsely represented as guaranteed roommate success.

The final model will be selected after comparative experiments.

### FR-08 — Recommendation Ranking

**Priority:** Must Have

**Description:** The system shall rank eligible roommate candidates using the selected ML-based recommendation method.

**Acceptance Criteria:**
- Candidates are ranked according to a documented scoring method.
- Ranking is based on actual model outputs.
- Required restrictions are applied before recommendations are shown.
- The system handles cases with no eligible candidates.
- Recommendation order can be reproduced for fixed inputs and a fixed model version.

### FR-09 — Compatibility Explanation

**Priority:** Must Have

**Description:** The system shall explain relevant factors influencing roommate compatibility.

**Acceptance Criteria:**
- The application displays important similarities and differences.
- Explanations are based on actual questionnaire values or validated model explanations.
- Missing information is not represented as a known preference.
- Explanations do not promise successful cohabitation.
- Users can distinguish factual preference comparisons from predictive estimates.

### FR-10 — Candidate Profile Viewing

**Priority:** Must Have

**Description:** The system shall allow users to view permitted information about recommended roommate candidates.

**Acceptance Criteria:**
- Selecting a recommendation opens the corresponding candidate profile.
- The candidate's permitted profile information is displayed.
- Compatibility information is associated with the correct candidate.
- Restricted personal information is not revealed.
- Unavailable profiles display an appropriate message.

### FR-11 — Search Filters

**Priority:** Must Have

**Description:** The system shall allow users to filter roommate candidates using relevant search criteria.

**Acceptance Criteria:**
- Users can select available filters.
- Applying filters updates candidate results.
- Multiple filters can be combined where supported.
- Users can clear applied filters.
- No-match conditions are handled correctly.

### FR-12 — Profile and Questionnaire Updates

**Priority:** Must Have

**Description:** The system shall allow users to update saved lifestyle information.

**Acceptance Criteria:**
- Users can edit their own questionnaire responses.
- Updated responses are stored correctly.
- New recommendation requests use the latest saved data.
- Unauthorized updates are rejected.

### FR-13 — Consent and Privacy Controls

**Priority:** Must Have

**Description:** The system shall provide privacy information and appropriate controls over collected profile data.

**Acceptance Criteria:**
- Users receive information about the purpose of data collection.
- Required consent is recorded where applicable.
- Private data access follows authorization rules.
- Users can request account or personal data deletion through an available process.
- Data handling follows the documented privacy policy and applicable requirements.

### FR-14 — Matching Error Handling

**Priority:** Must Have

**Description:** The application shall handle backend and ML service failures without displaying misleading results.

**Acceptance Criteria:**
- Failed prediction requests do not display invented ML scores.
- Users receive a clear error or retry message.
- The application does not crash when the ML service is unavailable.
- Errors can be investigated through appropriate server logs without exposing sensitive data.

### FR-15 — In-App Communication

**Priority:** Should Have

**Description:** The system should allow students to communicate with potential roommates.

**Acceptance Criteria:**
- Authorized users can initiate supported communication.
- Messages are delivered only to intended participants.
- Users can view their own conversations.
- Unauthorized message access is rejected.

If integrated chat is not implemented in the initial version, the project must document how users can proceed after reviewing recommendations.

### FR-16 — Student Status Verification

**Priority:** Should Have

**Description:** The system should support a mechanism for verifying student affiliation.

**Acceptance Criteria:**
- The application can distinguish verified and unverified accounts if verification is implemented.
- Unverified users are not displayed as verified.
- Users are informed of any verification requirements.
- Verification data is not unnecessarily exposed.

The exact verification mechanism requires further investigation.

### FR-17 — Report and Block Users

**Priority:** Could Have

**Description:** The system may allow users to report or block inappropriate profiles.

**Acceptance Criteria:**
- A report can be submitted with a reason.
- A blocked user is restricted according to documented rules.
- Reports are accessible only to authorized moderation personnel.
- The interface confirms submission without exposing private information.

### FR-18 — Save Favorite Candidates

**Priority:** Could Have

**Description:** The system may allow students to save roommate candidates for later review.

**Acceptance Criteria:**
- Users can add a candidate to a saved list.
- Saved candidates remain associated with the correct account.
- Users can remove saved candidates.
- Users cannot access another student's private saved list.

---

## 5. Functional Requirements Summary

| ID | Requirement | Priority | Responsible Component |
|---|---|---|---|
| FR-01 | User Registration | Must | Mobile + Backend |
| FR-02 | User Authentication | Must | Mobile + Backend |
| FR-03 | Student Profile Management | Must | Mobile + Backend |
| FR-04 | Lifestyle Questionnaire | Must | Mobile + Backend |
| FR-05 | Accommodation Preferences | Must | Mobile + Backend |
| FR-06 | Candidate Discovery | Must | Backend |
| FR-07 | ML Compatibility Prediction | Must | ML + Backend |
| FR-08 | Recommendation Ranking | Must | ML + Backend |
| FR-09 | Compatibility Explanation | Must | Mobile + ML |
| FR-10 | Candidate Profile Viewing | Must | Mobile + Backend |
| FR-11 | Search Filters | Must | Mobile + Backend |
| FR-12 | Profile Updates | Must | Mobile + Backend |
| FR-13 | Privacy Controls | Must | Mobile + Backend |
| FR-14 | Error Handling | Must | All Components |
| FR-15 | In-App Communication | Should | Mobile + Backend |
| FR-16 | Student Verification | Should | Backend |
| FR-17 | Report and Block | Could | Mobile + Backend |
| FR-18 | Favorite Candidates | Could | Mobile + Backend |

---

## 6. Non-Functional Requirements

Non-functional requirements describe how well the application should operate.

The quantitative values below are proposed development targets. They have not yet been measured.

### NFR-01 — Performance

**Priority:** Must Have

**Requirement:** The application should provide responsive profile and questionnaire interactions under normal testing conditions.

**Proposed Acceptance Criteria:**
- At least 95% of standard API requests complete within 2 seconds under the defined test workload.
- Recommendation requests for a defined test dataset complete within 5 seconds in at least 95% of test runs.
- The evaluation records the test environment and workload.

### NFR-02 — Security

**Priority:** Must Have

**Requirement:** The system shall protect accounts and personal information.

**Acceptance Criteria:**
- Passwords are stored using a suitable password-hashing mechanism.
- Protected endpoints require authentication.
- Authorization prevents access to other users' private records.
- Sensitive network communication uses HTTPS in production.
- Secret credentials are not committed to the public repository.

### NFR-03 — Privacy

**Priority:** Must Have

**Requirement:** The system shall minimize unnecessary collection and disclosure of student information.

**Acceptance Criteria:**
- Collected fields have documented purposes.
- Private fields are excluded from public profile responses.
- Research datasets are pseudonymized where applicable.
- Users can access information about data collection and deletion.
- Personally identifiable information is excluded from technical logs unless strictly necessary.

### NFR-04 — Usability

**Priority:** Must Have

**Requirement:** The application shall provide an understandable interface for the main student workflows.

**Proposed Acceptance Criteria:**
- Representative users can register, complete the questionnaire, and review recommendations.
- At least 80% of usability-test participants complete each core workflow without moderator assistance.
- Participants provide qualitative feedback on interface clarity.
- Usability findings and identified problems are documented.

### NFR-05 — Reliability

**Priority:** Must Have

**Requirement:** The system shall handle expected errors without corrupting saved user information.

**Acceptance Criteria:**
- Invalid input is rejected with understandable messages.
- Failed requests do not create unintended duplicate records.
- ML service failures are handled gracefully.
- Critical backend errors are logged for investigation.

### NFR-06 — Maintainability

**Priority:** Must Have

**Requirement:** The application shall follow a modular and documented architecture.

**Acceptance Criteria:**
- Mobile, backend, and ML responsibilities are separated.
- Source code is organized into documented modules.
- Major API contracts are documented.
- GitHub Pull Requests are used for reviewed changes.
- Project setup instructions are maintained in README files.

### NFR-07 — Compatibility

**Priority:** Must Have

**Requirement:** The application shall support the mobile platforms selected for implementation.

**Acceptance Criteria:**
- Core workflows are tested on supported Android configurations.
- Core workflows are tested on supported iOS configurations when test devices or environments are available.
- Supported operating-system versions are documented.
- Platform-specific issues are recorded.

### NFR-08 — Data Integrity

**Priority:** Must Have

**Requirement:** Stored profiles, questionnaire responses, and recommendations shall maintain consistent relationships.

**Acceptance Criteria:**
- Invalid database relationships are rejected.
- Users cannot modify another account's records.
- Questionnaire updates do not create unintended duplicate current responses.
- Database migrations are tracked.

### NFR-09 — ML Evaluation Quality

**Priority:** Must Have

**Requirement:** The compatibility model shall be evaluated using documented experimental procedures.

**Acceptance Criteria:**
- Training and testing data are separated appropriately.
- Data leakage risks are documented.
- Precision, Recall, and F1-score are reported.
- Additional relevant classification or ranking metrics are considered.
- The selected ML model is compared against a rule-based baseline.
- Dataset limitations are reported honestly.

### NFR-10 — Explainability

**Priority:** Must Have

**Requirement:** Compatibility information shall be understandable and should not exaggerate model capabilities.

**Acceptance Criteria:**
- The interface distinguishes predictions from confirmed facts.
- Compatibility explanations relate to actual features.
- Scores are not labeled as real-world success probabilities without supporting calibration and validation.
- Users receive understandable feedback when recommendations cannot be generated.

---

## 7. User Stories

### US-01 — Registration

As a university student, I want to create an account so that I can access personalized roommate matching features.

**Related Requirements:** FR-01, FR-02

### US-02 — Profile Creation

As a student, I want to create a personal profile so that potential roommates can learn relevant information about me.

**Related Requirements:** FR-03, FR-10

### US-03 — Lifestyle Questionnaire

As a student, I want to answer questions about my daily habits so that the system can use my preferences when recommending roommates.

**Related Requirement:** FR-04

### US-04 — Personalized Recommendations

As a student, I want to receive ranked roommate suggestions so that I can identify potentially compatible people.

**Related Requirements:** FR-06, FR-07, FR-08

### US-05 — Explainable Results

As a student, I want to understand why someone was recommended so that I can make an informed decision.

**Related Requirement:** FR-09

### US-06 — Search Preferences

As a student, I want to filter candidates by budget and lifestyle requirements so that I can avoid unsuitable options.

**Related Requirements:** FR-05, FR-11

### US-07 — Privacy

As a student, I want control over my private information so that I can use the application more safely.

**Related Requirement:** FR-13

### US-08 — Communication

As a student, I want to communicate with potential roommates before deciding whether to live together.

**Related Requirement:** FR-15

---

## 8. Main Use Cases

### UC-01 — Register and Create Profile

**Actor:** Student

**Preconditions:** The user does not have an account.

**Main Flow:**
1. The user opens the mobile application.
2. The user selects registration.
3. The user enters required information.
4. The system validates the input.
5. The system creates the account.
6. The user completes a student profile.

**Postconditions:** An authenticated account and profile are available.

**Alternative Flow:** Invalid information produces validation errors.

### UC-02 — Complete Lifestyle Questionnaire

**Actor:** Student

**Preconditions:** The student is authenticated.

**Main Flow:**
1. The student opens the questionnaire.
2. The system displays lifestyle questions.
3. The student selects answers.
4. The student submits the questionnaire.
5. The system validates and saves the responses.

**Postconditions:** Questionnaire responses are available for the recommendation process.

**Alternative Flow:** Missing required answers prevent submission.

### UC-03 — Get Roommate Recommendations

**Actor:** Student

**Preconditions:** The student is authenticated and has provided the required information.

**Main Flow:**
1. The student requests recommendations.
2. The backend retrieves relevant profile data.
3. Mandatory restrictions are evaluated.
4. Eligible candidate pairs are prepared.
5. The ML model produces compatibility predictions.
6. Candidates are ranked.
7. The system returns the recommendation list.
8. The mobile application displays the results.

**Postconditions:** The student can review potential roommate candidates.

**Alternative Flows:**
- No eligible candidates are available.
- Required questionnaire information is missing.
- The ML service is unavailable.

### UC-04 — View Compatibility Details

**Actor:** Student

**Preconditions:** A recommendation is available.

**Main Flow:**
1. The student selects a recommended candidate.
2. The system opens the candidate profile.
3. The system displays permitted profile information.
4. The system shows relevant compatibility information.
5. The student reviews important similarities and differences.

**Postconditions:** The student has additional information for evaluating the recommendation.

---

## 9. Requirements Traceability

The preliminary requirements were informed by five student interviews conducted on October 18, 2026, as well as the project's literature review and existing-system comparison.

| Identified Need | Supporting Evidence | Related Requirements |
|---|---|---|
| Different sleep schedules | Student interviews | FR-04, FR-07 |
| Noise and cleanliness conflicts | Interviews and literature | FR-04, FR-09 |
| Personal boundaries | Student interviews | FR-04, FR-05 |
| Budget and shared expenses | Student interviews | FR-05, FR-11 |
| Guest preferences | Student interviews | FR-04 |
| Reliable profile information | Student interviews | FR-03, FR-16 |
| Understandable recommendations | Student interviews and literature | FR-09, NFR-10 |
| Communication before deciding | Student interviews | FR-15 |
| Privacy and trust | Interviews and privacy literature | FR-13, NFR-02, NFR-03 |
| ML-based roommate matching | Supervisor requirement and project scope | FR-07, FR-08, NFR-09 |

The interviews are exploratory and do not establish that all university students share these needs.

---

## 10. Data Requirements

The initial data model is expected to contain the following entities:

| Entity | Purpose |
|---|---|
| User | Authentication and account information |
| StudentProfile | Student information and permitted profile fields |
| QuestionnaireQuestion | Questionnaire definitions |
| QuestionnaireResponse | Answers to lifestyle questions |
| AccommodationPreference | Student accommodation requirements |
| CompatibilityPrediction | Model outputs where persistence is necessary |
| Recommendation | Recommendation-related records if required |
| ConsentRecord | Relevant privacy and research consent records |

The final database structure will be defined during architecture and backend implementation.

Sensitive data should be separated from publicly visible profile information.

---

## 11. External Interface Requirements

### 11.1. Mobile User Interface

The application will provide the following core screens:

1. Welcome / Onboarding
2. Sign Up
3. Sign In
4. Student Profile Setup
5. Lifestyle Questionnaire
6. Main Recommendations Screen
7. Candidate Profile
8. Compatibility Details
9. Search Filters
10. Profile Editing
11. Settings and Privacy

Additional screens may be added if Should Have or Could Have features are implemented.

### 11.2. Backend API

The mobile application will communicate with the backend through authenticated REST endpoints.

Preliminary API groups include:

- `/auth`
- `/users`
- `/profiles`
- `/questionnaire`
- `/preferences`
- `/recommendations`

Endpoint names, HTTP methods, schemas, and access rules will be specified during implementation.

### 11.3. ML Service Interface

The backend will communicate with the Python ML component.

The ML service will accept validated pairwise compatibility features and return documented prediction outputs.

The production inference service will use a trained and versioned model rather than hard-coded compatibility results.

---

## 12. Constraints and Out-of-Scope Features

### 12.1. Development Constraints

- Two-person development team.
- Limited academic project timeline.
- Limited access to real labeled roommate compatibility data.
- Requirement to use ML-based matching.
- Mobile-first development.
- Appropriate protection of student information.
- Need for documented testing and supervisor review.

### 12.2. Out of Scope for the Initial Version

The following features are not planned as essential components of the initial system:

- Automated rental payments.
- Lease or housing contract management.
- University dormitory administration.
- Automatic assignment of rooms or roommates.
- Property-owner booking systems.
- Guaranteed predictions of successful cohabitation.

These features may be investigated as future improvements.

---

## 13. Verification and Acceptance Strategy

The requirements will be verified using several methods.

| Verification Method | Application |
|---|---|
| Unit Testing | Validation, filtering, and business logic |
| Integration Testing | Mobile, backend, database, and ML communication |
| API Testing | Authentication and REST endpoints |
| ML Evaluation | Classification metrics and baseline comparison |
| Usability Testing | Registration, questionnaire, and recommendations |
| Security Testing | Authentication, authorization, and input validation |
| Manual Acceptance Testing | Main user stories and use cases |

### Core System Acceptance Conditions

The final prototype should demonstrate that:

1. A student can register and sign in.
2. A student can create a profile.
3. A student can complete a lifestyle questionnaire.
4. Preferences can be stored and updated.
5. Eligible roommate candidates can be identified.
6. An actual trained ML model generates compatibility predictions.
7. Recommendations are ranked using the documented approach.
8. The user can view profile and compatibility information.
9. Essential privacy and authorization rules are enforced.
10. The ML model has documented evaluation results and a baseline comparison.

These are planned acceptance conditions and do not imply that the system currently satisfies them.

---

## 14. Requirement Dependencies

Several requirements depend on earlier development work.

| Requirement | Main Dependency |
|---|---|
| FR-03 Student Profiles | FR-01, FR-02 |
| FR-04 Lifestyle Questionnaire | FR-02 |
| FR-06 Candidate Discovery | FR-03, FR-05 |
| FR-07 ML Predictions | FR-04, labeled data, trained model |
| FR-08 Ranking | FR-06, FR-07 |
| FR-09 Explanations | FR-04, FR-07 |
| FR-10 Candidate Viewing | FR-03, FR-06 |
| FR-11 Search Filters | FR-05, FR-06 |
| FR-15 Communication | Authentication and candidate profiles |

The ML data collection and evaluation process is a critical project dependency.

---

## 15. Project Responsibilities

### Ayan Matayev — Frontend and UI/UX

Responsibilities:
- Mobile interface design.
- React Native application development.
- Questionnaire interface.
- Profile and recommendation screens.
- Navigation and interface validation.
- Mobile usability testing.
- Frontend integration with backend APIs.

### Mirasbek Idiatulla — Backend and Machine Learning

Responsibilities:
- NestJS backend development.
- PostgreSQL database design.
- Authentication and business logic.
- ML data processing and feature engineering.
- ML algorithm experimentation.
- Prediction API integration.
- Backend and ML evaluation.

Both team members participate in requirements reviews, testing, documentation, GitHub Pull Requests, and supervisor communication.

---

## 16. Conclusion

This Software Requirements Specification defines the initial requirements for a university student roommate matching application.

The proposed system will allow students to manage profiles, complete lifestyle questionnaires, and receive ML-based roommate recommendations.

The requirements address functionality, security, privacy, usability, performance, and Machine Learning evaluation.

The MoSCoW priorities distinguish essential features from optional improvements.

The document will serve as a reference for system architecture, Figma prototypes, backend development, ML implementation, and future testing.

All requirements remain subject to supervisor feedback and technical feasibility review.

---

## 17. Related Project Documents

- `docs/proposal/project-proposal.md`
- `docs/interviews/interview-findings.md`
- `docs/literature-review/literature-review.md`
- `docs/literature-review/literature-matrix.md`
- `docs/existing-systems/existing-systems-comparison.md`
- `docs/technology-comparison/technology-comparison.md`
- `docs/ml-research/ml-model-design.md`

**Document Status:** Draft completed for Pre-Defense 1 review.
