
# Literature Review

## Development of a Compatibility-Based Roommate Matching Application for University Students

**Team Members:** Ayan Matayev, Mirasbek Idiatulla

**Supervisor:** Tomiris Zhaksylyk

**Research Period:** 2022–2025

## 1. Introduction

Finding a suitable roommate is an important decision for university students, especially those who live in dormitories or rent shared apartments. Students may have different daily routines, sleeping schedules, cleaning habits, and expectations about personal space. These differences can create disagreements and affect the experience of living together.

Students often choose roommates through personal connections, university groups, or online advertisements. However, these methods may provide limited information about a person's everyday habits and preferences.

Our graduation project aims to develop a mobile application that helps university students find compatible roommates using machine learning and lifestyle-based recommendations.

This literature review examines 12 scientific publications related to roommate relationships, accommodation matching, recommender systems, mobile usability, and privacy.

The main objectives are to understand the existing research, identify relevant methods and limitations, and explain how these findings can support our proposed application.

## 2. Roommate Relationships and Student Housing

### 2.1. Measuring Roommate Relationship Quality

Willis and Lane (2022) investigated the Roommate Relationship Scale as a method for measuring the quality of relationships between college roommates.

Their research used longitudinal data and factor analysis to examine the reliability and validity of the scale. The results provided preliminary support for using the scale to evaluate roommate relationships.

This study is useful for our project because compatibility should not be measured only by how similar two students are. An important question is whether students actually feel comfortable living together.

However, the research focuses on measuring existing relationships rather than predicting suitable roommate pairs.

For our project, it provides a possible foundation for future user evaluation.

### 2.2. Roommate Conflicts and Daily Habits

Abela, Sharma, and Law (2024) investigated conflict resolution and bullying among undergraduate roommates.

Their mixed-method research involved 804 undergraduate students and examined conflict management, social support, and negative roommate experiences.

The study identifies household disagreements, including cleaning responsibilities and noise, as important sources of roommate conflict.

These findings are relevant because our application will ask students about their habits and living preferences before recommending a potential roommate.

Nevertheless, the study does not demonstrate that a matching algorithm can prevent conflicts. This remains an outcome that our proposed system would need to investigate.

### 2.3. Roommate Influence on University Life

Cao, Zhou, and Gao (2024) studied how roommate relationships influence academic performance using longitudinal data from 5,272 university students.

Their analysis found that roommates showed greater similarity in academic performance than expected under a randomized roommate-assignment model. The study also examined how peer effects developed over time.

These results suggest that shared accommodation can influence students beyond everyday household activities.

Although academic performance is not equivalent to roommate compatibility, the research supports the broader importance of studying student living arrangements.

Together, these three studies show that roommate relationships deserve attention when designing student-oriented accommodation services.

## 3. Roommate Matching and Allocation Approaches

### 3.1. Mathematical Roommate Allocation

Bonifaci and Rivera Dallorto (2025) investigated computational problems involving roommate allocation, fairness, and stability.

Their research focuses on mathematical properties of assigning people according to preferences. It demonstrates that some allocation objectives can be computationally difficult.

This work is relevant because roommate recommendations involve more than identifying similarities. The system must also consider whether the proposed matching arrangement is acceptable.

However, mathematical allocation algorithms do not necessarily predict how well two people will live together based on personal habits.

Our project will focus on individual compatibility prediction rather than solving the entire accommodation allocation problem.

### 3.2. University Accommodation Assignment

Afacan (2024) proposed mechanisms for assigning students to universities and dormitories.

The research introduced and analyzed dorm-augmented deferred acceptance mechanisms to address efficiency and stability problems in institutional accommodation assignment.

This study demonstrates how student preferences and allocation rules can be modeled systematically.

However, assigning students to dormitories differs from recommending individual roommates based on lifestyle characteristics.

Our application will not automatically allocate university housing. Instead, it will provide recommendations that students can evaluate before making their own decisions.

### 3.3. Reciprocal Recommendation Systems

Yang et al. (2024) studied reciprocal recommendation systems, where a successful match depends on the interests of both parties.

Their research proposed new evaluation metrics and methods that consider bilateral recommendation outcomes rather than evaluating each side independently.

Experiments were conducted using recruitment and online dating datasets.

This approach is especially relevant to roommate matching because both students should be comfortable with the proposed arrangement.

For example, a student who prefers a quiet environment may not be a suitable roommate for someone who frequently hosts noisy gatherings, even if they share several other interests.

Our system should therefore consider both users' preferences, not only the requirements of the student performing the search.

