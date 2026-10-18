
# Literature Review Matrix

**Project Title:** Development of a Compatibility-Based Roommate Matching Application for University Students

**Team Members:**
- Ayan Matayev — Mobile Frontend & UI/UX
- Mirasbek Idiatulla — Backend & Machine Learning

**Supervisor:** Tomiris Zhaksylyk  
**Review Period:** 2022–2025  
**Number of Sources:** 12 scientific publications

## 1. Introduction

This literature review examines existing research related to roommate relationships, student accommodation, matching algorithms, machine learning-based recommendations, mobile application usability, and data privacy. The purpose is to identify relevant findings, compare research approaches, and determine how existing knowledge can support the development of a mobile roommate matching application for university students.

The literature is organized into five categories:

- Roommate Relationships and Student Housing
- Roommate Matching and Allocation
- Machine Learning and Recommendation Systems
- Mobile Application and User Experience
- Privacy and Security

## 2. Literature Review Matrix

### Category A: Roommate Relationships and Student Housing

| ID | Authors & Year | Research Objective | Methodology | Key Findings | Limitations | Relevance to Our Project |
|---|---|---|---|---|---|---|
| S01 | Willis & Lane (2022) | Examine the reliability and validity of the Roommate Relationship Scale among college students. | Longitudinal quantitative study using exploratory and confirmatory factor analyses. | The study provides preliminary evidence that the scale can measure roommate relationship quality reliably. | The study evaluates an assessment instrument rather than a roommate prediction algorithm. | Helps define how roommate relationship satisfaction could be measured during application evaluation. |
| S02 | Abela, Sharma & Law (2024) | Investigate roommate conflict management, bullying, victimization, and social support. | Mixed-method study involving 804 undergraduate students, regression analysis, and thematic analysis. | Household disagreements, communication difficulties, and conflict management strategies were associated with roommate experiences. | Self-reported conflict experiences and a particular student sample limit generalization. | Supports including household responsibilities, noise, communication, and conflict expectations in the questionnaire. |
| S03 | Cao, Zhou & Gao (2024) | Investigate how roommate peer effects influence university students' academic performance. | Longitudinal analysis of 5,272 students using null models and regression methods. | Students sharing accommodation showed academic-performance similarities beyond those expected by chance, with peer effects changing over time. | Academic performance is not the same as personal roommate compatibility. | Demonstrates that roommate relationships can influence important aspects of university life. |

**Source Links**

**S01 — Willis & Lane (2022)**
- Article: https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2022.960421/full
- DOI: https://doi.org/10.3389/fpsyg.2022.960421
- Free PDF: https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2022.960421/pdf

**S02 — Abela, Sharma & Law (2024)**
- Article: https://journals.sagepub.com/doi/full/10.1177/21676968231216512
- DOI: https://doi.org/10.1177/21676968231216512
- Free full text: Available through the open-access publisher article page; use the publisher's PDF download option.

**S03 — Cao, Zhou & Gao (2024)**
- Article: https://www.nature.com/articles/s41467-024-49228-7
- DOI: https://doi.org/10.1038/s41467-024-49228-7
- Free PDF: https://www.nature.com/articles/s41467-024-49228-7.pdf

### Category B: Roommate Matching and Allocation

| ID | Authors & Year | Research Objective | Methodology | Key Findings | Limitations | Relevance to Our Project |
|---|---|---|---|---|---|---|
| S04 | Bonifaci & Rivera Dallorto (2025) | Investigate fair and stable roommate allocation under student preferences. | Mathematical optimization, computational complexity analysis, and stability analysis. | Several roommate allocation problems are computationally difficult, while weaker stability conditions can be achieved efficiently. | Theoretical allocation models do not directly predict lifestyle compatibility from questionnaires. | Provides a foundation for understanding matching constraints, fairness, and stable assignments. |
| S05 | Afacan (2024) | Develop mechanisms for assigning students to colleges and dormitories simultaneously. | Mathematical matching model using deferred acceptance mechanisms. | The proposed mechanisms address stable and efficient college-dorm assignment and examine student-optimality. | Focuses on institutional allocation rather than matching individual roommates by habits. | Useful for comparing traditional allocation approaches with personalized roommate recommendations. |
| S06 | Yang et al. (2024) | Improve reciprocal recommendation by considering outcomes for both parties. | Causal reciprocal recommendation framework, new evaluation metrics, reranking, and experiments on recruitment and dating datasets. | Bilateral evaluation and reranking can improve the assessment of reciprocal recommendations. | Experiments were not conducted specifically on roommate matching datasets. | Supports designing recommendations that consider the preferences of both students. |

