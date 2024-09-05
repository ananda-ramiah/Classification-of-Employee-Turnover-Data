# Salifort Motors Workforce Turnover Analysis

### Background of the Salifort Motors Scenario

#### About the company

Salifort Motors is a fictional French-based alternative energy vehicle manufacturer. Its over 100,000 employees research, design, construct, validate, and distribute electric, solar, algae, and hydrogen-based vehicles. Salifort’s end-to-end vertical integration model has made it a global leader at the intersection of alternative energy and automobiles.

As a data specialist working for Salifort Motors, you have received the results of a recent employee survey. The senior leadership team has tasked you with analyzing the data to develop ideas for increasing employee retention. To help with this, they would like you to design a model that predicts whether an employee will leave the company based on their department, number of projects, average monthly hours, and any other data points you deem helpful.

**Click [here](https://github.com/ananda-ramiah/Salifort-Motors-Workforce-Turnover-Analysis/blob/main/Activity_%20Course%207%20Salifort%20Motors%20project%20lab.ipynb) to view the capstone project, which includes detailed explanations for each step.**

### Project Overview

This project aimed to create a predictive model through multiple logistic regression or machine learning algorithms such as Decision Tree, Random Forest, or eXtreme Gradient Boosting (XGBoost). This project utilized employee statistics recorded by Salifort Motors and is the capstone project for Google's Advance Data Analytics Professional Certificate. The champion model for this analysis was a random forest with tuned hyper-parameters. The following metrics were used to evaluate the algorithm's success.

| Model Name	| F1 Score | Precision |	Recall | Accuracy | AUC |
| ----------  | -------- | --------- | ------- | -------- | -------- |
|Tuned Random Forest|	88.67%	| 87.04% |	90.36%	| 96.16% | 93.84% |

The random forest model determined the most relevant features for separating employees who are likely to leave from those who won't are last_evaluation, number_project, tenure, and overworked. We note that the latter feature was engineered and represents the employees who worked over 175 hours in a month or not.

### Business Understanding

During the Exploratory Data Analysis process, we observed that salary and department are not leading factors for employee turnover rates. We see that the number of projects, hours worked, tenure and recent evaluation scores are good indicators of employee turnover. Another important aspect of this project was to determine the best way to invest in employee training and resources without losing skilled workers. Thus, our recommendations would be to have better allocations of projects and improve processes to reward long-tenured and overworked employees.

### Data Understanding

The dataset was artificially generated by Google for this project. The fictional company's data came from [Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv) and is free to use according to this [license](https://creativecommons.org/publicdomain/zero/1.0/). The data consisted of approximately 12k unique employees and 10 features per employee. The features included employee satisfaction, evaluation score, number of projects contributed to, the average number of hours worked per month, tenure, whether if they had a work accident if they were promoted within the last 5 years, the department worked for, and salary. The bar chart below shows the proportion of employee leaving Salifort Motors

  ![Employee Turnover Bar Chart](https://github.com/user-attachments/assets/a8a77a2b-4d42-4a57-9a29-e23a933ae855)

### Modeling and Evaluation

I implemented two machine learning algorithms and matched them against each other to compare their performance based on the previous four metrics (F1 Score, Precision, Recall, Accuracy). The dataset was split into training, validating and testing sets with a (60/20/20) proportion respectively. We performed this splitting such that we are able to cross-validate our models in the process of hyper-parameter tunning; this technique will avoid our models to overfit the training data and will improve how the model manages randomness. The results of each model are summarized in their respective confusion matrix.

![Logistic Regression Confusion Matrix](https://github.com/user-attachments/assets/70d76271-8fc1-4465-bbe3-f6bad9491561)
![Random Tree Confusion Matrix](https://github.com/user-attachments/assets/4cc612aa-bae5-41ed-9177-8be8d532ced6)


### Conclusion

The models and the feature importances extracted from the models confirm that employees at the company are overworked and not rewarded according to the effort exrted on projects.

To reduce the number of employees leaving the company, the company should consider the following:

- Cap the number of projects an employee can work on at a time.
- Reward employees for working longer hours and for working on more projects.
- Consider promoting employees who have been with the company for atleast four years, or conduct further investigation about why four-year tenured employees are so dissatisfied.
- If employees aren't familiar with the company's overtime pay policies, inform them about this. If the expectations around workload and time off aren't explicit, make them clear.
- High evaluation score shouldn't just be based on the number of projects and hours worked, but also on the quality of the work

#### Next Steps

It may be justified to still have some concern about data leakage. It could be prudent to consider how predictions change when last_evaluation is removed from the data. It's possible that evaluations aren't performed very frequently, in which case it would be useful to be able to predict employee retention without this feature. It's also possible that the evaluation score determines whether an employee leaves or stays, in which case it could be useful to pivot and try to predict performance score. The same could be said for satisfaction score.