## 4. Machine Learning and Recommendation Systems

### 4.1. Knowledge-Based Recommendation

Uta et al. (2024) reviewed knowledge-based recommendation systems and their main approaches.

The study discusses how explicit user preferences, domain knowledge, and constraints can support recommendation decisions.

This is relevant because a new roommate matching application may have limited historical user interaction data.

At the beginning, the system may rely primarily on questionnaire responses about sleep schedules, cleanliness, noise tolerance, and accommodation preferences.

Knowledge-based methods can support the handling of mandatory requirements, while machine learning can be investigated for compatibility prediction.

The main limitation is that preference-based approaches depend on the quality of user-provided information and the design of domain rules.

### 4.2. Multi-Objective Recommendation

Jannach and Abdollahpouri (2023) presented a survey of multi-objective recommender systems.

Their work explains why optimizing only recommendation accuracy may be insufficient in real-world applications.

Different objectives, stakeholders, and technical requirements may need to be considered simultaneously.

For our project, this is important because a recommended roommate should not only have a high predicted compatibility score.

Other factors may include budget limitations, smoking preferences, accommodation location, and mutual willingness to share a room.

The proposed application will therefore distinguish between compatibility predictions and mandatory matching restrictions.

### 4.3. Explainable Recommendations

Govea, Gutierrez, and Villegas-Ch (2024) investigated transparency and explainability in recommendation systems.

Their experimental research used explainability approaches, including LIME and SHAP, with recommendation models evaluated on existing datasets.

The authors reported improvements in recommendation precision and the ability to understand recommendation outputs under their experimental conditions.

This research is particularly relevant to the user experience of our application.

Instead of displaying only a compatibility percentage, the system could explain important similarities and differences.

For example, the application may show that two students prefer similar sleeping schedules but have different expectations about guests.

However, explanations must accurately describe the model and should not be treated as proof of successful future cohabitation.

## 5. Mobile Application Design and User Experience

### 5.1. Mobile Usability Testing

Weichbroth (2024) reviewed methodological approaches to mobile application usability testing.

The research discusses user testing procedures, experimental settings, data collection methods, and ways to assess mobile usability.

This study is relevant because our project is intended for university students who will interact with the system through smartphones.

The application should allow students to register, complete questionnaires, and review recommendations without unnecessary complexity.

We plan to evaluate whether users can complete these tasks efficiently and understand the results presented by the application.

### 5.2. User-Centered Mobile Application Development

Rezaee et al. (2024) designed and evaluated a mobile self-care application for adolescents using a user-centered approach.

Their development process involved interviews with potential users, application development, and usability evaluation.

Although the application belongs to a different domain, the methodology demonstrates the value of involving target users during design.

Our project follows a related principle by conducting initial student interviews and using their findings to inform requirements and interface design.

Future usability testing will examine the registration process, questionnaire completion, roommate recommendations, and profile navigation.

## 6. Privacy, Security, and User Trust

Saeed (2024) investigated users' perceptions of mobile application privacy and security controls.

The study discusses the importance of protecting personal information while keeping privacy settings understandable and accessible.

This is relevant because roommate matching applications may collect information about students' habits, preferences, accommodation plans, and personal profiles.

Our application should collect only information necessary for its intended functions.

Sensitive information should not automatically become publicly visible to other users.

The proposed system should include appropriate authentication, access controls, and clear privacy settings.

User trust is important because students may hesitate to communicate with unfamiliar people or disclose unnecessary personal information.

## 7. Critical Discussion

The reviewed publications provide different perspectives on roommate matching and mobile recommendation systems.

Research on roommate relationships establishes the social importance of shared accommodation. However, these studies mainly examine existing relationships rather than predicting future compatibility.

Mathematical matching studies provide methods for understanding preferences, stability, and fair allocation. Their objectives are different from predicting lifestyle-based compatibility between individuals.

Recommender-system research offers possible approaches to personalized matching, but existing techniques may require interaction data that a newly developed application does not initially possess.

Mobile usability research provides practical guidance for interface design and testing, while privacy studies emphasize responsible handling of personal information.

An important limitation is that evidence from online dating, recruitment, or general recommender systems cannot automatically be generalized to student roommate matching.

Therefore, the effectiveness of our proposed system must be evaluated in its intended context.

## 8. Identified Research Gaps

Based on the reviewed literature, we identified several challenges that motivate our project.

### Gap 1 — Lifestyle-Based Compatibility Prediction

The selected publications do not establish a validated solution combining our proposed student lifestyle questionnaire with a supervised ML roommate compatibility model.

