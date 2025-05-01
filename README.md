# Final Project: Statistical Modelling with Python

## Project Goals
The goal of this project is to use CityBikes, Foursquare, and Yelp APIs to determine if a relationship exists between the number of free bikes a station has and the average distance of the closest restaurant or pilates studio. Perhaps there are individuals that use bikeshares to travel to restaurants or pilates studios that are near their station of origin, resulting in those stations having less bikes available. The null hypothesis is the average restaurant distance and average pilates studio distance does not have an effect on the number of free bikes each station has. The alternative hypthesis is that the two avergage distances do have an effect on the number of free bikes availble at each station. 
## Process
### 1. Connecting to CityBikes API
I called the API to retrieve all bike stations in the city of Vancouver. For each bike station, I obtained their latitude, longitude, and number of bikes and stored all results in a dataframe. 
### 2. Connecting to Foursquare and Yelp APIs
I connected to both Foursquare and Yelp APIs to query each bike station from the step above. My points of interest were restaurants and pilates studios, and I determined the Yelp API to have more complete covereage, where I retrieved the average rating and distance of restaurants and pilates studios in a 1000 radius of each bike station. 
### 3. Model Building  
I built a multivariate linear regression model using the statsmodel package to determine if a correlation exists between the independent variables avg_rdist and avg_pdist with the dependant variable free_bikes. 
## Results
The Foursquare API provided the distances of nearby restaurants and pilates studios, as well as providing their category, latitude, longitude, address, and whether it's open or not. In comparison, the Yelp API provided the distances and addresses, as well as the rating, and number of reviews. I determined the Yelp API to provide more complete results as I deemed the ratings and reviews to be more important than whether the location is open or not. 

As for the regression model, the output values suggest that there are no significant correlations between the dependent and independent variables. Of the two independent variables, average pilates distances seems to have a slightly higher impact of the number of free bikes, but the amount is neglible. 
## Challenges & Limitations 
I ran into difficulties when parsing through the JSON results that were retrieved by the Foursquare and Yelp APIs. Specifically, each POI's address returned from the Yelp API was nested in a dictionary, and I had to be mindful of my limited API credits when callling, especially in a loop. The primary limitation of my model is the time that CityBikes APIs was called, which determined the number of free bikes that was saved in my dataframe.

## Future Goals
If I had more time, I would play around with different attributes outputted from the Yelp API to determine if there are variables with stronger correlations. I would also like to apply my model with CityBikes API called at a different time of day, as well as with POI distances from Foursquare instead of Yelp.
