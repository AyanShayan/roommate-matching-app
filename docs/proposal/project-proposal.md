# Project Proposal

## 1. Project Information

**Project Title:** Development of a Compatibility-Based Roommate Matching Application for University Students

**Project Type:** Mobile Application with Machine Learning

**Team Members:**
- Ayan Matayev — Mobile Frontend Development & UI/UX Design
- Mirasbek Idiatulla — Backend Development & Machine Learning

**Supervisor:** Tomiris Zhaksylyk

**Project Management:** YouTrack (RMM)

**Version Control:** GitHub

## 2. Problem Statement

Finding a suitable roommate can be challenging for university students, especially those moving into dormitories or shared apartments.

Students often choose roommates based on personal recommendations, social media groups, or available accommodation options. However, these methods may not adequately consider differences in daily routines, cleanliness, sleeping schedules, noise tolerance, and lifestyle preferences.

Such differences can contribute to misunderstandings, conflicts, and uncomfortable living conditions.

Our project aims to address this problem by developing a mobile application that helps university students identify potentially compatible roommates through machine learning-based recommendations.

The relevance of this problem will be investigated through interviews with university students and an analysis of existing roommate-matching services.

## 3. Target Users

The primary target users are university students who are searching for roommates for shared accommodation.

The application is intended for:
- Students moving into university dormitories.
- Students planning to rent apartments together.
- Students searching for roommates with similar lifestyles.
- Students who want to make more informed roommate decisions.

## 4. Project Aim

The main aim of this project is to develop a mobile application that uses machine learning algorithms to recommend compatible roommates for university students based on their lifestyle characteristics, habits, and accommodation preferences.

## 5. Project Objectives

To achieve this aim, the following objectives have been defined:

1. Investigate common problems students experience when searching for roommates.
2. Analyze existing roommate-matching applications and relevant scientific research.
3. Design a user-friendly mobile application interface.
4. Develop a student registration and profile management system.
5. Create a questionnaire to collect lifestyle preferences and roommate requirements.
6. Design and implement a machine learning-based roommate compatibility prediction model.
7. Develop a backend system for managing student profiles, questionnaire responses, and recommendations.
8. Integrate the ML model with the mobile application through backend services.
9. Evaluate the performance of the ML model against a rule-based compatibility baseline.
10. Test the functionality, usability, and reliability of the application.

## 6. Proposed Solution

The proposed solution is a mobile application that recommends potentially compatible roommates using machine learning.

The main workflow will be:

**Step 1 — Registration**

Students create accounts and securely log in.

**Step 2 — Student Profile**

Users provide basic information about themselves and their accommodation preferences.

**Step 3 — Lifestyle Questionnaire**

Students answer questions related to:
- Sleep schedules
- Cleanliness habits
- Noise tolerance
- Study habits
- Guest preferences
- Smoking preferences
- Accommodation budget

**Step 4 — Machine Learning Analysis**

The application sends relevant questionnaire features to the backend.

A trained ML model analyzes the characteristics of student pairs and produces compatibility predictions.

**Step 5 — Roommate Recommendations**

Students receive a ranked list of potential roommates based on model predictions and mandatory accommodation restrictions.

**Step 6 — Profile Exploration**

Users can view recommended roommate profiles and compare their preferences before making a decision.

## 7. Machine Learning Approach

Machine learning will be the core technical component of the roommate recommendation system.

The project will investigate supervised learning algorithms, including:

- Logistic Regression
- Random Forest
- Gradient Boosting

The final model will be selected based on experimental performance, available training data, and interpretability.

Training data will need to include student preference characteristics and independently collected compatibility labels. The team will investigate collecting voluntary survey responses and pairwise compatibility assessments.

The proposed evaluation will include suitable classification and recommendation-ranking metrics, such as F1-score and Precision@K.

A weighted rule-based compatibility method will be developed as a baseline to determine whether the ML approach provides measurable improvements.

The availability and quality of labeled training data are expected to be significant research challenges.

## 8. Proposed Technology Stack

**Mobile Application:**
- React Native
- Expo
- TypeScript

**Backend:**
- Node.js
- NestJS
- REST API

**Database:**
- PostgreSQL
- Prisma ORM

