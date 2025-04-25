# Terms of Use

This portfolio showcases my skills in data analysis, machine learning, and related areas. 
Each project contains Jupyter Notebooks with code, explanations, and documentation of my thought process.

**Code License:** The code within these Jupyter Notebooks is licensed under the [MIT License](./LICENSE) for the purpose of evaluation by potential employers.

**Non-Code Content License:** The ideas, documentation, and explanations within these Jupyter Notebooks are licensed under the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0).  You can view the license details here: [https://creativecommons.org/licenses/by-nc-nd/4.0/](https://creativecommons.org/licenses/by-nc-nd/4.0/)

**Purpose:** These projects are solely intended for demonstrating my skills to potential employers during my job search.

**Commercial Use and Distribution:** Commercial use or distribution of these projects (beyond evaluation for hiring purposes) is strictly prohibited without my explicit permission.

For any inquiries, please contact me at liucheng.july@outlook.com.

# NYC-Taxi-Generous-Tipper-Prediction

* Random Forest Classification model
* XGBoost Classification model

## Documentation Structure

| Directory/File         | Description                                               |
|------------------------|-----------------------------------------------------------|
| `README.md`             | High-level introduction, project purpose, getting started, and documentation structure overview. |
| `LICENSE`                | Code License for the code within these Jupyter Notebooks for purpose of evaluation by potential employers. |
| `LICENSE-NON-CODE`       | License for the ideas, documentation, and explanations within these Jupyter Notebooks  |
| `code/`                 | Jupyter Notebooks of my data projects |
| `code/nyc-taxi-gratuity-prediction-analyze.ipynb`                 | Jupyter Notebook of Analyzing tip percent |
| `code/nyc-taxi-gratuity-prediction-random-forest.ipynb`                 | Jupyter Notebook of classification model, predict passengers will tip>=20% or not |
| `code/nyc-taxi-gratuity-prediction-xgboost.ipynb`| Jupyter Notebook of classification model, predict passengers will tip>=20% or not |
| `code/nyc-taxi-gratuity-prediction-summary.ipynb`                 | Summary of this project |
| `image/`             | images of my data projects                        |
| `data/`             | data set of my data projects                        |
| `data/2017_Yellow_Taxi_Trip_Data.csv` | NYC Yellow Taxi 2017 trip data(dataset from Google Advanced Data Analytics Certificate by Coursera) |
| `data/taxi_trip_clean.csv` | [NYC-Taxi-Fare-Amount-Prediction](https://github.com/panda-july/NYC-Taxi-Fare-Amount-Prediction/blob/main/README.md) EDA results |
| `data/rf_clean_label_predicted_fare_amount.csv` | [NYC-Taxi-Fare-Amount-Prediction](https://github.com/panda-july/NYC-Taxi-Fare-Amount-Prediction/blob/main/README.md) predicted fare amount|
| `data/nyc_clean_credit_trips.csv` | NYC Yellow Taxi 2017 trip data after analyzing(Created in `nyc-taxi-gratuity-prediction-analyze.ipynb`) |
| `pickle/`             | pickle files of my data projects                        |
| `pickle/rf_pickle.zip`      | pickle files of `nyc-taxi-gratuity-prediction-random-forest.ipynb`   |
| `pickle/xgb_pickle.zip`  | pickle files of `nyc-taxi-gratuity-prediction-xgboost.ipynb`      |


## Background
This is my capstone project from Google Advanced Data Analytics Certificate by Coursera.<BR/>
Since 1971, TLC has been regulating and overseeing the licensing of New York City's taxi cabs, for-hire vehicles, commuter vans, and paratransit vehicles.
In this fictional scenario, the New York City Taxi and Limousine Commission (TLC) has approached the data consulting firm Automatidata to identify which variables or factors influence the amount of gratuity a rider gives a driver. At a meeting with New York City TLC stakeholders, data team suggests building a random forest model to predict whether or not a rider will be a generous tipper (>= 20%). 


## Data
* [2017_Yellow_Taxi_Trip_Data.csv](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page): NYC Yellow Taxi 2017 trip data(dataset from Google Advanced Data Analytics Certificate by Coursera)
* [taxi_trip_clean.csv](https://github.com/panda-july/NYC-Taxi-Fare-Amount-Prediction/blob/main/code/taxi-fareamount-prediction-eda.ipynb): NYC Yellow Taxi 2017 trip data after data cleaning and joint other resources
* [crime_count.csv](https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i/about_data): Original dataset taken from NYPD Complaint Data with condition occurrence date in 2017, transformed and excluded some type of crimes(rape and sex crime, crimes occurred on a moving train), crimes occurred out of nyc, and aggregated it.
* Holiday, weather, taxi zone, Gasoline data please refer [NYC-Taxi-Fare-Amount-Prediction](https://github.com/panda-july/NYC-Taxi-Fare-Amount-Prediction/blob/main/README.md)

**2017_Yellow_Taxi_Trip_Data** 
| Column Name           | Type  | Description |
| :---                  | :---  | :--- |
| ID                    | int64 | Trip identification number. |
| VendorID              | int64 | A code indicating the TPEP provider that provided the record. <BR/>1= Creative Mobile Technologies, LLC;<BR/>2= VeriFone Inc.|
| tpep_pickup_datetime  | object| The date and time when the meter was engaged.  |
| tpep_dropoff_datetime | object| The date and time when the meter was disengaged.  |
| passenger_count       | int64 | The number of passengers in the vehicle.  <BR/> This is a driver-entered value.|
| trip_distance         | float64| The elapsed trip distance in miles reported by the taximeter.|
| RatecodeID            | int64 | The final rate code in effect at the end of the trip. <BR/>1= Standard rate <BR/>2=JFK <BR/>3=Newark <BR/>4=Nassau or Westchester <BR/>5=Negotiated fare <BR/>6=Group ride|
| store_and_fwd_flag    | object| This flag indicates whether the trip record was held in vehicle memory before being sent to the vendor, aka “store and forward,”  because the vehicle did not have a connection to the server. <BR/> Y= store and forward trip <BR/>N= not a store and forward trip|
| PULocationID          | int64 | TLC Taxi Zone in which the taximeter was engaged.|
| DOLocationID          | int64 |TLC Taxi Zone in which the taximeter was disengaged. |
| payment_type          | int64   | A numeric code signifying how the passenger paid for the trip.<BR/>1= Credit card<BR/>2= Cash<BR/>3= No charge<BR/>4= Dispute<BR/>5= Unknown<BR/>6= Voided trip    |
| fare_amount           | float64 | The time-and-distance fare calculated by the meter.|
| extra                 | float64 | Miscellaneous extras and surcharges. Currently, this only includes the $0.50 and $1 rush hour and overnight charges. |
| mta_tax               | float64 | $0.50 MTA tax that is automatically triggered based on the metered  rate in use.|
| tip_amount            | float64 | Tip amount – This field is automatically populated for credit card  tips. Cash tips are not included. |
| tolls_amount          | float64 | Total amount of all tolls paid in trip.  |
| improvement_surcharge | float64 | $0.30 improvement surcharge assessed trips at the flag drop. The  improvement surcharge began being levied in 2015. |
| total_amount          | float64 | The total amount charged to passengers. Does not include cash tips.|


## Summary

### Issues
* Not representative data. This dataset only had credit tip data, cash tip were not included. 
* Lack of data. This dataset didn't include tip percent feature, could not know the actual tip percent. 
* Vendor 1 and Vendor 2 may have different way to round tip_amount, one vendor may round down to 0.05, another one may round  to 0.01. The calculated tip percent may different from passenger actual choice.
  |Vendor|tip_amount calculation(assumption)|Example|
  |:-|:-|:-|
  |Vendor1|round down to 0.05|2.075->2.05|
  |Vendor2|round to 0.01|5.575->5.58<BR/>1.825->1.82|

### Model Results
* When consider tip_amount calculation difference:
    * Champion model:`rf_label1_cv14_hyp8_gs1`
    * Model features: `RatecodeID`,`mean_trip_distance`, `mean_trip_duration`, `mean_trip_speed`,
       `predict_fare_amount`, `PU_month`, `PU_weekday`,`PU_hour`
    * Lack of important features, the model score was not good. `mean_trip_speed`, `mean_trip_distance`, `mean_trip_duration`,`predict_fare_amount` were relatively important features
    * Limitation:
        * Could only predict credit card trips
    * Model assumptions:
        * Two vendors only had two way to calculate tip_amount, round tip_amount to .01 or round down to .05.
    * Model score:

|score|precision|recall   |F1      |accuracy|ROC_AUC |
|:-   |:-       |:-       |:-      |:-      |:-      |
|train|0.786816 |0.844237 |0.814516|0.732109|0.747175|
|val  |0.700602 |0.747429 |0.723259|0.601433|0.511623|
|test |0.706255 |0.731867 |0.718833|0.601182|0.521098|


* When not consider tip_amount calculation difference, if we could not use VendorID
    * Champion model: `xgb_label3_cv14_hyp18_gs1`
    * Model features: `RatecodeID`,`mean_trip_distance`, `mean_trip_duration`, `mean_trip_speed`,`predict_fare_amount`, `PU_month`, `PU_weekday`,`PU_hour`
    * Lack of important features, the model score was not good. `mean_trip_distance`, `mean_trip_duration`, `mean_trip_speed`,`predict_fare_amount` were relatively important features
    * Limitation:
        * Could only predict credit card trips
    * Model assumptions:
        * Two vendors had the same way to calculate tip_amount
        * Tip_percent which calculated from tip_amount could reflect the actual choice of passengers
    * Model score:			

|score|precision|recall   |F1      |accuracy|ROC_AUC |
|:-   |:-       |:-       |:-      |:-      |:-      |
|train|0.704602 |0.782443 |0.741485|0.711838|0.784784|
|val  |0.558140 |0.610169 |0.582996|0.538737|0.552162|
|test |0.551646 |0.622075 |0.584748|0.53319 |0.540218|

* When not consider tip_amount calculation difference, if we could use VendorID:
    * Champion model:`rf_label3_cv16_hyp8_gs1`
    * Model features: `RatecodeID`,`VendorID`,
       `mean_trip_distance`, `mean_trip_duration`, `mean_trip_speed`,
       `predict_fare_amount`, `PU_month`, `PU_weekday`,`PU_hour`
    * `VendorID` was the most important feature, it might associated with tip amount calculation difference
    * Limitation:
        * Could only predict credit card trips
    * Model assumptions:
        * Two vendors had the same way to calculate tip_amount
        * Tip_percent which calculated from tip_amount could reflect the actual choice of passengers
    * Model score:

|score|precision|recall   |F1      |accuracy|ROC_AUC |
|:-   |:-       |:-       |:-      |:-      |:-      |
|train|0.693943 |0.823579 |0.753224|0.714974|0.766781|
|val  |0.711257 |0.824576 |0.763736|0.730408|0.741567|
|test |0.683876 |0.821974 |0.746593|0.705187|0.71517 |


### Recommendation
* Not recommend to use this model
    * Could only predict credit trips
    * Lack of actual tip percent data, the estimated tip percent may different from actual tip percent
    * Vendor was an important feature to predict whether a passenger will tip >=20% or not. However it may due to tip amount calculation difference, not associated with passengers.
    * When consider tip amount calculation difference, lack of important features, model performance was not good
* To get more reliable prediction result, could consider collect more features such as passenger actual tip choice, passenger group(e.g. age, income, why they take a taxi, actual passenger count, do they have luggage or bags, relationship of passengers, region, job), taxi info(e.g. accessible taxi or not, vehicle type, how old the vehicle, payment system Vendor, how many hours vehicle used per day, how often the vehicle will be cleaned), driver info(e.g. age, region, income, driving experience, full time/part time, information about breaking traffic laws, how long they drive per day, rent car/owner, work period(06:00-18:00)), cash tip data.
* Unify tip calculation method to ensure all system providers will calculate tip amount in the same way [Licensing & Rules for
Technology System Providers](https://www.nyc.gov/assets/tlc/downloads/pdf/rule_book_current_chapter_66.pdf)