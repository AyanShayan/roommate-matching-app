
# Technology Comparison and Selection

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Team Members:** Ayan Matayev, Mirasbek Idiatulla

**Supervisor:** Tomiris Zhaksylyk

**Date:** October 19, 2026

**Project:** RMM — Roommate Matching Application

## 1. Introduction

Our graduation project aims to develop a mobile application that helps university students find compatible roommates using Machine Learning.

The application will include student registration, profiles, lifestyle questionnaires, and personalized roommate recommendations.

Selecting appropriate technologies is important because the system must combine mobile development, backend services, data storage, and ML-based compatibility prediction.

This document compares alternative technologies and explains the proposed choices based on the requirements and limitations of our project.

Four technical decisions are analyzed:

1. Mobile application framework.
2. Backend framework.
3. Database management system.
4. Machine Learning algorithms and tools.

The evaluation considers development complexity, maintainability, available functionality, integration, and suitability for a two-person student development team.

## 2. Mobile Application Framework Comparison

The application should support mobile devices and provide a user-friendly interface for completing questionnaires and viewing roommate recommendations.

Three approaches were considered:

- React Native with Expo
- Flutter
- Native Android and iOS Development

### 2.1. React Native with Expo

React Native is a framework for developing mobile applications using React and JavaScript or TypeScript.

Expo provides development tools, routing, and application build services.

**Advantages:**
- Shared codebase for Android and iOS.
- TypeScript support.
- Reusable UI components.
- Access to native mobile functionality.
- Expo tools simplify development and testing.
- Familiar React concepts can reduce learning time.

**Disadvantages:**
- Some native functionality requires additional configuration.
- Platform-specific behavior may require separate testing.
- Third-party library compatibility must be checked.

### 2.2. Flutter

Flutter is Google's cross-platform UI development framework. It uses Dart and provides a comprehensive widget system.

**Advantages:**
- Shared codebase for multiple platforms.
- Extensive collection of UI widgets.
- Flexible and customizable interface design.
- Consistent rendering across platforms.

**Disadvantages:**
- Requires learning Dart.
- Introduces a separate UI development ecosystem.
- The team would need additional time to become familiar with its development patterns.

### 2.3. Native Android and iOS Development

Native development typically uses Kotlin for Android and Swift for iOS.

**Advantages:**
- Direct access to platform-specific APIs.
- Strong integration with operating-system features.
- Full control over platform-specific interfaces.

**Disadvantages:**
- Separate platform development environments.
- More work to support Android and iOS.
- Increased maintenance effort for a two-person team.

### 2.4. Mobile Framework Comparison Table

| Criterion | React Native + Expo | Flutter | Native Development |
|---|---|---|---|
| Primary language | TypeScript / JavaScript | Dart | Kotlin / Swift |
| Android support | Yes | Yes | Yes |
| iOS support | Yes | Yes | Yes |
| Shared UI codebase | Yes | Yes | Limited |
| Learning requirements | React and TypeScript | Flutter and Dart | Platform-specific skills |
| UI customization | Flexible | Flexible | Full native control |
| Development complexity for our team | Moderate | Moderate | Higher |
| Maintenance for two platforms | Shared codebase | Shared codebase | Separate implementations |

### 2.5. Selected Technology: React Native with Expo

React Native with Expo is the proposed choice for our mobile application.

The main reasons are:

- One development team can support Android and iOS.
- TypeScript can be used for application logic.
- Expo provides useful tools for creating installable application builds.
- The architecture supports reusable components and API integration.
- The approach is suitable for our project scope and team size.

**Responsible Developer:** Ayan Matayev

## 3. Backend Framework Comparison

The backend will handle authentication, student profiles, questionnaire responses, roommate recommendations, and communication with the ML service.

Three frameworks were considered:

- NestJS
- Express.js
- FastAPI

### 3.1. NestJS

NestJS is a Node.js framework designed for building server-side applications using a modular architecture.

**Advantages:**
- TypeScript support.
- Modules, controllers, services, and dependency injection.
- Suitable for structured REST APIs.
- Support for validation, testing, and authentication.
- Clear separation of application responsibilities.

**Disadvantages:**
- Additional architectural concepts to learn.
- More initial configuration than minimal frameworks.
- May be unnecessarily complex for very small applications.

### 3.2. Express.js

Express.js is a lightweight Node.js web framework.

