# nyc_yellow_cab
analysing NYC yellow cab company 

This project is to be run on Google Cloud Platform. It includes running a Pub/Sub job.

For supervised learning algorithms, it is a common practice to split the data into training and test sets to see how well a model will perform.

For the purpose of this study, we are using 3 datasets - 2 historical datasets from Google's Marketplace in NYC TLC Trips and one newly updated one from pub/sub topic 
projects/pubsub-public-data/topics/taxirides-realtime. 

The following code was used to create table schema for data transfer:
bq mk --time_partitioning_field timestamp --schema ride_id:string,point_idx:integer,latitude:float,longitude:float,timestamp:timestamp,meter_reading:float,meter_increment:float,ride_status:string,passenger_count:integer -t taxirides.realtime

Tlc_yellow_trips_2015 was used as a training set
In cases when it was possible (i.e., appropriate prediction values were present in the test set), realtime table was used as a test set
Otherwise, tlc_yellow_trips_2016 was used as a test set instead.

Machine learning algorithms are mentioned in detail in the PowerPoint, so feel free to use it after you loaded the data :) 
