# Comparing-Classifiers


# Goal

Out objective is to use the Portuguese Bank data set to determine if we can predict a successful sale for calling campaigns using the potential customer's age and the total time spent speaking to the potential customer to see if there is a trend. Identifying such a trend would exceptionally useful as the salesmen/callers could focus their efforts on a particular age group as well as understand if campaign persistence is useful.

# Setup

Our data set was entirely clean with no NaNs or exceptional outliers to cutoff.

<img src="/images/data.png">

We set our X variable to the potential customers age, and the Y variable to the duration of the campaign, we also retain our results data for whether or not there was a sale. We see from the initial scatterplot below that there isn't a very well defined trend.

<img src="/images/scatter.png">

We run four different analysis/predication techniques and score so that we may have the best model possible for our predictions.

# Results


## KNN

The first model we use is the KNN model with multiple hyperparameters

<img src="/images/knn.png">

We find that there is indeed a decision boundary for possible sales but it is heavily limited to only three small sections. From the given information we successfully built a model that predicts with ~88% accuracy. The features resulting in the best model were setting the predictive neighbors to 11, the p value to 2 and keeping the weights uniform. 

This model is pretty useful in this case. It would indicate to the salesmen/callers that the best strategy for a successful sale is to focus on the older people and avoid wasting time on long campaigns.


##  Decision Tree

The second model we try is the Decision Tree model with multiple hyperparameters.

<img src="/images/dtree.png">

We find a rather clean and simple Decision Tree model with the best parameters being a maximum depth of 2 and a minimum sample split of 0.1. This model also had an ~88% accuracy. 

However, in this case it is not a very useful model as besides being able to split the data, it does not really allow a salesmen with the clearest information as to how to approach their next customers.

3
## Logistic Regression

The third model we try is the Logistic Regression with multiple hyperparmeters.

<img src="/images/lgr.png">

Although our results show that we have an ~88% predication accuracy like the other models, after looking at the graphical visualization we find that there is no apparent decision boundary. 

Even with the best model features using a penalty of l2 and a lbfgs solver, it seems the most optimal strategy depicted by this model, is to not bother calling at all as there won't be a sale ever. Not the most useful model in this case.


## SVC

The fourth and final model we try is SVC with multiple hyperparmeters
<img src="/images/svc.png">

Unfortunately, we find the sale result as the Logistic Regression model. That is, an ~88% successful predication rate but a graphical representation that describes a zero success rate for any sale.

The best parameters of 0 coefficient, 0.1 gamma, and the Gaussian kernel results in a rather useless predictive model as it considers any strategy to have 0% changes of a successful sale.

# Model Scores

<img src="/images/score.png">


# Findings

Our four models all had predictive success rates of ~88%, however, since two of the models predicted a 0% sale success rate, when we do know there were successful sales, then we can conclude that our predictive score/rating is rather meaningless.

We immediately can scratch off the Logistic Regression and SVC models are being useful models for our intentions.

The Decision Tree model is a bit more useful as it successfully splits our data, however it terms of a business use case, it has very little potential.

The KNN model however is fantastic, we get a meaningful decision boundary. We see that on our graphical representation of this model that the callers/salesmen should focus on targeting older people as they have a much string sale success rate. Additionally, it shows that longer campaigns do not serve any practical purpose. There is a niche field where people around the age of 75 and up will purchase what the salesmen has to sell rather quickly. This model can save money in two ways:

1st -> Salesmen should not waste time with long campaigns. Their time is money, so spending it on long campaigns is wasteful.
2nd -> Target the elderly as they seem to purchase what the salesman has to offer rather quickly.