**Advantages:**
- Simple routing and middleware.
- Flexible application structure.
- Large ecosystem.
- Suitable for basic REST APIs.

**Disadvantages:**
- Application architecture requires more manual decisions.
- Validation, dependency management, and project structure must be organized separately.
- Large projects can become difficult to maintain without conventions.

### 3.3. FastAPI

FastAPI is a Python framework for developing APIs.

**Advantages:**
- Uses Python and type annotations.
- Automatic OpenAPI documentation.
- Request validation.
- Convenient integration with Python ML libraries.
- Suitable for exposing ML predictions through HTTP.

**Disadvantages:**
- Using FastAPI for the entire backend would require additional Python backend implementation.
- Choosing FastAPI as the main backend would reduce the benefit of using TypeScript across the mobile and application-server layers.
- The team would need to organize database access, authentication, and business logic using a Python-based stack.

### 3.4. Backend Framework Comparison Table

| Criterion | NestJS | Express.js | FastAPI |
|---|---|---|---|
| Language | TypeScript | JavaScript / TypeScript | Python |
| Built-in architectural conventions | Extensive | Minimal | Moderate |
| REST API support | Yes | Yes | Yes |
| API documentation | Supported | Additional setup | Automatic OpenAPI |
| Python ML integration | HTTP service | HTTP service | Direct Python integration |
| Application modularity | Strong conventions | Developer-defined | Developer-defined |
| Initial complexity | Moderate | Low | Low–moderate |
| Suitability for our main backend | High | Good | Good alternative |

### 3.5. Selected Technology: NestJS

NestJS is the proposed backend framework.

Its modular structure is suitable for separating authentication, student profiles, questionnaires, and recommendation services.

A separate Python service based on FastAPI is proposed for ML inference.

This approach allows the application backend and ML component to use technologies suited to their responsibilities.

However, it introduces an additional deployment and integration dependency. The team should compare this design with an integrated deployment during implementation.

**Responsible Developer:** Mirasbek Idiatulla

## 4. Database Technology Comparison

The database must store student accounts, profiles, questionnaire responses, preferences, and matching-related information.

Three database solutions were considered:

- PostgreSQL
- MongoDB
- Firebase Cloud Firestore

### 4.1. PostgreSQL

PostgreSQL is a relational database management system.

**Advantages:**
- Relational data modeling.
- Primary and foreign key constraints.
- SQL queries and transactions.
- Suitable for structured student profiles and questionnaire data.
- Integration with Prisma ORM.

**Disadvantages:**
- Database schema and migrations must be managed.
- More initial data modeling is required compared with some document databases.
- Database hosting and maintenance must be considered.

### 4.2. MongoDB

MongoDB is a document-oriented database.

**Advantages:**
- Flexible document structures.
- Suitable for JSON-like records.
- Convenient for evolving questionnaire structures.
- Support for indexing and complex queries.

**Disadvantages:**
- Relationships between documents require careful modeling.
- Some relational consistency requirements are less natural to express than in SQL.
- Document duplication can create additional maintenance concerns.

### 4.3. Firebase Cloud Firestore

Cloud Firestore is a managed NoSQL document database.

**Advantages:**
- Managed cloud infrastructure.
- Mobile application integration.
- Real-time synchronization.
- Offline caching capabilities.
- Flexible document storage.

**Disadvantages:**
- Query and data modeling constraints differ from relational SQL.
- Usage-based pricing requires monitoring.
- Security rules require careful configuration.
- The data architecture is more dependent on Firebase services.

### 4.4. Database Comparison Table

| Criterion | PostgreSQL | MongoDB | Firestore |
|---|---|---|---|
| Database model | Relational | Document | Document |
| Query approach | SQL | Document queries | Firebase queries |
| Defined relationships | Foreign keys | Application / document modeling | Document references |
| Schema flexibility | Structured | Flexible | Flexible |
| Transaction support | Yes | Yes, with deployment requirements | Yes |
| Managed hosting options | Available | Available | Managed service |
| Suitability for relational student data | High | Good | Good with careful modeling |
| Prisma integration | Yes | Depends on selected ORM version | No native Prisma connector |

### 4.5. Selected Technology: PostgreSQL

PostgreSQL is the proposed database.

Our application contains related entities, such as:

- Students
- User profiles
- Questionnaire questions
- Questionnaire responses
- Accommodation preferences
- Match recommendations

A relational structure allows these entities to be connected using keys and constraints.