### Gap 2 — Training Data Availability

A new roommate matching application may lack sufficient labeled examples of compatible and incompatible student pairs.

A separate data collection and labeling strategy is therefore required.

### Gap 3 — Mutual Compatibility

Roommate matching requires consideration of both students' preferences.

A recommendation that satisfies only one student may not lead to a suitable roommate arrangement.

### Gap 4 — Explainability and Trust

Compatibility percentages alone may not provide enough information for students to make informed decisions.

Model explanations and understandable profile comparisons should be included and evaluated.

### Gap 5 — Mobile Usability and Privacy

The application must balance convenient profile discovery with appropriate protection of student information.

### Gap 6 — Real-World Validation

Predictive performance on a test dataset does not automatically demonstrate improved roommate relationships.

Evaluation should consider model quality, user feedback, and the limitations of self-reported compatibility data.

## 9. Proposed Research Direction

Based on the literature, our project proposes the following approach:

1. Design a structured lifestyle questionnaire for university students.
2. Collect relevant student preferences and accommodation requirements.
3. Develop a strategy for obtaining labeled compatibility data.
4. Investigate supervised ML algorithms, including Logistic Regression, Random Forest, and Gradient Boosting.
5. Compare models using appropriate validation procedures.
6. Implement mandatory compatibility restrictions.
7. Generate ranked roommate recommendations.
8. Provide explanations of relevant similarities and differences.
9. Design a mobile interface using React Native and Expo.
10. Evaluate the system through technical testing and student usability feedback.

A weighted rule-based matching method will be developed as a baseline for evaluating whether the ML approach provides measurable improvements.

The final model will be chosen using experimental evidence rather than assuming that a particular algorithm will perform best.

## 10. Conclusion

This literature review examined 12 scientific publications related to roommate relationships, matching systems, personalized recommendations, mobile usability, and privacy.

The literature supports the importance of understanding student living preferences and demonstrates several computational and design approaches relevant to roommate selection.

At the same time, the reviewed research highlights challenges involving mutual preferences, training data, model evaluation, explainability, and privacy.

Our proposed project will combine these ideas in a mobile application that uses supervised machine learning to generate roommate compatibility recommendations.

The effectiveness of the application will be investigated through model evaluation, comparison with a baseline, and usability testing with university students.

## References

[S01] Willis, M. A., & Lane, S. P. (2022). Preliminary evidence for the factor structure, concurrent validity, and construct validity of the Roommate Relationship Scale in a college sample. https://doi.org/10.3389/fpsyg.2022.960421

[S02] Abela, K. R., Sharma, A., & Law, D. M. (2024). Compromising, Avoiding, or Bullying? A Mixed Method Approach to Understanding Conflict Resolution and Bullying Among Undergraduate Roommates. https://doi.org/10.1177/21676968231216512

[S03] Cao, Y., Zhou, T., & Gao, J. (2024). Heterogeneous peer effects of college roommates on academic performance. https://doi.org/10.1038/s41467-024-49228-7

[S04] Bonifaci, V., & Rivera Dallorto, H. (2025). Egalitarian roommate allocations: Complexity and stability. https://doi.org/10.1016/j.tcs.2024.115009

[S05] Afacan, M. O. (2024). Dorm augmented college assignments. https://doi.org/10.1007/s00355-024-01510-9

[S06] Yang, C., et al. (2024). Revisiting Reciprocal Recommender Systems: Metrics, Formulation, and Method. https://doi.org/10.1145/3637528.3671734

[S07] Uta, M., et al. (2024). Knowledge-based recommender systems: overview and research directions. https://doi.org/10.3389/fdata.2024.1304439

[S08] Jannach, D., & Abdollahpouri, H. (2023). A survey on multi-objective recommender systems. https://doi.org/10.3389/fdata.2023.1157899

[S09] Govea, J., Gutierrez, R., & Villegas-Ch, W. (2024). Transparency and precision in the age of AI: evaluation of explainability-enhanced recommendation systems. https://doi.org/10.3389/frai.2024.1410790

[S10] Weichbroth, P. (2024). Usability Testing of Mobile Applications: A Methodological Framework. https://doi.org/10.3390/app14051792

[S11] Rezaee, R., et al. (2024). Design and usability evaluation of a mobile application for self-care among Iranian adolescents. https://doi.org/10.1186/s12889-024-18341-z

[S12] Saeed, S. (2024). Usable Privacy and Security in Mobile Applications: Perception of Mobile End Users in Saudi Arabia. https://doi.org/10.3390/bdcc8110162
