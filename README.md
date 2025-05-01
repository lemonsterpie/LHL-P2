# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal of this project is to use CityBikes API to request a list of Vancouver bike stations, then use FourSquare and Yelp APIs to request nearby restaurants and pilates studios for each station. The purpose of gathering this data is to determine if a relationship exists between free bikes and the average distance of the nearest restaurant and pilates studio. Perhaps there are individuals that use bikeshares to travel to restaurants or pilates studios that are near their station of origin, resulting in the stations having less bikes available. 

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
## Challenges 
A main challenge I had was in regards to the 

## Future Goals
(what would you do if you had more time?)
