# Student Interviews — Findings and Requirements Analysis

## 1. Introduction

**Project:** Development of a Compatibility-Based Roommate Matching Application for University Students

**Date of Interviews:** October 18, 2026

**Interviewers:** Ayan Matayev and Mirasbek Idiatulla

**Number of Participants:** 5 university students

**Research Method:** Qualitative semi-structured interviews conducted through online messaging.

### Research Objective

The purpose of these interviews was to understand the challenges university students experience when searching for roommates and sharing accommodation.

The research also explored which lifestyle characteristics students consider important, what functions they would expect from a mobile roommate-matching application, and their attitudes toward machine learning-based recommendations.

## 2. Methodology

Five students participated in individual text-based interviews.

Four participants had previous or current experience living with roommates, while one participant had not yet shared accommodation but planned to do so in the future.

The interview questions focused on:

- Previous roommate experiences.
- Roommate selection methods.
- Conflicts and lifestyle differences.
- Important compatibility factors.
- Unacceptable roommate behaviors.
- Expectations for a mobile matching application.
- Privacy concerns.
- Trust in machine learning-based recommendations.

Participants are identified as P1–P5 to protect their identities.

The interview format was flexible, and not every participant was asked every question in exactly the same wording. In particular, P3 was not directly asked about willingness to complete the lifestyle questionnaire.

## 3. Individual Interview Findings

### Participant P1 — Previous Dormitory Experience

P1 lived in a university dormitory with two roommates. One relationship was positive, while the other involved recurring conflicts.

The main problems included excessive noise from gaming, different sleep schedules, and disagreements about shared responsibilities.

P1 identified cleanliness, personal space, and sleep schedules as important roommate compatibility factors.

The participant supported the idea of a lifestyle questionnaire and suggested compatibility percentages, preference filters, messaging, and explanations of matching results.

P1 expressed approximately 70% personal confidence in ML-based recommendations but emphasized the importance of communicating with a potential roommate before making a decision.

Privacy concerns included exact addresses, identity documents, and income information.

### Participant P2 — Generally Positive Roommate Experience

P2 had lived in a university dormitory for approximately one and a half years.

The participant found a roommate through a university student group chat and reported a generally positive living experience.

Minor disagreements occurred regarding room temperature and ventilation.

P2 emphasized communication, compromise, respect, and the ability to resolve problems.

Suggested application features included matching by interests, habits, and university, as well as messaging and saving preferred profiles.

P2 also wanted to see both similarities and potential differences between candidates.

The participant was willing to complete a detailed questionnaire but preferred not to share private messages or family information.

### Participant P3 — Prospective Roommate Seeker

P3 had not previously lived with roommates but was considering renting an apartment with another student.

The participant expressed concerns about personal safety, trustworthiness, noise, and whether people accurately describe their habits.

Important characteristics included honesty, a calm lifestyle, respect, and similar daily routines.

Suggested application features included university-based search, compatibility percentages, messaging, prioritization of personal preferences, and comparison of candidates.

P3 expressed approximately 50% personal trust in ML-generated recommendations. The participant suggested that detailed explanations and verified questionnaires could improve confidence.

No direct answer about willingness to complete a lifestyle questionnaire was collected from P3.

### Participant P4 — Shared Apartment Experience

P4 previously rented an apartment with a university friend.

Although their friendship was positive, sharing accommodation created disagreements about cleaning, guests, personal boundaries, and household responsibilities.

The participant emphasized responsibility, cleanliness, communication, and the ability to keep agreements.

Suggested application features included budget filters, location preferences, lifestyle filters, student-status verification, and reporting suspicious profiles.

P4 supported completing a lifestyle questionnaire but preferred not to publicly share phone numbers or exact residential locations.

The participant considered ML recommendations useful for the initial selection process but believed that personal communication was still necessary.

### Participant P5 — Unsuccessful Shared Accommodation Experience

P5 previously rented an apartment with another student. The arrangement ended because of problems involving shared expenses and cleaning responsibilities.

The participant emphasized financial responsibility, honesty, and respect for shared living agreements.

Suggested features included student verification, budget filters, optional references from previous roommates, blocking users, and showing when users were ready to move in.

P5 was willing to complete a short questionnaire but did not want to provide unnecessary personal information.

The participant expressed skepticism about ML compatibility percentages because users could provide inaccurate questionnaire answers.

Verified profiles, understandable recommendations, and personal communication were identified as ways to increase trust.

## 4. Cross-Participant Analysis

| Research Topic | Main Findings | Evidence |
|---|---|---|
| Roommate experience | Four students had lived with roommates; one was a prospective roommate seeker | P1–P5 |
| Noise and sleep | Different schedules and excessive noise were important concerns | P1, P3 |
| Cleanliness and responsibilities | Cleaning habits and shared duties caused or could cause disagreements | P1, P4, P5 |
| Financial responsibility | Shared expenses and timely payments were important concerns | P4, P5 |
| Communication | Participants emphasized discussing expectations and communicating before deciding | P1, P2, P3, P4, P5 |
| Trust and verification | Participants identified uncertainty about other users and requested ways to improve trust | P3, P4, P5 |
| Messaging | In-app communication was explicitly requested | P1, P2, P3 |
| Transparent matching | Explanations of recommendations were considered valuable | P1, P3, P5 |
| Privacy | Participants expressed concerns about revealing unnecessary personal information | P1, P2, P4, P5 |
| Questionnaire acceptance | All four participants directly asked about willingness agreed, with different preferences regarding questionnaire length | P1, P2, P4, P5 |

