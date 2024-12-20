**The HR department at Salifort Motors** is focused on improving employee satisfaction, identifying employees likely to leave, and understanding the reasons behind their decisions.\
\
**By analyzing a dataset with 14,999 rows and 10 columns, the goals are:**\
A. Predicting Employee Quits.\
B. Identifying Key Predictors of Employee Quits.\
C. Providing Insights and Recommendations.\
\
With better employee retention, Salifort Motors can save time and resources spent on hiring and benefit from a more stable workforce.\
\
**A.	Predicting Employee Quits.**\
•	The logistic regression model, trained with a 75% training and 25% testing split, a random state of 42, and a maximum of 500 iterations, achieved a precision of 79%, a recall of 82%, an F1-score of 80% (all weighted averages), and an accuracy of 82%.\
•	However, the scores are significantly lower when focusing on predicting employees who leave.\
•	The random forest2 model was trained using 75% of the data for training and 25% for testing, with cross-validation set to 4, a random state of 0, a maximum depth of 5, maximum features set to 1.0, maximum samples set to 0.7, minimum samples per leaf set to 2, minimum samples per split set to 2, and 300 estimators.\
•	Random forest2 achieved an AUC score of 0.964, slightly lower than forest's 0.982 due to using fewer features, but it still outperforms decision tree2 (0.957) based on the AUC metric.\
•	The model predicts more false positives than false negatives, which means that some employees may be identified as at risk of quitting or getting fired, when that's actually not the case. But this is still a strong model.\
\
**B.	Key Predictors of Employee Quits.**\
•	The correlation heatmap shows that tenure, average monthly hours, number of projects, and last evaluation are related to left, whether an employee leaves.\
•	Feature importance from both decision tree and random forest models confirms that the key predictors are last evaluation, number of projects, tenure, and being overworked-working more than 166.67 hours per month. This is also in line with the results obtained from the correlation heatmap during exploratory data analysis.\
\
**C.	Insights and Recommendations.**\
**General Insights:**\
•	Employees leaving the company appear to be a result of poor management.\
•	The turnover can be related to a connection of longer hours at work, handling of too many projects, and generally low levels of satisfaction.\
•	Long hours without promotions or good evaluations tend to be unsatisfactory and could have caused a burnout for the group of employees in the company.\
•	However, people who have spent over six years with the company are less likely to quit.\
•	The models and feature importance analysis confirm that employees are overworked.\
\
**For improving retention, the following recommendations are advised:**\
•	Limit the number of projects that can be taken on by an employee.\
•	Promote employees who have at least four years of tenure or probe further into why they are feeling dissatisfied at this stage.\
•	Reward employees for working longer hours, or ensure they do not have to without remuneration.\
•	Clearly communicate overtime policies and set explicit expectations about workload and time off.\
•	Facilitate company-wide and team-level discussions to understand and improve the work culture.\
•	Reassess the evaluation criteria so that high scores are not only given to employees who work more than 200 hours a month. Apply a justified scale to reward effort and contribution in proportion.\
•	Besides, data leakage might still be an issue. It could be interesting to check the predictions performance after removing the last_evaluation feature as it may not occur frequently. Since the scores in an evaluation determine whether or not someone leaves, it would probably be more useful to know how to predict a person's performance score. Same with the satisfaction score.