**Source Links**

**S04 — Bonifaci & Rivera Dallorto (2025)**
- Article: https://www.sciencedirect.com/science/article/pii/S0304397524006261
- DOI: https://doi.org/10.1016/j.tcs.2024.115009
- Free PDF: https://ricerca.matfis.uniroma3.it/users/vbonifaci/pub/roommate-tcs.pdf

**S05 — Afacan (2024)**
- Article: https://link.springer.com/article/10.1007/s00355-024-01510-9
- DOI: https://doi.org/10.1007/s00355-024-01510-9
- Free PDF: https://link.springer.com/content/pdf/10.1007/s00355-024-01510-9.pdf

**S06 — Yang et al. (2024)**
- Article: https://arxiv.org/abs/2408.09748
- DOI: https://doi.org/10.1145/3637528.3671734
- Free PDF: https://arxiv.org/pdf/2408.09748

### Category C: Machine Learning and Recommendation Systems

| ID | Authors & Year | Research Objective | Methodology | Key Findings | Limitations | Relevance to Our Project |
|---|---|---|---|---|---|---|
| S07 | Uta et al. (2024) | Review knowledge-based recommendation techniques and future research directions. | Literature review of case-based, constraint-based, and knowledge-based recommendation approaches. | Explicit preferences and domain constraints are important for recommendations involving complex decisions. | Knowledge-based approaches require predefined domain knowledge and constraints. | Supports designing a lifestyle questionnaire and combining mandatory constraints with an ML model. |
| S08 | Jannach & Abdollahpouri (2023) | Review systems that optimize multiple recommendation objectives. | Scientific survey of multi-objective and multistakeholder recommendation approaches. | Optimizing recommendation accuracy alone may be insufficient when objectives and stakeholder interests conflict. | The survey does not provide a roommate-specific model. | Supports balancing ML compatibility predictions, personal preferences, and accommodation constraints. |
| S09 | Govea, Gutierrez & Villegas-Ch (2024) | Evaluate the effect of explainability methods on recommendation transparency and precision. | Experimental comparison of recommendation approaches incorporating explainability techniques such as LIME and SHAP. | The study reported improved transparency and a precision increase of up to 3% under its experimental conditions. | Results from other recommendation domains may not generalize to roommate compatibility. | Supports providing understandable explanations alongside ML-based compatibility results. |

**Source Links**

**S07 — Uta et al. (2024)**
- Article: https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2024.1304439/full
- DOI: https://doi.org/10.3389/fdata.2024.1304439
- Free PDF: https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2024.1304439/pdf

**S08 — Jannach & Abdollahpouri (2023)**
- Article: https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2023.1157899/full
- DOI: https://doi.org/10.3389/fdata.2023.1157899
- Free PDF: https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2023.1157899/pdf

**S09 — Govea et al. (2024)**
- Article: https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2024.1410790/full
- DOI: https://doi.org/10.3389/frai.2024.1410790
- Free PDF: https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2024.1410790/pdf

### Category D: Mobile Application and User Experience

| ID | Authors & Year | Research Objective | Methodology | Key Findings | Limitations | Relevance to Our Project |
|---|---|---|---|---|---|---|
| S10 | Weichbroth (2024) | Develop a methodological framework for evaluating mobile application usability. | Methodological research on usability testing and evaluation procedures. | A structured usability evaluation process helps assess mobile application quality and user interaction. | A general framework does not provide roommate-specific usability requirements. | Supports planning usability tests for registration, questionnaires, and recommendation screens. |
| S11 | Rezaee et al. (2024) | Design and evaluate a mobile self-care application using a user-centered approach. | Applied development study involving interviews, application design, and usability evaluation. | Demonstrates the use of user involvement and usability assessment in mobile application development. | The application addresses adolescent self-care rather than student housing. | Provides a methodological example for developing and testing a student-centered mobile interface. |

**Source Links**

**S10 — Weichbroth (2024)**
- Article: https://www.mdpi.com/2076-3417/14/5/1792
- DOI: https://doi.org/10.3390/app14051792
- Free PDF: https://www.mdpi.com/2076-3417/14/5/1792/pdf

