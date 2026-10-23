# Supervisor Feedback and Revision Log

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Prepared by:** Ayan Matayev  
**Team Members:** Ayan Matayev, Mirasbek Idiatulla  
**Supervisor:** Tomiris Zhaksylyk  
**YouTrack Task:** RMM-12  
**Date:** October 23, 2026  
**Version:** 1.0  
**Status:** Open — Awaiting Final Pre-Defense 1 Feedback

---

## 1. Purpose

This document records academic supervisor feedback and the corresponding revisions made to the Roommate Matching Application project.

The purpose of the feedback log is to provide traceability between supervisor recommendations, technical decisions, assigned responsibilities, and project documentation.

The log will be updated after every relevant supervisor consultation.

Unconfirmed feedback and future actions will not be recorded as completed.

## 2. Project Overview

The project aims to develop a mobile application that helps university students find potentially compatible roommates based on lifestyle habits and accommodation preferences.

The proposed solution consists of:

- A React Native mobile application.
- A NestJS application backend.
- A PostgreSQL database.
- A Python-based Machine Learning component.
- A structured lifestyle questionnaire.
- ML-based roommate recommendations.
- Compatibility explanations and profile comparisons.

The first pre-defense focuses on research, documentation, system architecture, UX prototyping, and planning for future implementation.

## 3. Feedback Register

### FB-01 — Machine Learning Requirement

| Field | Details |
|---|---|
| Feedback ID | FB-01 |
| Feedback Source | Academic supervisor, as reported by the student team |
| Supervisor | Tomiris Zhaksylyk |
| Date Received | Not recorded |
| Topic | Roommate Matching Algorithm |
| Feedback | The roommate matching algorithm should use Machine Learning rather than rely exclusively on rule-based compatibility scoring. |
| Priority | High |
| Responsible Developer | Mirasbek Idiatulla |
| Supporting Developer | Ayan Matayev |
| Current Status | Reflected in project design; supervisor confirmation pending |

### 3.1. Interpretation

The project should include an actual supervised ML model for roommate compatibility prediction.

A weighted rule-based algorithm may be implemented as a baseline, but it should not replace the required Machine Learning component.

### 3.2. Actions Reflected in the Design

The following documents address this requirement:

1. Project Proposal — defines the ML-based roommate matching objective.
2. Literature Review — reviews recommendation and matching approaches.
3. Technology Comparison — evaluates ML technologies and algorithms.
4. ML Model Research and Design — defines the prediction task, features, data strategy, and candidate algorithms.
5. Software Requirements Specification — identifies ML compatibility prediction as a Must Have requirement.
6. System Architecture — includes the Python ML service.
7. Verification and Evaluation Plan — defines ML metrics and baseline comparison.

### 3.3. Proposed Technical Response

The team plans to:

- Collect appropriately labeled student-pair compatibility data.
- Prepare pairwise lifestyle features.
- Evaluate Logistic Regression, Random Forest, and Gradient Boosting.
- Compare trained models against a rule-based baseline.
- Select a model using experimental evidence.
- Integrate the chosen model into the application.
- Display recommendations and understandable compatibility information.

### 3.4. Remaining Work

- Obtain the required labeled training data.
- Train and evaluate candidate models.
- Validate recommendation quality.
- Integrate the ML model with the backend.
- Confirm that the implemented approach meets supervisor expectations.

**Revision Status:** Design response prepared; implementation and final supervisor verification pending.

## 4. Additional Supervisor Feedback

No additional specific supervisor comments have been documented in this log yet.

New feedback should be added using the following structure.

### FB-XX — Feedback Title

**Date Received:** To be recorded

**Source:** Supervisor meeting, email, or other confirmed communication

**Supervisor Comment:** Exact comment or faithful summary

**Affected Area:** Document, design, algorithm, or implementation

**Required Action:** Description of the requested revision

**Assigned Developer:** Ayan / Mirasbek

**Action Taken:** Record only after implementation or revision