Prisma ORM is proposed for database access from the NestJS backend. Its exact implementation will depend on the ORM version chosen during development.

**Responsible Developer:** Mirasbek Idiatulla

## 5. Machine Learning Technology Comparison

The supervisor requested that the roommate matching algorithm use Machine Learning.

Our project therefore needs to investigate supervised learning models that can predict compatibility between student pairs.

The proposed Python ML stack includes:

- Python
- pandas
- scikit-learn
- FastAPI for model inference

Three algorithms will be evaluated:

- Logistic Regression
- Random Forest
- Gradient Boosting

### 5.1. Logistic Regression

Logistic Regression is a supervised learning method suitable for binary classification.

**Advantages:**
- Relatively simple to train.
- Supports interpretable coefficients.
- Useful as a baseline ML model.
- Can produce estimated class probabilities.

**Disadvantages:**
- May not capture complex nonlinear relationships without feature engineering.
- Requires suitable feature representation.
- Probability estimates may require calibration.

### 5.2. Random Forest

Random Forest combines multiple decision trees.

**Advantages:**
- Can model nonlinear relationships.
- Supports numerical and encoded categorical features.
- Can capture interactions between lifestyle factors.
- Provides feature importance measures.

**Disadvantages:**
- Less directly interpretable than Logistic Regression.
- Requires hyperparameter tuning.
- Can overfit or provide unreliable probabilities depending on the data and configuration.

### 5.3. Gradient Boosting

Gradient Boosting builds an ensemble of models sequentially to improve prediction performance.

**Advantages:**
- Can model complex relationships between features.
- Supports nonlinear patterns.
- Can be effective on structured tabular data.

**Disadvantages:**
- Requires careful hyperparameter tuning.
- Can overfit when data is limited.
- Interpretation may require additional methods.

### 5.4. ML Algorithm Comparison Table

| Criterion | Logistic Regression | Random Forest | Gradient Boosting |
|---|---|---|---|
| Learning type | Supervised | Supervised | Supervised |
| Classification support | Yes | Yes | Yes |
| Nonlinear relationships | Requires feature engineering | Yes | Yes |
| Interpretability | Relatively high | Moderate | Moderate–low |
| Training complexity | Relatively low | Moderate | Moderate |
| Hyperparameter tuning | Relatively simple | Required | Required |
| Probability prediction | Yes | Yes | Yes |
| scikit-learn availability | Yes | Yes | Yes |

### 5.5. Proposed ML Approach

The final model has not yet been selected.

We propose evaluating Logistic Regression, Random Forest, and Gradient Boosting using the same independently collected and labeled dataset.

The model input will represent the lifestyle characteristics and preferences of two students.

Potential features include:

- Sleep schedule compatibility.
- Cleanliness preferences.
- Noise tolerance.
- Guest preferences.
- Study environment preferences.
- Smoking restrictions.
- Budget compatibility.
- Expectations regarding shared responsibilities.

The model's initial target could be a binary label indicating whether both students consider the pair suitable for shared accommodation.

Such labels would require a separate data collection procedure.

Five exploratory interviews have already been conducted to understand user requirements. These interviews are not a sufficient dataset for supervised model training.

### 5.6. Model Evaluation

The team plans to use:

- Training, validation, and test separation.
- Precision, Recall, and F1-score.
- ROC-AUC when applicable.
- Precision@K for ranked recommendations when suitable relevance labels are available.
- Comparison with a weighted rule-based baseline.
- Additional analysis of model limitations and errors.

The split procedure must prevent data leakage between training and testing. Since students may appear in multiple candidate pairs, the evaluation should consider participant-level separation when testing generalization to unseen users.

The final algorithm will be selected based on empirical results, available data, and interpretability.

**Responsible Developer:** Mirasbek Idiatulla

## 6. Component Communication

The proposed application will use REST APIs for communication between the mobile application and NestJS.

NestJS will communicate with the Python ML service over an internal HTTP API.

This approach was selected because REST supports standard HTTP methods, JSON payloads, and independently testable endpoints.

The mobile application will not communicate directly with the database.

The ML inference service should not be publicly exposed unless necessary. Authentication, authorization, validation, and access controls will be implemented at appropriate service boundaries.

## 7. Proposed System Architecture

The proposed system contains four main components:

**1. Mobile Application**

React Native + Expo + TypeScript

Responsibilities:
- Authentication screens.
- Student profiles.
- Lifestyle questionnaires.
- Recommendation presentation.
- User interactions.

