# Statistical-Machine-Learning

# Spam Filtering

Comparison of Classification Methods

The spam data set consists of information from 4601 email messages. The data set was generated in 1999 and donated by George Forman from HP Labs, CA. It is available at the UCI Machine Learning Repository (https://archive.ics.uci.edu/ml/datasets/Spambase). The response is either regular email (60.6%) or spam (39.4%). There are 57 predictors: 48
predictors are the percentage of words in the email that match a given word (e.g. business, address, free), 6 predictors are the percentage of punctuation marks in the email that match a given punctuation mark (e.g. !, $), and additional three predictors are the average length of uninterrupted sequences of capital letters (CapAve), the length of the longest uninterrupted sequence of capital letters (CapMax), and the sum of the length of uninterrupted sequences of capital letters (CapTotal). We use the spam data set available in the R package kernlab and classify emails using logistic regression, LDA, QDA, and k-NN.

Identifying those words or characters with largest difference in the average percentage between spam and regular email

![image](https://user-images.githubusercontent.com/42225976/157140390-cb13e67f-5ee8-49d9-943b-4f9b8ac3a4bb.png)

Considering the predictors george, hp, you, free, and remove in the following analysis

![image](https://user-images.githubusercontent.com/42225976/157140467-c07ef849-5dcf-4c99-9305-1f7dd1b44211.png)

# Logistic Regression

Using the five variables, we fit a logistic regression model. Note that the response variable type is a factor with two levels, “nonspam” and “spam”, and the glm() function models the log odds of the second level (spam) versus the first level (nonspam) as a function of the predictors

Confusion matrix for training is,

![image](https://user-images.githubusercontent.com/42225976/157140781-c5da1a28-0891-43ca-b13f-3bad8116f0ec.png)

The training error is 17.6%

Confusion matrix for testing is,

![image](https://user-images.githubusercontent.com/42225976/157140898-14a2adf9-ceeb-4cb4-bcbc-a11eea2dc738.png)

The testing error is 16.96%

# Linear Discriminant Analysis (LDA)

The lda() function in the MASS library is used to carry out a linear discriminant analysis

Confusion matrix for training is,

![image](https://user-images.githubusercontent.com/42225976/157141539-435a228a-d7ce-4c3d-af58-7ffe869c768d.png)

The training error is 25%

![image](https://user-images.githubusercontent.com/42225976/157141619-93b2e1ef-ead8-45ca-85b6-390d885aef27.png)

The testing error is 24.49%

# Quadratic Discriminant Analysis (QDA)

A quadratic discriminant analysis is done using the qda() function in the MASS library

Confusion matrix for training is,

![image](https://user-images.githubusercontent.com/42225976/157141755-3c6981aa-99eb-4ea2-b320-dc6e527edc9a.png)

The training error is 31.2%

Confusion matrix for testing is,

![image](https://user-images.githubusercontent.com/42225976/157141956-ea04a072-1e0b-4884-a00b-de475943e675.png)

The testing error is 31.2%

# k-Nearest Neighbor Method

For k-nearest neighbors method, we use the knn() function in the class library

1-NN

The confusion matrix for testing is,

![image](https://user-images.githubusercontent.com/42225976/157142146-75671842-c2a6-4fec-ac58-3901eddeed1b.png)

The testing error is 18.05%

10-NN

The testing error is 18.05%

The plot of error rate vs number of neighbors,

![image](https://user-images.githubusercontent.com/42225976/157142370-5b61344b-a0b7-4337-8903-2f701b851677.png)

With a much smaller data dimension compared to the sample size, the test error rate of k-NN tends to increase with k. Note that there are many cases with zero percentage for each of the five words in the training data, which explains why the training error rate for 1-NN is not zero.

# k-NN with 54 predictors
Considering all of the 54 predictors on the percentage of words or punctuation marks for k-NN.

![image](https://user-images.githubusercontent.com/42225976/157152248-b5e124fe-81b9-4ee1-a4cc-80d7530de213.png)

When all of the 54 predictors are used, overall there is a reduction in the test error rates of k-NN. Still, the 1-NN turns out to be the best with the error rate of 0.1158012.
