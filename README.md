## Market Share Decrease Analysis of the NYC Yellow Cab

---
### Where to use?
This project is to be run on Google Cloud Platform (GCP). It includes running a **Pub/Sub job**.

### Which data to use?
For supervised learning algorithms, it is a common practice to split the data into training and test sets to see how well a model will perform.

For the purpose of this study, we are using 3 datasets - 2 historical datasets from Google's Marketplace in NYC TLC Trips and one newly updated one from pub/sub topic *projects/pubsub-public-data/topics/taxirides-realtime*. 

### What's the table schema (necessary for proper data loading)? 
The following code was used to create table schema for data transfer: <br /> 
`bq mk --time_partitioning_field timestamp --schema ride_id:string,point_idx:integer,latitude:float,longitude:float,timestamp:timestamp,meter_reading:float,meter_increment:float,ride_status:string,passenger_count:integer -t taxirides.realtime`

### Train / test data
Tlc_yellow_trips_2015 was used as a training set
In cases when it was possible (i.e., appropriate prediction values were present in the test set), realtime table was used as a test set. Otherwise, tlc_yellow_trips_2016 was used as a test set instead.

### ML Models
The two main machine learning models used were Boosted Classifier Tree and Linear Regression 

### Summary of the project scope
• Supervised statistical analysis on market share decrease of NYC yellow cab company in Google Cloud Platform over 225 million records by running linear regression and boosted tree classifier models and visualizing in Data Studio <br />
• Recommended business strategies such as introducing a yellow cab app with more transparent fare calculations, flexible payment options and optimized route to lower driving costs
