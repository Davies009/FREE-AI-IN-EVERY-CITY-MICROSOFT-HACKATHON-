# Microsoft X DSN FREE AI Classes in Every City Hackathon-
Expresso Churn Prediction by Data Science Nigeria,
Predict when an airtime customer will move to another provider
## INTRODUCTION AND PROBLEM STATEMENT
Expresso is an African telecommunications company that provides customers with airtime and mobile data bundles. The objective of this challenge is to develop a machine learning model to predict the likelihood of each Expresso customer “churning,” i.e. becoming inactive and not making any transactions for 90 days.The objective of this hackathon is to develop a predictive model that determines the likelihood for a customer to churn - to stop purchasing airtime and data from Expresso.
The data describes 500,000 Expresso clients.
## Data preparation & preprocessing
The dataset was taken through several techniques starting from checking missing data to the filling of missing values with zero .The target variable was then visualized with the data as well as the square root of both data , to check the distribution of the target variable

## Features Engineering
#### Feature engineering was the performed using label Encoder both on the test and train data on the "Region

from sklearn.preprocessing import LabelEncoder

#### Initialize LabelEncoder

label_encoder = LabelEncoder()

train_box.loc[:,'REGION_label'] = label_encoder.fit_transform(train_box['REGION'].astype(str))

test_box.loc[:,'REGION_label'] = label_encoder.fit_transform(test_box['REGION'].astype(str))

#### Also another Feature engineering was done extracting numerical value from strings

def return_mileage(length):

    mile = re.search("\d+", length)
    if mile is not None:
      return int(mile.group(0))
      
train_box.loc[:,"TENURE_um"] = train_box["TENURE"].apply(return_mileage)

Print(train_box[["TENURE", "TENURE_um"]].head())

## Model Trainig, Validation and Evaluation
The Catboostclassifier was used to train the model as the evaulation was based on log loss, Grid search was used to get the best parameter for the model , it gave the following results: 
##### bestTest = 0.2560194097
##### bestIteration = 998
##### Log Loss: 0.256019409719239
#### The model gave an Accuracy of : 0.8770625
#### Feature importance visualization was also done on the top 20 features.

## Technologies Used
#### python
#### pandas
#### seaborn
#### sklearn
#### catboost
#### jupyter notebook

## Result 
#### The model performed on a LOG_LOSS score of 0.251802394 on the public leaderboard and 0.247434682 on the private leaderboard
#### This score placed me 13th on the final leaderboard
### This is the link to the competition
https://zindi.africa/competitions/microsoft-x-dsn-free-ai-classes-in-every-city-hackathon-expresso-churn-prediction