**S11 — Rezaee et al. (2024)**
- Article: https://link.springer.com/article/10.1186/s12889-024-18341-z
- DOI: https://doi.org/10.1186/s12889-024-18341-z
- Free PDF: https://bmcpublichealth.biomedcentral.com/counter/pdf/10.1186/s12889-024-18341-z

### Category E: Privacy and Security

| ID | Authors & Year | Research Objective | Methodology | Key Findings | Limitations | Relevance to Our Project |
|---|---|---|---|---|---|---|
| S12 | Saeed (2024) | Investigate mobile users' perceptions of privacy and security controls. | Empirical research examining user perceptions of privacy and security in mobile applications. | The study highlights the importance of aligning security and privacy controls with users' expectations and understanding. | The participant context is geographically specific and not focused on roommate matching. | Supports minimizing sensitive data collection and designing understandable privacy controls. |

**Source Links**

**S12 — Saeed (2024)**
- Article: https://www.mdpi.com/2504-2289/8/11/162
- DOI: https://doi.org/10.3390/bdcc8110162
- Free PDF: https://www.mdpi.com/2504-2289/8/11/162/pdf

## 3. Comparative Analysis

The reviewed publications address different aspects of the proposed roommate matching application.

Studies S01–S03 demonstrate the importance of roommate relationships and the consequences of shared accommodation for university students. They provide a foundation for understanding roommate experiences and designing meaningful user requirements.

Studies S04–S06 investigate matching and allocation problems. These publications indicate that successful matching involves not only preference similarity but also fairness, stability, and mutual acceptance.

Studies S07–S09 examine recommendation technologies. They suggest that student preferences, mandatory restrictions, multiple evaluation objectives, and understandable explanations should be considered when designing the recommendation system.

Studies S10–S11 provide methodological guidance for designing and evaluating usable mobile applications.

Study S12 emphasizes privacy and security from the user's perspective, supporting careful handling of student profile information.

Taken together, these studies suggest that effective roommate matching requires a combination of social understanding, recommendation algorithms, usability, and data protection.

## 4. Research Gaps

The following gaps are relevant to the proposed project:

### Gap 1: Limited integration of lifestyle preferences and ML-based matching

The selected literature does not demonstrate a complete, validated mobile roommate matching system using the proposed student lifestyle questionnaire and supervised ML model.

### Gap 2: Limited data for new recommendation systems

New applications may not have sufficient historical interactions. Therefore, the project needs a strategy for collecting meaningful compatibility labels.

### Gap 3: Reciprocal compatibility

Both students should find the suggested roommate acceptable. A one-sided recommendation score may not fully represent this requirement.

### Gap 4: Explainability

A numerical compatibility result does not explain why two students might be suitable roommates. Clear explanations need to be evaluated with actual users.

### Gap 5: Privacy and trust

Roommate applications may involve sensitive lifestyle and accommodation information. Privacy must be considered during both system design and model development.

### Gap 6: Model validation

A compatibility prediction model must be evaluated using appropriate independent data and compared with a baseline approach. High prediction accuracy alone does not establish successful real-world roommate relationships.

These gaps represent opportunities for the proposed project rather than proof that no other roommate matching solutions exist.

## 5. Implications for Our Project

- Develop a lifestyle questionnaire informed by roommate-related research and student interviews.
- Include preferences related to sleep, cleanliness, noise, shared responsibilities, and accommodation restrictions.
- Investigate supervised machine learning for predicting pairwise compatibility.
- Consider reciprocal preferences in the recommendation process.
- Compare the ML model against a rule-based baseline.
- Display meaningful compatibility explanations in the mobile interface.
- Evaluate mobile usability with university students.
- Protect personal information and minimize unnecessary data collection.
- Establish suitable model evaluation and data collection procedures before claiming predictive performance.

## 6. Conclusion

The selected literature provides scientific and methodological support for the proposed mobile roommate matching application. Existing studies demonstrate the importance of roommate relationships, the computational challenges of matching, the potential of recommendation systems, and the need for usable and trustworthy interfaces.

The project will investigate an integrated approach that combines student lifestyle information, supervised machine learning, reciprocal preferences, and a mobile user interface.

The final effectiveness of this approach will need to be demonstrated through model evaluation, baseline comparison, and usability testing.

## 7. Source Verification Status

Total sources included: 12.

Publication years: 2022–2025.

All selected publications have openly accessible publisher pages or legally available full texts.

Individual Scopus records must be checked by DOI before the final submission.

The matrix is an initial critical synthesis; detailed claims should be checked against the complete papers during supervisor review.
