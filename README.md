# Starbucks-Capstone-Challenge

## Context
As one of the biggest coffee giants in the world, Starbucks operates more than 31,000 stores worldwide, in 2017, Starbucks launched its most advanced AI-driven initiative “Deep Brew”. The brand’s custom-made recommendation platform was built to reach customers across multiple channels, including the Starbucks ordering app. The industry-leading Starbucks Rewards Program has continued to flourish since its introduction in 2007. Obviously, it becomes more and more important to leverage the AI technology to enhance the customer experience.


## The Goal
Since it’s important to provide customized experience from ordering to offer on loyalty app, the problem becomes to how to correctly and precisely locate the target customer group. That is, the task is to decide what the best-personalized offer is to send to users so that the conversion rate can be maximized. Also, it’s critical to know which groups of people are most responsive to each type of offer, and how best to present each type of offer.

The plan of this project is to build a machine learning model to decide which is the best type of offer to send to each customer. The dataset will be separated into three types of offer and fit the data into three supervised classification models. Using this way, the model will predict whether the offer will be responded by customer or not when sent to them. Also, by investigating the feature importance of the model, it can help answer the question that what factors mainly affect people to make the decision and finally complete the transaction. Therefore, with the solution above, it’ll be easier and more accurate to identify which groups of people are most responsive to each type of offer, and how best to present each type of offer.


## Data Sets

The data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Following is the schema and explanation of each variable in the files:

**portfolio.json**
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

**profile.json**
* age (int) - age of the customer 
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

**transcript.json**
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## Project design
The project is designed with the following steps:

- Prepare and clean data -- combine transaction, demographic and offer data. Understand the connection between columns and dataset. Try to get the useful information from data as much as possible.  

- Data exploration -- In order to analyze the problem better in next sections, first need to explore the datasets which includes checking the missing value, visualizing the data distribution, etc.  

- Data preprocessing -- In order to find out what mainly affect the finish of the transaction by sending the offer, in the data processing process, also need to process the data to merge the events of each specific offer sent so as to find out which offer were received, viewed and finally completed with a transaction.  

- Feature engineering -- After basic processing, the next step will look if there are any columns that can be used to create new features. For example, generating a new column for length of customer’s membership, the count of offer received for each user, calculate the time lap between offers, etc.  

- Building model – after pre-processing and feature engineering, next step is to build the model using response flag generated in previous steps to predict whether the customer will respond to the offer or not.  

- Model tuning – Compare the model using metrics selected above and tune the parameters of initial model using GridSearch method to get higher performance.  

- Conclusion and further improvement – compare the final selected model to benchmark to see if the solution provide a better personalized offer. Also, review the built process and see if there’s any opportunities to enhance the model in the future.  

__Notes:__ more details please refer to proposal.pdf


## There's also a Medium post [link](https://medium.com/@yfan941101/how-to-send-out-starbucks-offer-in-a-smart-way-9321cbf3ee4d) with the project summary.

## Licensing, Authors, Acknowledgements, etc.
This project was authored by Fan Yuan.
Thanks to Starbucks for the dataset, and to Udacity for bringing the opportunity to work with it.

