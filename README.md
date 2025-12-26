# Deep-Learning---Exploring-the-Dataset-and-Identifying-Predictors

Business Case: Exploring the Dataset and Identifying Predictors
Introduction to the Business Case
You are given data from an audiobook app, which logically relates to the audio version of books only. Each customer in the database has made at least one purchase, which is the condition to be included. Our goal is to create a machine learning algorithm based on this data that can predict if a customer will buy again from the audiobook company. The main idea is that the company should not spend its advertising budget targeting individuals who are unlikely to return. By focusing efforts on customers likely to convert again, the company can improve sales and profitability.

The model will take several metrics and try to predict human behavior. A side effect of our study is that the model will reveal which metrics are most important for a customer to come back. Having the data and technology to identify prospective customers creates significant value and growth opportunities. This is one of the better applications of data science.

Exploring the Dataset
The dataset is provided as a CSV file included in the lecture resources. When downloaded, the column headers will not be included, as we want no text in the data when training the model. Each row represents a person. Let's review the columns and understand why each could be useful.

Customer ID
The first column is customer ID. The ID acts like a name; whether it is 1, 2, 3, or John 1, John 2, John 3 makes no difference. Since no information is contained in the ID, we will exclude it from our algorithm.

Book Length Metrics
Next, we have book length metrics. The overall book length is the sum of the lengths of all purchases. The average book length is the sum divided by the number of purchases. For example, if a customer bought a single audiobook, the average and overall lengths will be equal. There is no need to include the number of purchases separately, as it is contained in these two variables.

Price Metrics
Then, we have the overall price paid and the average price paid. These variables are constructed similarly to the book length metrics. The price is in dollars, though this makes no difference to the algorithm. Price is almost always a good predictor of behavior.

Review Metrics
The next variable is review, which is Boolean and indicates if the customer left a review. This metric shows engagement with the platform. We assume that people who leave reviews are more likely to convert again.

Following that, we have "review out of 10," which measures the customer's review on a scale from 1 to 10. Note that only customers who left a review will have a value here. Most people do not leave reviews, which is common in marketplaces.

Handling Missing Review Values
To handle missing review values, we substitute all missing values with the average review score, which is 8.91. For our machine learning algorithm, 8.91 represents the status quo. A review greater than 8.91 indicates above-average feelings, while a review less than 8.91 indicates below-average feelings.

Review scores reflect customer sentiment towards the content or the platform as a whole. For example, an average review of 2 out of 10 indicates the customer did not have a pleasant experience, especially compared to the average of 8.91. Such a customer is unlikely to buy again.

Engagement Metrics
Next, we have total minutes listened, which measures engagement. Alongside it is completion, calculated as total minutes listened divided by the total length of books purchased, assuming customers do not re-listen to books. Both variables are self-explanatory.

Support requests is a numerical variable showing the total number of support requests a person has opened. Support can range from forgotten passwords to assistance using the platform. This is another engagement measure. It may indicate frustration leading to abandonment or high engagement with the platform.

Interaction Duration
Finally, we have a variable measuring the difference between the last time a person interacted with the platform and their first purchase date. This is another engagement measure. The larger the difference, the better, as it indicates regular engagement. A value of zero suggests the customer has never accessed their purchase or only did so on the first day, making it unlikely they will convert again.

Data Collection and Target Variable
It is always necessary to ask how the data was gathered, as this information is valuable for analysis. The data was gathered from the audiobook app and represents two years' worth of engagement.

Since we are doing supervised learning, we need targets. The targets are Boolean: one if a person converted and zero if not. Conversion means the customer bought another book within six months after the two-year data period. This six-month window was chosen as a reasonable period to observe repurchase behavior.

If a customer buys no new audiobook in that period, chances are they have gone to a competitor or did not like the audiobook format.

Summary
Our task is to create a machine learning algorithm that predicts if a customer will buy again. This is a binary classification problem with two classes: will not buy (0) and will buy (1).

In the next lesson, we will outline the solution. You can try solving the problem on your own or check out the upcoming lessons.

Key Takeaways
The business case involves predicting if a customer will repurchase from an audiobook app using machine learning.
The dataset includes various engagement and purchase metrics, excluding customer ID as it holds no predictive value.
Missing review scores are imputed with the average review score to handle incomplete data.
The target variable is defined by whether a customer made a purchase in the six months following the two-year data period, framing a binary classification problem.
