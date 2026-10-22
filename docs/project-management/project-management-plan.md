# Project Management Plan and Risk Assessment

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Prepared by:** Ayan Matayev
**Team Members:** Ayan Matayev, Mirasbek Idiatulla
**Supervisor:** Tomiris Zhaksylyk
**Project:** Roommate Matching Application (RMM)
**YouTrack Task:** RMM-11
**Date:** October 22, 2026
**Status:** Draft for Pre-Defense 1

---

## 1. Introduction

This document describes the project management approach for the development of a compatibility-based roommate matching mobile application for university students.

The application will help students discover potential roommates through lifestyle questionnaires and supervised Machine Learning-based recommendations.

The project is being developed by a two-person team. Therefore, clear responsibilities, task tracking, code reviews, and realistic planning are important for successful implementation.

This document defines the project scope, work breakdown structure, team responsibilities, milestones, dependencies, collaboration process, risks, and monitoring approach.

## 2. Project Objectives

The main project objectives are:

1. Investigate roommate compatibility problems among university students.
2. Review relevant academic research and existing applications.
3. Define functional and non-functional system requirements.
4. Design a user-friendly cross-platform mobile application.
5. Develop a backend and relational database.
6. Collect appropriate data for supervised ML training.
7. Train and evaluate a roommate compatibility prediction model.
8. Integrate ML recommendations into the mobile application.
9. Evaluate system functionality, usability, and recommendation quality.
10. Prepare documentation and demonstrations for university defenses.

The first pre-defense focuses on research, planning, requirements, diagrams, and a prototype rather than a completed production application.

## 3. Project Scope

### 3.1. In Scope

The planned system includes:

- Student registration and authentication.
- Student profile management.
- Lifestyle compatibility questionnaires.
- Accommodation and lifestyle preferences.
- Candidate discovery and filtering.
- ML-based compatibility prediction.
- Ranked roommate recommendations.
- Compatibility explanations.
- Privacy and security controls.
- Mobile usability and model evaluation.

### 3.2. Optional Features

The following features may be developed if time and resources permit:

- Integrated messaging.
- Student-status verification.
- Saving favorite candidates.
- User reporting and blocking.
- Mutual interest confirmation.

### 3.3. Out of Scope

The initial version will not include:

- Automated apartment rental payments.
- Housing contract management.
- Property booking systems.
- University dormitory administration.
- Automatic roommate or room assignment.
- Guarantees of successful long-term roommate relationships.

## 4. Team Structure and Responsibilities

The project has two student developers and one academic supervisor.

| Team Member        | Project Role                        | Main Responsibilities                                                                                                 |
| ------------------ | ----------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Ayan Matayev       | Frontend Developer & UI/UX Designer | Mobile application, interface design, Figma prototype, questionnaire screens, frontend integration, usability testing |
| Mirasbek Idiatulla | Backend Developer & ML Engineer     | Backend APIs, database, data preprocessing, ML model development, recommendations, backend testing                    |
| Tomiris Zhaksylyk  | Academic Supervisor                 | Review of project direction, research, technical decisions, progress, and academic deliverables                       |

### 4.1. Ayan Matayev

Responsibilities:

- Conduct preliminary user interviews.
- Analyze existing roommate matching systems.
- Prepare system requirements.
- Design user flows and mobile interfaces.
- Develop the React Native frontend.
- Integrate frontend screens with backend APIs.
- Conduct usability evaluation.
- Maintain project management documentation.

### 4.2. Mirasbek Idiatulla

Responsibilities:

- Conduct the academic literature review.
- Compare and justify selected technologies.
- Research ML matching approaches.
- Define system architecture.
- Develop NestJS backend services.
- Design the PostgreSQL database.
- Prepare and evaluate ML models.
- Conduct backend and model testing.

### 4.3. Shared Responsibilities

Both developers will:

- Maintain the GitHub repository.
- Track work in YouTrack.
- Review each other's Pull Requests.
- Discuss system integration.
- Update documentation.
- Fix defects.
- Prepare demonstrations.
- Incorporate supervisor feedback.

## 5. Project Management Approach

The team uses an iterative development approach with task-based planning.

The project is divided into research, design, implementation, integration, testing, and final documentation stages.

YouTrack is used to manage tasks and progress.

GitHub is used for version control, code reviews, and documentation.

Figma is used for UI/UX design and interactive mobile prototyping.

The development process follows these steps:

1. Define a task in YouTrack.
2. Assign an owner and priority.
3. Define an expected deliverable.
4. Create a corresponding Git branch.
5. Complete the work.
6. Open a Pull Request.
7. Request review from the other team member.
8. Address review comments.
9. Merge approved changes into the main branch.
10. Update the task and attach evidence.

This approach provides traceability between project requirements, individual contributions, and GitHub history.

## 6. Work Breakdown Structure

The work is organized into six major work packages.

### WBS 1.0 — Research and Problem Analysis

- 1.1 Project Proposal
- 1.2 Student Interviews
- 1.3 Literature Review
- 1.4 Existing Systems Comparison

### WBS 2.0 — Technical Planning

- 2.1 Technology Comparison
- 2.2 Machine Learning Research and Design
- 2.3 Software Requirements Specification
- 2.4 System Architecture and UML Diagrams

### WBS 3.0 — UI/UX Design

- 3.1 Define user flows
- 3.2 Create mobile screens in Figma
- 3.3 Connect interactive prototype screens
- 3.4 Review UX design
- 3.5 Prepare frontend implementation specifications

### WBS 4.0 — System Development

- 4.1 Set up React Native application
- 4.2 Set up NestJS backend
- 4.3 Design PostgreSQL database
- 4.4 Implement authentication
- 4.5 Implement profiles and questionnaires
- 4.6 Prepare ML training data
- 4.7 Train and evaluate candidate ML models
- 4.8 Implement recommendation API
- 4.9 Integrate mobile frontend and backend

### WBS 5.0 — Testing and Evaluation

- 5.1 Functional testing
- 5.2 API and database testing
- 5.3 ML performance evaluation
- 5.4 Baseline comparison
- 5.5 Usability testing
- 5.6 Security and privacy testing
- 5.7 Defect resolution

### WBS 6.0 — Project Delivery

- 6.1 Pre-Defense 1 preparation
- 6.2 Supervisor feedback processing
- 6.3 Subsequent pre-defense preparation
- 6.4 Final documentation
- 6.5 Final demonstration and defense

## 7. YouTrack Task Management

The project is managed using the RMM project in YouTrack.

