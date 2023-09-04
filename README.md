# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
My goals in the project were to follow my initial hypotheses about where bike share companies are located in Los Angeles, CA, by extracting information from City Bik.es, Foursquare, and YELP. My initial hypotheses are:

1. Bike share rentals are ideally located near:

    - Bars;
    - Lodgings such as hotels or equivalents; and
    - Transportation locations such as train stations, bus stops/stations.

2. Bike share rentals located near the above increase their value rating on Foursquare or YELP 

My thoughts are that these bikes are very popular with tourists who may be looking for a faster way of moving around the city that is near where they are staying. Bike shares near where you are staying or after you exit a train station would allow for you to get to where you want to go potentially faster and cheaper than via a car. 

## Process

### Step 1: Load data from City Bik.es, Foursquare, and YELP

City bik.es is the dataset which shows where in any city that you can rent a bike that this service is offered. The freely offered API allows a user to extract information related to each rental location, such as latitude, longitude, and the number of bikes available at the time the information is requested.

With the location data from City Bik.es stations, I can search for bars, lodgings, and transportation hubs via Foursquare and YELP, collect all this information into a dataset and begin analysis.

### Step 2: Explore data and analyze hypothesis

Once the data is collected, the work of analyzing begins. The Foursquare and YELP datasets allow a user to extract ratings of the location which can be used to associate the ranking of a place to the City Bik.es station.

## Results
In my intitial results for this project, the model does not validate my initial hypotheses. The model R2 value without any scaling or transformations applied to it is 0.152. This allows for room for improvement in data collection and cleaning which could be addressed by:

1. Removing locations found in Foursquare or YELP that do not have ratings. This would allow for data transformation in the modelling stage (applyiing log functions for left-skewed data)
2. Increase the size of the dataset, currently ~9000 rows. If locations with missing values are removed and replaced with locations with data, the quality of the dataset is increased.

## Challenges 
1. The daily API call limits for YELP was the biggest challenge for me. This rate can be hit much quicker than anticipated.
2. The limit of how many results each API call will return is 50. For an analysis with the radius specified to 1000 m, this limit more than likely excludes many businesses which limits the analysis
3. The City Bik.es dataset is a more dynamic dataset with regard to time as bikes during the day are constantly being rented and returned each day. 

## Future Goals
My future goals for building upon this analysis are:

1. Add in the YELP dataset information.
2. Add in a plot of where the City Bik.es stations are on a map
3. Run the API call functions for the City Bik.es data to pull information from each station once or multiple times per day over the course of a week or a month to capture the time-element.