## 5. Key Findings

### Finding 1: Lifestyle Compatibility Matters

The interviews showed that compatible daily routines and household expectations are important in shared accommodation.

Sleep schedules, cleanliness, noise tolerance, and personal boundaries were repeatedly mentioned.

**Design implication:** The application should include a structured lifestyle questionnaire.

### Finding 2: Students Need More Information Before Choosing

Several participants reported that initial conversations did not provide enough information about future roommates.

**Design implication:** Student profiles should present relevant accommodation preferences and lifestyle characteristics.

### Finding 3: ML Recommendations Should Be Explainable

Participants were interested in compatibility recommendations but did not view percentages as guarantees of successful relationships.

**Design implication:** The application should display interpretable explanations of compatibility factors alongside the model-generated results.

### Finding 4: Trust and Privacy Are Important

Participants expressed concerns about false information, personal safety, and sharing sensitive data.

**Design implication:** The application should minimize unnecessary personal data collection and consider profile verification, reporting, and blocking features.

### Finding 5: Personal Communication Remains Necessary

All five participants described communication as important for evaluating potential roommates or resolving compatibility uncertainties.

**Design implication:** The system should help students make informed decisions instead of automatically deciding who must live together. Contact or messaging functionality should be considered in the development roadmap.

## 6. Requirements Derived from Interviews

| ID | Proposed Requirement | Priority | Evidence |
|---|---|---|---|
| FR-01 | Students should be able to complete a lifestyle compatibility questionnaire | Must Have | P1, P2, P4, P5 |
| FR-02 | The application should provide ML-based roommate recommendations | Must Have | Project objective; interview discussion |
| FR-03 | Users should be able to view important compatibility factors | Must Have | P1, P2, P3, P5 |
| FR-04 | Users should be able to filter candidates by relevant preferences | Must Have | P1, P3, P4, P5 |
| FR-05 | Students should be able to view candidate profiles before making decisions | Must Have | P1–P5 |
| FR-06 | The application should offer a way for users to contact suitable candidates | Should Have | P1, P2, P3; broader communication needs |
| FR-07 | Users should be able to save or compare candidates | Should Have | P2, P3 |
| FR-08 | The application should support student-status verification | Should Have | P4, P5 |
| FR-09 | Users should be able to report or block suspicious profiles | Should Have | P4, P5 |
| NFR-01 | Unnecessary personal information should not be collected or publicly displayed | Must Have | P1, P2, P4, P5 |
| NFR-02 | ML recommendation results should be understandable to users | Must Have | P1, P3, P5 |

These requirements are preliminary and should be reconciled with the main Software Requirements Specification.

## 7. Implications for Machine Learning

The interviews suggest several potential input features for a roommate compatibility model:

| Feature | Possible Representation |
|---|---|
| Sleep schedule | Preferred sleeping and waking times |
| Cleanliness | Self-reported cleanliness preferences |
| Noise tolerance | Ordinal preference scale |
| Guest preferences | Frequency and acceptability of visitors |
| Smoking preferences | Compatibility restriction |
| Study environment | Preferred quiet or shared study conditions |
| Budget | Acceptable accommodation cost range |
| Shared responsibilities | Expectations about cleaning and expenses |
| Communication preferences | Preferred ways of resolving disagreements |

These are candidate features, not a finalized training dataset.

Compatibility labels must be collected separately through a suitable supervised learning data collection procedure.

The five qualitative interviews are useful for identifying requirements and potential features, but they are not sufficient for training or validating a reliable ML model.

## 8. Research Limitations

This research has several limitations:

1. The sample includes only five participants.
2. Participants were recruited through a small convenience sample.
3. Four participants had roommate experience, while one provided expectations rather than firsthand roommate experience.
4. Interviews were conducted through text messaging, limiting opportunities for spontaneous follow-up discussion.
5. Not all participants were asked exactly the same questions.
6. Questions introducing the proposed ML solution may have influenced responses about its usefulness.
7. Self-reported experiences and preferences have not been independently verified.

The findings should therefore be treated as exploratory qualitative evidence rather than representative conclusions about all university students.

The participants' stated trust percentages are individual opinions, not measurements of ML model accuracy.

## 9. Conclusion

The five interviews provided initial evidence that roommate selection involves more than finding available accommodation.

Students described difficulties related to lifestyle differences, shared responsibilities, communication, trust, and the lack of information about potential roommates.

The findings support the proposed direction of developing a mobile roommate-matching application with lifestyle questionnaires, ML-based recommendations, understandable matching results, and privacy-conscious profile management.

Future work will involve validating these requirements with a larger sample, designing a labeled dataset for supervised machine learning, and evaluating the resulting recommendations against a baseline method.

**Research Status:** Initial user interviews completed; findings prepared for team and supervisor review.