**GitHub Evidence:** Pull Request or commit link

**Status:** Open / In Progress / Implemented / Verified

## 5. Revision Tracking Table

| Feedback ID | Affected Area | Planned or Documented Response | Evidence | Status |
|---|---|---|---|---|
| FB-01 | Matching algorithm | Include supervised ML in the proposed architecture and evaluation strategy | ML design, SRS, architecture, evaluation plan | Design documented; final review pending |
| — | Additional supervisor feedback | To be recorded when received | Pending | Not recorded |

## 6. Feedback Management Process

The team will use the following procedure:

1. Receive and record supervisor feedback.
2. Identify the affected documents or system components.
3. Evaluate the importance and scope of the requested change.
4. Assign the responsible developer.
5. Create or update a YouTrack task.
6. Make the necessary changes in a Git branch.
7. Submit changes through a Pull Request.
8. Conduct peer review.
9. Merge accepted changes.
10. Record the final evidence and supervisor confirmation when available.

This process ensures that revisions are traceable and can be demonstrated during academic reviews.

## 7. Pre-Defense 1 Review Topics

The following points should be presented to the supervisor for review:

| Topic | Question for Supervisor |
|---|---|
| Project scope | Is the proposed student-focused functionality appropriate for the graduation project? |
| ML approach | Is the proposed supervised compatibility prediction approach acceptable? |
| Training dataset | Is the planned pairwise data collection and labeling approach appropriate? |
| Literature review | Are the selected research areas and publications sufficient? |
| Requirements | Are the Must Have requirements realistic for the project? |
| Architecture | Is the separation of NestJS backend and Python ML service acceptable? |
| UX prototype | Does the Figma prototype demonstrate the expected user workflow? |
| Evaluation | Are the ML and usability evaluation methods sufficient? |

These are proposed review questions, not confirmed supervisor comments.

## 8. Evidence and Documentation

The project maintains evidence through GitHub, YouTrack, and design documentation.

**GitHub Repository:**  
https://github.com/AyanShayan/roommate-matching-app

**YouTrack Project:**  
https://ayanshayan.youtrack.cloud/projects/RMM

**Figma Prototype:**  
https://www.figma.com/design/zVzAKw38CXKzEMXBPlZguu/RoommateMatch-%E2%80%94-Mobile-UX-Prototype--RMM-9-?node-id=0-1&t=N0rFL0120HBnz18P-1

**Relevant Documentation:**

- `docs/proposal/project-proposal.md`
- `docs/ml-research/ml-model-design.md`
- `docs/requirements/software-requirements-specification.md`
- `docs/architecture/architecture-overview.md`
- `docs/testing/verification-evaluation-plan.md`

Supervisor correspondence or meeting notes may be referenced when appropriate. Private messages should not be uploaded to a public repository without permission.

## 9. Pre-Defense 1 Feedback Status

As of October 23, 2026:

- The team has documented the reported ML requirement.
- The planned ML approach has been incorporated into the design documents.
- The application remains in the design and research phase.
- Formal confirmation of the final design from the supervisor has not been recorded in this document.
- Additional feedback and required revisions will be added when available.

## 10. Next Actions

Before or during Pre-Defense 1, the team should:

1. Share the current proposal and supporting documentation with the supervisor.
2. Demonstrate the interactive Figma prototype.
3. Explain the planned ML matching approach and dataset strategy.
4. Request comments on the architecture and evaluation plan.
5. Record actual feedback with dates and evidence.
6. Create revision tasks for any required changes.
7. Update this document after receiving feedback.

## 11. Conclusion

This document establishes a structured process for recording supervisor feedback and project revisions.

One previously reported requirement has been documented: the roommate matching algorithm must use Machine Learning.

The team has incorporated this requirement into the proposed technical design and evaluation strategy.

The feedback log will remain open until additional supervisor comments are recorded and required revisions are reviewed.

**Document Status:** Initial feedback log prepared; final supervisor review pending.
