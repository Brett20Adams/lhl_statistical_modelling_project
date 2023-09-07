# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
My goals in the project were to follow my initial hypotheses about where bike share companies are located in Los Angeles, CA, by extracting information from City Bik.es, Foursquare, and YELP. My initial hypotheses are:

1. Bike share rentals are ideally located near:

    - Bars;
    - Lodgings such as hotels or equivalents; and
    - Transportation locations such as train stations and bus stops/stations.

2. Bike share rentals located near the above increase their value rating on Foursquare or YELP 

These bikes are very popular, especially with tourists and those looking for a faster way of moving around the city near where they are staying. Bike shares near where you are staying or after you exit a train station would allow you to get to where you want to go potentially faster and cheaper than via a car. 

## Process

### Step 1: Load data from City Bik.es, Foursquare, and YELP

City bik.es is the dataset which shows where in any city you can rent a bike that this service is offered. The freely offered API allows users to extract information related to each rental location, such as latitude, longitude, and the number of bikes available when the information is requested.

With the location data from City Bik.es stations, I can search for bars, lodgings, and transportation hubs via Foursquare and YELP, collect all this information into a dataset and begin analysis.

### Step 2: Explore data and analyze hypothesis

Once the data is collected, the work of analyzing begins. The Foursquare and YELP datasets allow a user to extract ratings of the location, which can be used to associate a place's ranking to the City Bik.es station.

## Results
In my initial results for this project, the model results align with my initial hypotheses. The model has an R2 value of 0.244, showing that my feature selections positively correlate with the number of bikes at a given station. There is room for improvement in data collection and cleaning to improve the correlation strength, which could be addressed by:

1. Removing locations found in Foursquare or YELP that do not have ratings. This would allow for data transformation in the modelling stage (applying log functions for left-skewed data)
2. Increase the size of the dataset, currently ~9000 rows. If locations with missing values are removed and replaced with locations with data, the dataset's quality would increase.

## Challenges 
1. YELP's daily API call limits are more restrictive than Foursquare. This slows down data collection, especially for larger datasets.
2. The limit of how many results each API call will return is 50. For an analysis with a radius specified to 1000 m, this limit more than likely excludes many businesses, which limits the analysis
3. The City Bik.es dataset is a more dynamic dataset concerning time, as bikes during the day are constantly being rented and returned each day. 

## Future Goals
My future goals for building upon this analysis are:

1. Collect any missing data from Yelp for stations where the upper limit of API results is encountered.
2. Take advantage of Foursquare's less restrive API, find the most strongly correlated attributes from Foursquare, and use that information to inform the fields returned from Yelp.
3. Add in a plot of where the City Bik.es stations are on a map.
4. Run the API call functions for the City Bik.es data to pull information from each station once or multiple times daily for a week or a month to capture the time element.