**2. Application Backend**

NestJS + Node.js

Responsibilities:
- Authentication and authorization.
- Student and profile management.
- Questionnaire management.
- Recommendation requests.
- Business logic and validation.

**3. Database**

PostgreSQL + Prisma ORM

Responsibilities:
- Store student accounts and profiles.
- Store questionnaire responses.
- Store accommodation preferences.
- Store recommendation records where necessary.

**4. Machine Learning Service**

Python + scikit-learn + FastAPI

Responsibilities:
- Load the trained ML model.
- Process pairwise compatibility features.
- Generate compatibility predictions.
- Return prediction results to NestJS.

### Main Data Flow

1. A student completes a lifestyle questionnaire.
2. The mobile application sends the responses to NestJS.
3. NestJS validates and stores the relevant data in PostgreSQL.
4. When recommendations are requested, NestJS obtains candidate profiles and constructs the required prediction input.
5. The ML service predicts compatibility for eligible pairs.
6. NestJS applies mandatory restrictions and ranking rules.
7. The mobile application displays recommended candidates and supporting explanations.

## 8. Justification of the Selected Stack

| Component | Proposed Technology | Main Reason |
|---|---|---|
| Mobile | React Native + Expo | Shared mobile codebase and suitable development tools |
| Programming language | TypeScript | Type safety and reuse across mobile and backend |
| Backend | NestJS | Modular structure and maintainability |
| Database | PostgreSQL | Structured relational data |
| ORM | Prisma | Database access and schema management |
| ML tools | Python + scikit-learn | Suitable libraries for supervised ML experiments |
| ML inference API | FastAPI | Convenient Python API integration |
| Communication | REST / HTTP | Simple and testable component integration |
| UI/UX | Figma | Mobile interface prototyping |

The proposed stack separates responsibilities between the two team members while supporting integration between mobile development, backend engineering, and Machine Learning.

## 9. Risks and Trade-offs

The following technical risks have been identified:

**Risk 1: Insufficient labeled ML data**

Mitigation: Define a realistic collection and labeling strategy before training.

**Risk 2: Additional service complexity**

Mitigation: Keep clear API contracts between NestJS and FastAPI, and evaluate whether a separate ML service is necessary for the final deployment.

**Risk 3: Mobile platform differences**

Mitigation: Test the application on Android and iOS development environments.

**Risk 4: Database and API integration issues**

Mitigation: Use consistent schemas, API documentation, and integration tests.

**Risk 5: Incorrect or misleading compatibility predictions**

Mitigation: Compare ML models with a baseline and clearly explain prediction limitations.

**Risk 6: Privacy and security problems**

Mitigation: Minimize unnecessary data collection, secure API access, and protect sensitive information.

## 10. Conclusion

This technology comparison evaluated four major technical decisions for the proposed roommate matching application.

React Native with Expo was selected as the preferred mobile development solution because it supports a shared cross-platform codebase and fits the team's development requirements.

NestJS was selected as the preferred application backend because of its modular architecture.

PostgreSQL was chosen for managing structured and related student information.

Python and scikit-learn were selected for Machine Learning development, while the final compatibility prediction algorithm will be chosen after experiments.

These technologies form a proposed architecture that will be validated through implementation, integration testing, usability testing, and ML model evaluation.

## 11. References

[1] React Native Documentation  
https://reactnative.dev/docs/getting-started

[2] Expo Documentation  
https://docs.expo.dev/

[3] Expo EAS Build  
https://docs.expo.dev/build/introduction/

[4] Flutter Documentation  
https://docs.flutter.dev/

[5] Android Developers  
https://developer.android.com/

[6] Apple Developer Documentation  
https://developer.apple.com/documentation/

[7] NestJS Documentation  
https://docs.nestjs.com/

[8] Express.js Documentation  
https://expressjs.com/

[9] FastAPI Documentation  
https://fastapi.tiangolo.com/

[10] PostgreSQL Documentation  
https://www.postgresql.org/docs/

[11] MongoDB Documentation  
https://www.mongodb.com/docs/

[12] Firebase Cloud Firestore Documentation  
https://firebase.google.com/docs/firestore

[13] Prisma Documentation  
https://www.prisma.io/docs/

[14] scikit-learn Documentation  
https://scikit-learn.org/stable/

**Document Status:** Proposed technology decisions, pending implementation and supervisor review.