**Machine Learning:**
- Python
- scikit-learn
- pandas
- FastAPI

**Design and Management:**
- Figma
- GitHub
- YouTrack

These technologies are preliminary selections and will be justified through a structured technology comparison.

## 9. Project Scope

### In Scope

The planned core functionality includes:

- Student registration and authentication.
- Student profile creation and editing.
- Lifestyle preference questionnaire.
- Secure storage of student information.
- ML-based roommate compatibility prediction.
- Ranked roommate recommendations.
- Viewing recommended roommate profiles.
- Basic preference and accommodation restrictions.
- Model evaluation and application testing.

### Out of Scope

The following features are not included in the initial implementation:

- Online rental payments.
- Property booking and rental contract management.
- Advanced real-time messaging.
- Video calls.
- Integration with university administrative databases.
- Automated verification of actual roommate relationships.

Some additional features may be considered after completing the core application.

## 10. Expected Outcomes

The expected final outcomes of the project are:

1. A functional mobile application for roommate matching.
2. An implemented and evaluated machine learning compatibility model.
3. A backend API and database for student information.
4. A questionnaire for collecting relevant compatibility features.
5. A recommendation interface showing suitable roommate candidates.
6. Experimental results comparing ML-based matching with a baseline.
7. Technical documentation, architectural diagrams, and testing results.

The application is expected to help students make more informed roommate choices. Whether the recommendations improve real-world compatibility will require appropriate user evaluation.

## 11. Engineering Complexity

The project involves several technical challenges:

- Designing and integrating mobile, backend, database, and ML components.
- Preparing and processing compatibility-related data.
- Obtaining meaningful training labels.
- Comparing and evaluating supervised ML algorithms.
- Preventing data leakage during model evaluation.
- Providing secure authentication and personal data protection.
- Developing a maintainable cross-platform application architecture.

These challenges provide opportunities to apply software engineering, database design, mobile development, and machine learning techniques.

## 12. Team Responsibilities

### Ayan Matayev

**Role: Mobile Frontend Developer & UI/UX Designer**

Responsibilities:
- Design mobile application interfaces using Figma.
- Develop mobile screens using React Native.
- Implement navigation and form interactions.
- Develop student profiles and questionnaire interfaces.
- Display ML-based roommate recommendations.
- Integrate the mobile frontend with backend APIs.
- Perform mobile interface and usability testing.

### Mirasbek Idiatulla

**Role: Backend Developer & Machine Learning Engineer**

Responsibilities:
- Design the backend architecture.
- Develop REST API endpoints using NestJS.
- Design and manage the PostgreSQL database.
- Implement authentication and profile management services.
- Research and develop ML matching algorithms.
- Prepare training and evaluation pipelines.
- Integrate the ML model through a Python service.
- Conduct backend and ML testing.

Both team members will participate in documentation, research, project planning, and code reviews.

## 13. Project Risks and Limitations

Potential risks include:

- Insufficient labeled data for supervised learning.
- Poor generalization of compatibility predictions.
- Bias or unreliable responses in questionnaire data.
- Difficulties integrating ML services with the backend.
- Privacy concerns related to student information.
- Limited development and testing time.

The project will address these risks through early data planning, comparative model evaluation, modular architecture, documented privacy requirements, and regular supervisor reviews.

Personal information and credentials will not be stored in the public project documentation or Git history.

## 14. Current Development Status

**Stage:** Initial Analysis and Design

**Target:** Pre-Defense 1 — October 24, 2026

At this stage, the project focuses on:
- Problem definition and scope.
- Research and literature review.
- Interviews with potential users.
- Technology comparison.
- Software requirements.
- System architecture.
- Mobile UI/UX prototype.
- ML evaluation planning.
- GitHub and YouTrack project management.

A complete mobile application and trained ML model are not required for the first pre-defense.

## 15. Conclusion

This project proposes a machine learning-based mobile application to support roommate selection among university students.

By combining student lifestyle questionnaires, compatibility prediction, and personalized recommendations, the proposed system aims to provide a more structured approach to finding suitable roommates.

The project will apply mobile software development, backend engineering, database management, and machine learning to address a practical problem faced by university students.

The effectiveness of the proposed approach will be assessed through model evaluation, baseline comparison, and user testing.
