# Starbucks: Offer customer segment

It is imperative to optimize the marketing related efforts such as they produce the best results, i.e. return on investments (conversion, loyalty, referral) with respect to time and expenses. In this case, we will focus on the likelihood, on whether the customers will respond to the offer made by Starbucks based on their demographical and historical transactional data. I am going to build a Machine Learning (ML) model which will predict whether the user will make a purchases as a response to the offer or without it, based on the transactional and demographic data on that user. 

The ML model I build allows to assign probabilities of completing each type of offer for any user based on her demographic and transactional data. Thus, we will be able to see if it makes sense to send an offer to the prospective user and what kind of offer should it be. In few test cases, the discount was the offer with the highest probability of success, most probably because among many different business and demographic factors discount offers had higher correlation with the offers completed. 

In order to implement the ML model into actual business process, it might make sense to develop the unit economics of each particular product and associated offer and based on that calculate, which offer lets to higher conversion and highest retention metrics.

For detailed description of the project please refer to Medium blog (https://medium.com/@mamatov.aziz_68918/loyalty-program-analytics-starbucks-challenge-340c29198b13).

We will determine the customer segment most susceptible to promotional offer using ML or heuristic approaches
This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

Not all users receive the same offer, and that is the challenge to solve with this data set.

We will combine transaction, demographic and offer data to determine which demographic groups respond best to which offer type. This data set is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. You'll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement.

There are the following files in the repository, the Jupyter Notebook containing all the data processing and ML work and the data which is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

## portfolio.json

* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

## profile.json

* age (int) - age of the customer
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

## transcript.json

* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

# Libraries used
* pandas, numpy
* matplotlib.pyplot
* seaborn
* sklearn.model_selection: train_test_split
* sklearn.model_selection: GridSearchCV
* catboost

# References:
https://catboost.ai/
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge_asof.html
https://www.cleverism.com/ultimate-guide-unit-economics/