**YouTrack Project:** [https://ayanshayan.youtrack.cloud/projects/RMM](https://ayanshayan.youtrack.cloud/projects/RMM)

The initial planning tasks are:

| Task ID | Task                             | Owner    | Expected Deliverable                  |
| ------- | -------------------------------- | -------- | ------------------------------------- |
| RMM-1   | Project Proposal                 | Ayan     | Project proposal                      |
| RMM-2   | Student Interviews               | Ayan     | Interview findings                    |
| RMM-3   | Literature Review                | Mirasbek | Review, matrix, and bibliography      |
| RMM-4   | Existing Systems Comparison      | Ayan     | Comparative analysis                  |
| RMM-5   | Technology Comparison            | Mirasbek | Technology selection document         |
| RMM-6   | ML Research and Design           | Mirasbek | ML model design                       |
| RMM-7   | Requirements Specification       | Ayan     | SRS                                   |
| RMM-8   | Architecture and Diagrams        | Mirasbek | Architecture description and diagrams |
| RMM-9   | Figma UX Prototype               | Ayan     | Interactive mobile prototype          |
| RMM-10  | Verification and Evaluation Plan | Mirasbek | Testing and evaluation plan           |
| RMM-11  | Project Management and Risks     | Ayan     | Project management plan               |
| RMM-12  | Supervisor Feedback              | Ayan     | Feedback and revision records         |

The official status of each task is maintained in YouTrack.

Documentation completion does not automatically mean that implementation or evaluation has been completed.

### 7.1. Task Statuses

The project workflow uses:

- **Open:** Work has not started.
- **In Progress:** Work is being completed.
- **In Review:** The deliverable is awaiting review.
- **Done:** The task's acceptance criteria have been met.
- **Blocked:** Progress depends on an unresolved issue.

These status definitions describe the intended workflow. Actual available status values depend on the project's YouTrack configuration.

## 8. Project Milestones

The project is organized around academic deliverables and development milestones.

| Milestone                          | Planned Period          | Expected Outcome                                  |
| ---------------------------------- | ----------------------- | ------------------------------------------------- |
| M1 — Problem and Research          | October 2026            | Proposal, interviews, literature review           |
| M2 — Requirements and Architecture | October 2026            | SRS, technology decisions, diagrams               |
| M3 — UX Prototype                  | October 2026            | Interactive Figma prototype                       |
| M4 — Pre-Defense 1                 | October 24, 2026        | Research and design evidence presented            |
| M5 — Development Foundation        | Following Pre-Defense 1 | Mobile, backend, and database foundations         |
| M6 — ML Dataset and Experiments    | Implementation phase    | Labeled data, trained models, baseline evaluation |
| M7 — Integrated Prototype          | Integration phase       | Mobile application with ML recommendations        |
| M8 — System Evaluation             | Testing phase           | Functional, ML, usability, and security evidence  |
| M9 — Final Preparation             | Before final defense    | Refined system, documentation, and demonstration  |

Dates beyond Pre-Defense 1 will be updated after the university confirms the remaining academic schedule and the supervisor reviews the plan.

## 9. Dependencies and Critical Activities

Several activities depend on the completion of earlier work.

| Activity                      | Dependency                            | Main Concern                  |
| ----------------------------- | ------------------------------------- | ----------------------------- |
| Mobile interface development  | Figma prototype and SRS               | UI implementation consistency |
| Backend implementation        | Architecture and database design      | API stability                 |
| ML data collection            | Questionnaire and labeling procedure  | Data quality and privacy      |
| ML model training             | Sufficient labeled data               | Model feasibility             |
| ML service integration        | Trained model and prediction contract | Component compatibility       |
| Recommendation UI integration | Backend recommendation API            | Data format consistency       |
| Model evaluation              | Labeled test data and baseline        | Valid comparison              |
| Final demonstration           | Integrated and tested system          | End-to-end reliability        |

### 9.1. Critical ML Dependency

The most important technical dependency is the availability of appropriate labeled roommate compatibility data.

The five exploratory student interviews conducted on October 18, 2026, support requirements analysis but do not provide enough labeled examples for supervised ML training.

A separate collection and labeling process must therefore be defined and implemented before meaningful model evaluation.

A delay in obtaining usable training data could affect the ML model, backend integration, recommendations, testing, and final demonstration.

### 9.2. Proposed Dependency Sequence

Research and Requirements
→ Questionnaire Design
→ Data Collection and Labeling
→ ML Model Training
→ ML Service Integration
→ Mobile Recommendations
→ System Testing
→ Final Demonstration

Frontend development, backend setup, and data collection can proceed in parallel where dependencies allow.

This is a preliminary dependency sequence rather than a formally calculated critical path.

## 10. GitHub Collaboration Strategy

**Repository:** [https://github.com/AyanShayan/roommate-matching-app](https://github.com/AyanShayan/roommate-matching-app)

The repository is used to maintain project documentation, source code, diagrams, and development history.

### 10.1. Branching Strategy

The main branch is used for reviewed and accepted work.

Each task is developed on a separate branch.

Examples:

- `RMM-7-software-requirements`
- `RMM-8-system-architecture`
- `RMM-9-ux-prototype`
- `RMM-10-verification-plan`
- `RMM-11-project-management`

### 10.2. Commit Messages

Commit messages should include the relevant task identifier.

Example:

`RMM-11: Add project management and risk assessment`

Commits should reflect actual development activities.

The team will not artificially modify commit timestamps to create an inaccurate project history.

### 10.3. Pull Request Reviews

Each developer reviews the other developer's contributions.

Review checks include:

- Alignment with project requirements.
- Correctness and completeness.
- Naming and formatting consistency.
- Appropriate documentation.
- Potential security or privacy concerns.
- Possible conflicts with existing changes.

Approved changes are merged into the main branch.

### 10.4. Repository Quality

The repository should contain:

- An up-to-date README.
- Project documentation.
- Editable diagram sources.
- Figma prototype references.
- Source code as implementation progresses.
- Setup instructions.
- Example configuration files without secrets.
- Evidence of reviewed contributions.

The team plans to create the `pre-defense-1` Git tag after verifying the submission state.

Future tags will correspond to subsequent academic milestones.

## 11. Communication and Coordination

The two developers will coordinate regularly throughout the project.

### 11.1. Communication Practices

The proposed workflow includes:

- Brief progress discussions several times per week.
- YouTrack updates when tasks change status.
- GitHub Pull Request reviews before merging.
- Shared discussions about technical dependencies.
- Supervisor consultations at academic milestones.

### 11.2. Progress Monitoring

Progress will be monitored through:

- Completed YouTrack tasks.
- Open and merged Pull Requests.
- Identified blockers.
- Upcoming milestones.
- Test results when implementation begins.
- Outstanding supervisor comments.

If a task is delayed, the team will reassess its dependencies, priority, and possible effect on the next milestone.

## 12. Risk Assessment Method

The project uses a qualitative risk assessment supported by a simple numerical scoring system.

Each risk is evaluated by:

- **Probability (P):** From 1 (very unlikely) to 5 (very likely).
- **Impact (I):** From 1 (minor) to 5 (critical).
- **Risk Score:** Probability × Impact.

### Risk Levels

| Score | Risk Level | Response                                   |
| ----- | ---------- | ------------------------------------------ |
| 1–5   | Low        | Monitor                                    |
| 6–12  | Medium     | Plan mitigation                            |
| 13–25 | High       | Prioritize mitigation and close monitoring |

The ratings below are preliminary team estimates, not measured probabilities.

## 13. Project Risk Register

| ID  | Risk                                             |  P |  I |       Score | Mitigation Strategy                                                                                                      | Owner    |
| --- | ------------------------------------------------ | -: | -: | ----------: | ------------------------------------------------------------------------------------------------------------------------ | -------- |
| R01 | Insufficient labeled ML data                     |  4 |  5 |   20 — High | Start data collection planning early, verify labeling quality, and discuss feasible dataset requirements with supervisor | Mirasbek |
| R02 | ML model performs poorly                         |  3 |  5 |   15 — High | Compare multiple models, evaluate data quality, use a baseline, and report limitations                                   | Mirasbek |
| R03 | Delays caused by limited team size               |  4 |  4 |   16 — High | Prioritize Must Have functionality and review progress regularly                                                         | Both     |
| R04 | Backend and frontend integration issues          |  3 |  4 | 12 — Medium | Define API contracts early and implement integration tests                                                               | Both     |
| R05 | User privacy or data security problems           |  3 |  5 |   15 — High | Apply data minimization, authentication, authorization, and secure storage practices                                     | Both     |
| R06 | Poor mobile user experience                      |  3 |  3 |  9 — Medium | Validate the Figma prototype and conduct usability testing                                                               | Ayan     |
| R07 | Inaccurate or incomplete questionnaire responses |  4 |  4 |   16 — High | Use clear questions, validation rules, and transparent model limitations                                                 | Both     |
| R08 | Changes requested by supervisor                  |  4 |  3 | 12 — Medium | Record feedback, prioritize changes, and revise planning documents                                                       | Both     |
| R09 | Limited device or hosting resources              |  3 |  3 |  9 — Medium | Use development environments, control infrastructure scope, and test on available devices                                | Both     |
| R10 | Git conflicts or inconsistent contributions      |  3 |  3 |  9 — Medium | Use task branches, Pull Requests, and peer reviews                                                                       | Both     |
| R11 | Incomplete research source verification          |  3 |  4 | 12 — Medium | Verify article metadata, accessible full texts, and Scopus records before final submission                               | Mirasbek |
| R12 | Insufficient time for testing                    |  4 |  4 |   16 — High | Prepare test cases early, automate core checks, and reserve a stabilization period                                       | Both     |

## 14. High-Priority Risk Response Plans

### R01 — Insufficient Labeled ML Data

**Potential Consequence:** The team may be unable to train or validate a meaningful supervised compatibility model.

**Mitigation:** Define a realistic data collection procedure, obtain appropriate consent, and collect pairwise compatibility labels.

**Contingency:** Use synthetic data only for software pipeline demonstrations, clearly state that it does not establish real prediction performance, and revise the research claims and model scope with supervisor approval.

### R02 — Poor ML Model Performance

**Potential Consequence:** Machine Learning may not improve recommendations over simpler matching rules.

**Mitigation:** Evaluate Logistic Regression, Random Forest, and Gradient Boosting using appropriate data splitting and consistent metrics.

**Contingency:** Retain the actual trained ML component, report its measured limitations, compare it honestly with the baseline, and reconsider features or data quality.

### R03 — Development Delays

**Potential Consequence:** Important functionality may be unfinished at academic milestones.

**Mitigation:** Focus on essential requirements, split tasks into manageable units, and track blockers through YouTrack.

**Contingency:** Postpone Could Have and Should Have features while preserving the essential matching and evaluation workflow.

### R05 — Privacy and Security

**Potential Consequence:** Student information may be disclosed improperly.

**Mitigation:** Limit data collection, apply role-based access controls where appropriate, and keep credentials out of the repository.

**Contingency:** Disable affected functionality, investigate the issue, and correct it before further testing with real participant data.

### R12 — Insufficient Testing Time

**Potential Consequence:** The final demonstration may include significant defects or unvalidated predictions.

**Mitigation:** Prepare test scenarios before implementation and conduct tests incrementally.

**Contingency:** Freeze optional feature development, prioritize core workflow stability, and document unresolved limitations.

## 15. Quality Assurance Plan

The project will use documentation reviews, code reviews, automated tests, and manual validation.

### Research and Documentation Quality

- Validate important academic claims against the original publications.
- Confirm bibliography information and required indexing.
- Keep conclusions consistent with available evidence.
- Maintain references between documents.
- Incorporate supervisor feedback.

### Software Quality

- Follow consistent coding conventions.
- Validate application inputs.
- Review significant code changes.
- Maintain modular source structure.
- Add appropriate unit and integration tests.
- Track defects in YouTrack.

### Machine Learning Quality

- Define the training labels clearly.
- Record dataset size and limitations.
- Prevent training/test data leakage.
- Compare trained models with a rule-based baseline.
- Report appropriate metrics.
- Avoid presenting demonstration scores as real model results.

### User Experience Quality

- Maintain consistent navigation and interface design.
- Test key mobile user flows.
- Record usability feedback.
- Resolve critical usability problems before the final demonstration.

## 16. Pre-Defense 1 Deliverables

The planned Pre-Defense 1 submission includes:

| Deliverable                      | Related Task | Evidence                              |
| -------------------------------- | ------------ | ------------------------------------- |
| Project Proposal                 | RMM-1        | Proposal document                     |
| Student Interviews               | RMM-2        | Anonymized interview findings         |
| Literature Review                | RMM-3        | Literature review, matrix, references |
| Existing Systems Comparison      | RMM-4        | Comparison document                   |
| Technology Comparison            | RMM-5        | Technology selection analysis         |
| ML Research and Design           | RMM-6        | ML design document                    |
| Requirements Specification       | RMM-7        | SRS                                   |
| Architecture and Diagrams        | RMM-8        | Context, Use Case, Component diagrams |
| Interactive UX Prototype         | RMM-9        | Figma prototype                       |
| Verification and Evaluation Plan | RMM-10       | Testing and evaluation plan           |
| Project Management and Risks     | RMM-11       | This document                         |
| Supervisor Feedback              | RMM-12       | Feedback and revision records         |

**Pre-Defense 1 Date:** October 24, 2026.

The final submission must be reviewed against university requirements and confirmed with the supervisor.

## 17. Pre-Defense 1 Readiness Checklist

The following items must be confirmed before submission:

- [ ] All required documents are available in GitHub.
- [ ] Every required document has been reviewed.
- [ ] The literature matrix contains at least 12 meaningfully analyzed sources.
- [ ] Required academic source and indexing checks are complete.
- [ ] Three required system diagrams are available.
- [ ] Diagram source files remain editable.
- [ ] The Figma prototype link works for reviewers.
- [ ] The main prototype navigation works.
- [ ] Requirements contain priorities and acceptance criteria.
- [ ] Evaluation methods, metrics, conditions, and baselines are documented.
- [ ] Major project risks and dependencies are identified.
- [ ] Individual contributions can be traced through GitHub and YouTrack.
- [ ] Supervisor feedback is recorded when received.
- [ ] The `pre-defense-1` repository tag is created after the final submission review.

Unchecked items must not be reported as completed.

## 18. Change and Feedback Management

Requirements and technical decisions may change after supervisor discussions.

The team will maintain a feedback record containing:

- Date of feedback.
- Feedback source.
- Affected document or feature.
- Requested change.
- Responsible developer.
- Action taken.
- Associated GitHub Pull Request or commit.
- Final review status.

Changes that affect the core scope, ML approach, or academic evaluation will be discussed with the supervisor before implementation.

## 19. Expected Outcomes

Successful project management should result in:

1. Clear responsibility distribution between team members.
2. Traceable progress through GitHub and YouTrack.
3. Timely completion of academic deliverables.
4. Early identification of major project risks.
5. Controlled integration of frontend, backend, and ML components.
6. Reliable evidence for system verification and evaluation.
7. Documented supervisor feedback and revisions.

## 20. Conclusion

This project management plan defines the organization, responsibilities, work breakdown structure, dependencies, milestones, collaboration practices, and risk management strategy for the roommate matching application.

The project is being developed by two students with complementary responsibilities in mobile development, UI/UX, backend engineering, and Machine Learning.

GitHub and YouTrack provide traceability for task progress and individual contributions.

The most significant risks are insufficient labeled ML data, limited development time, model performance, and privacy concerns.

These risks will be monitored throughout implementation and evaluation.

The plan will be updated after supervisor feedback and as additional academic milestone dates are confirmed.

## 21. Project Resources

**GitHub Repository:**
[https://github.com/AyanShayan/roommate-matching-app](https://github.com/AyanShayan/roommate-matching-app)

**YouTrack Project:**
[https://ayanshayan.youtrack.cloud/projects/RMM](https://ayanshayan.youtrack.cloud/projects/RMM)

**Figma Prototype:**
https://www.figma.com/design/zVzAKw38CXKzEMXBPlZguu/RoommateMatch-%E2%80%94-Mobile-UX-Prototype--RMM-9-?node-id=0-1&t=N0rFL0120HBnz18P-1

**Software Requirements:**
`docs/requirements/software-requirements-specification.md`

**ML Model Design:**
`docs/ml-research/ml-model-design.md`

**Evaluation Plan:**
`docs/testing/verification-evaluation-plan.md`

**Document Status:** Draft prepared for Pre-Defense 1 review.
