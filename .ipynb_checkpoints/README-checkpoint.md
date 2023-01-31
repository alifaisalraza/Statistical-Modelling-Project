# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
(fill in your description and goals here)

## Process
### (your step 1)
Part 1: Connecting to CityBikes API

City selected: London

Find the network managing bike stands in the city of London. 
Network discovered: ‘Santander-cycles’.

Get all the bike station details belonging to the city of London from ‘CityBikes’ API. 
Total number of bike stations received: 796

Collate bike station information into a csv file.
CSV file name: ’london_city_bikes_stns.csv’
Bike Station details received:
Station_id
Station_name
Latitude
Longitude
Number of Bikes

### (your step 2)
Part 2: Connecting to Foursquare and Yelp APIs

Collect all business outlets information for first 100 bike stations (out of 796 stations) using Four Square API (100 stations selected for ease of analysis and faster data retrieval).
All Business outlets information written to CSV file (‘fsquare_POIs_for_100_BikeStns.csv’)

Collect all business outlets information for first 100 bike stations out of 796 stations using Yelp API.
All Business outlets information written to CSV file (‘yelp_POIs_for_100_BikeStns.csv’)


## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

Total of 790 business outlets information received from API.
POI characteristics received included:
Distance of business from nearest bike station.
Nature of business  (‘Food’, ‘Retail’,…..)
Latitude
Longitude
Majority of business outlet pertained to food (553 out of 790)

Total of 2000 business outlets information received from API.
POI characteristics received included:
Distance of business  from nearest bike station(s).
Number of public reviews for the business.
Public rating of the business.
Latitude
Longitude
Nature of business outlet (‘Food’ only)

Owing to majority of information received pertaining to food outlets, focus of research shifted to ‘Food’ category.
(2533 out of 2790 business from ‘four square’ and ‘yelp’ are food businesses.)

All businesses information from ‘four square’ and ‘yelp’ merged into a single dataset.

Part 3: Joining Data

The merged data was then aggregated for each bike station to derive the following parameters:
Average distance of food businesses (in each bike station zone) from the bike station.
Average number of reviews for food businesses in each bike station zone.
Average rating of food businesses in each bike station zone.

Each bike station had its own characteristic in terms of ‘free bikes’ which was inferred as bike station capacity.

A distribution containing 100 data points was hence created for each bike station.

These data points were then plotted in different graphical forms to understand the nature of distribution.

Four different datasets were analyzed first independently and then together:
Bike capacity of each bike station.
Average distance of food businesses from bike stations.
Average number of review for food businesses.
Average rating of businesses.

Observations:
None of the datasets had normal distributions. There was also little correlation between these datasets.

There were outliers for some datasets, but these couldn’t be due to sampling or data entry error.

SQL lite database:
Name of database: ‘bike_stns_poi’
Tables created:
List of bike stations in city of London
A joined and merged table of bike stations along with food outlets and POI characteristics.
An aggregated table of POIs over each bike station.

Part 4: Building a Model

Forward selection model building adopted.

Dependent variable selected: ‘Average Number of Business Reviews’
Independent variables: 
Average business distance from stations,
Station Bike Capacity,
Average Business Rating

Adjusted R Square received: 0.065. Conclusion: Viable Model not feasible.

New dependent variable selected: ‘Average Business Rating’.
Independent variables: 
Average business distance from stations,
Station Bike Capacity,
Average Number of Business Reviews

Adjusted R Square: 0.017. Conclusion: Viable Model not feasible.


## Challenges 
(discuss challenges you faced in the project)
Lack of POI characteristics from foursquare API. Data bias towards food businessess in both APIs.

## Future Goals
(what would you do if you had more time?)
Analyze other similar APIs to see if they had more useful data to make inferences or a suitable model.
