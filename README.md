# Toronto Airbnb - Using Machine Learning

## History of Airbnb
"Airbnb happened because two guys could not pay their rent, but did have some space." That's how Air-bed and breakfast(Airbnb) started when Joe and Martin from San Francisco rented out their three airbeds to make some cash. Since then, guests and hosts have used Airbnb to travel in a more unique and personalized way.
## Introduction
The story of Airbnb's foundation is fascinating. Airbnb is a hospitality service which enables people to lease or rent short-term accommodation. The company does not own any lodging. It is merely an agent. It receives a percentage service fees (commission) from both guests and hosts for every booking. A Host can create a listing by selecting the "Host" menu after logging in. Price for the listing is decided by the host. Host can charge different prices for nightly, weekly, and monthly stays. Host then add a description of the residence, amenities, available dates, cancellation policies, and any house rules. Potential guests are required to message the host directly through Airbnb to ask questions regarding the property. After the reservation, the hosts coordinate meeting times and contact information with the guests. Airbnb guests can leave a review and rate a listing after their stay. This rating can be used as an indicator of their experience during the stay.

<img src="https://github.com/GKPSingh/Toronto-Airbnb/blob/main/images/airbnb-hero-image.png" height=700px width=900px>

## Problem I Want to Solve
Although Airbnb and other sites provide some general guidance, there are currently no free and accurate services which help hosts price their properties using a wide range of data points. Also there is no way for travellers to figure out the correct price range based on the features they are looking for.

Paid third party pricing software is available, but generally hosts are required to put in their own expected average nightly price (‘base price’), and the algorithm will vary the daily price around that base price on each day depending on the day of the week, seasonality, how far away the date is, and some other factors.

It is very important to get the listings’ price correctly, particularly in big cities like Toronto, Vancouver, Ottawa where competition is very high and small differences in prices can make a big difference.

This project aims to solve this problem by using Machine Learning for properties in Toronto.

## Who Are My Clients?
I have two types of client clients, it can be used for both hosts and airbnb for better pricing optimization & maximize the revenue.

1. Airbnb hosts

If the listing price is high, then chances of listings getting booked will go down. Also if the price is low, then the host will be missing out on a lot of potential income. This project will help Airbnb hosts to price their listings competitively and thereby increase the bookings. The prices predicted by this model can also be used by existing hosts to increase bookings which will result in more earnings.

2. Guests looking to book Airbnb Listings

When guests are on Airbnb they do not have any means of knowing if the price that the hosts are asking for is reasonable for given features or not. This project will help guests to find real value for their money in the Airbnb marketplace.

## Dataset
<img src="https://github.com/GKPSingh/Toronto-Airbnb/blob/main/images/airbnb-toronto-map.png" height=600px width=900px>

The dataset that I am using for this project is available on <a href="http://insideairbnb.com/get-the-data.html">Inside Airbnb</a> for <a href="http://insideairbnb.com/toronto/">Toronto</a>. <a href="http://insideairbnb.com/get-the-data.html">Inside Airbnb</a> is an independent, non-commercial set of tools and data that allows to explore how airbnb is really being used in cities around the world.

As per the information available on <a href="http://insideairbnb.com/get-the-data.html">Inside Airbnb</a> the dataset was last scraped on April 9, 2021 and contains information for all 23524 listings for Toronto on Airbnb website on that day.

<img src="https://github.com/GKPSingh/Toronto-Airbnb/blob/main/images/airbnb-toronto-data.png" height=600px width=900px>

## Approach
1. Apply data wrangling(cleaning), exploratory data analysis, inferential statistics on the dataset.
2. For modelling, apply:

    1. Linear Regression
    2. Ridge Regression
    3. Lasso Regression
    4. K-Nearest Neighbors
    5. Random Forest

This will be a supervised machine learning project.

## Data Wrangling









## Modeling
With insights based on exploratory data analysis (EDA), I started to train predictive models.
I checked the distribution of the target, which is price & confirmed that taking log (using log_price column) can make it distribute more normally & skew is much improved.
I tried five different models:
1. Linear Regression
  * Predict the label of a data point by a linear function
  * Loss function = Ordinary least squares (OLS), which is sum of squares of residuals.
2. Ridge Regression (L2 regularization)
  * Same as Linear Regression but penalize large coefficients by L2 regularization:
  <img src="https://github.com/GKPSingh/Toronto-Airbnb/blob/main/images/ridge.png" height=60px width=300px>
3. Lasso Regression (L1 regularization)
  * Same as Linear Regression but penalize large coefficients by L1 regularization:
  <img src="https://github.com/GKPSingh/Toronto-Airbnb/blob/main/images/lasso.png" height=60px width=300px>
4. K-Nearest Neighbors
  * Predict the label of a data point by 
        * Looking at the ‘k’ closest labeled data points
        * Taking a majority vote
5. Random Forest
  * Predict the label of a data point by ensembling decision trees, which correct for decision trees' habit of overfitting.

I trained the above models with four features:
  * Accommodates
  * Bathrooms_text
  * Bedrooms
  * Beds

Test size of Train-test-split is set to 20%. We chose Root-Mean-Squared-Error (RMSE) as our scoring metric.

## Summary
1. I tried 5 different models on Airbnb listing price prediction
  * Linear Regression
  * Ridge Regression
  * Lasso Regression
  * K-Nearest Neighbors
  * Random Forest
2. Lasso Regression has the best Root Mean Square Error (RMSE) when Price column is used.
3. RandomForest has the best Root Mean Square Error (RMSE) when log_Price column is used.
4. Linear regression models did not perform well because there are less data points with price above dollar 200 and looks like they have a different linear relationship. 50% listings are below dollar 99.
5. RSME can be improved further by fine tuning the hyperparameters.

## Future
* Apply NLP on Airbnb descriptions and reviews for better listing price prediction.
* Apply models on other cities or training models on other cities.
* Apply piecewise linear regression.
* Apply ensemble models like Gradient Boosting
* Hyperparameters can be further fine tuned to get better results.
* More data clean up can be done for even better results.
