# World_Weather_Analysis
## 1 Overview of Project

The  project involved retrieving and analyzing weather data for a hypothetical travel company, PlanMyTrip.  PlanMyTrip intends to use the data to recommend ideal hotels, based on clients' weather preferences.  The project involved generating a large list of cities and their weather in order to test the capabilities of the application. Working with APIs, we were able to generate real world data to use for testing. Then, interacting with the program, users are able to select weather preferences and create visual trip itineraries using the google maps API. 

## 2 Approach and Analysis

The project was broken into three main parts:

- Creation of a larger test file of cities and their corresponding weather information
- Enabling user input for desired weather preferences, and
- The development of a trip itinerary and route map 

### 2.1 Retrieve Weather Data

The creation of a large test file of cities and their corresponding weather information started with generating an even larger list of random latitudes and longitudes.  Using the installed Python module CityPy we than determined which city was closest to the random coordinates.  An API call was then made to a weather database , OpenWeather, that holds current data for cities around the world. 

To generate a database of weather information we use the Try Except functionality in Python to see if OpenWeather has data for our random cities.  In figure 1 below you can see that if the weather data is not available, the city was skipped and not added to the database.

![This is a VS screenshot of the Vacation_Itinerary.py code](file://C:\Users\Greg\Carleton\World_Weather_Analysis\Weather_Database\Build_City_Weather.png?lastModify=1640037549 "Figure 1  - Building Database of City Weather Information")

***Figure 1  - Building Database of City Weather Information***

As a final output,  the city weather was written to WeatherPy_Database.csv file for use in testing the other programs in this project.

### 2.2 Create a Customer Travel Destinations Map

The next program requested user input to select desired minimum and maximum temperatures to narrow the search for a vacation get away.   You can see, in the figure 2 below, there are two dialog boxes for user input.  We selected a very narrow range of temperatures, resulting in the selection of 18 cities from the original database of 746 locations.

![This is a VS screenshot of the Vacation_Search.py code](file://C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Search\User_Input_Weather_Choices.png?lastModify=1640037549 "Figure 2 - User Selects Preferred Temperatures")

***Figure 2 - User Selects Preferred Temperatures***

For the cities of interest API calls were made to Google Directions API to get JSON data about local lodging.  Using the same Try Except logic as was performed for weather, only cities with lodgings were kept.  Table 1 below is the first 10 rows of the DataFrame of search results.

![This is a VS screenshot of the Vacation_Search.py code](file://C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Search\WeatherPy_vacation_dataframe.png?lastModify=1640037549 "Table 1 - WeatherPy DataFrame of Search Results")

***Table 1 - WeatherPy DataFrame of Search Results***

This data has been writen to the output file WeatherPy_vacation.csv and it is also shown on the map below with custom markers in figure 3.

![This is a VS screenshot of the Vacation_Itinerary.py code](file://C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Search\WeatherPy_vacation_map.png?lastModify=1640037549 "Figure 3 - WeatherPy Search Results with Custom Markers")

***Figure 3 - WeatherPy Search Results with Custom Markers***



### 2.3 Create a Travel Itinerary Map

The next task was to assemble a travel itinerary for four cities of interest.  The individual dataframes for each city have been assembled into a single view below in table 2.

![This is a VS screenshot of the Vacation_Itinerary.py code](C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Itinerary\WeatherPy_travel_itinerary.png "Table 2 - Itinerary of Selected locations")

***Table 2 - Itinerary of Selected locations***

Making a call to Google's direction layer, a map of the route itinerary was created in figure 4 below.  For future reference I have popped up one of the default markers that google applies. 



![This is a VS screenshot of the Vacation_Itinerary.py code](C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Itinerary\WeatherPy_travel_map.png "Figure 4 - WeatherPy Travel Map with Default Marker")

***Figure 4 - WeatherPy Travel Map with Default Markers***



Google also provides a method to centre the map, I chose to calculate the central lat and lng of the itinerary for the map centre, see figure 5.

![This is a VS screenshot of the Vacation_Itinerary.py code](C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Itinerary\Code_to_centre_travel_map.png "Figure 5 - Code to Centre Map on Itinerary Centre")

***Figure 5 - Code to Centre Map on Itinerary Centre***

If you want to to show a directions map with your own custom markers it is neccessary to first remove the default markers and then apply your own marker layer.  The code for this is shown in figure 6.

![This is a VS screenshot of the Vacation_Itinerary.py code](C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Itinerary\Code_to_replace_map_markers.png "Figure 6 - Custom Code to Replace Default Markers")

***Figure 6 - Custom Code to Replace Default Markers*** 

By using the code in figure 6 we are able to produce a directions map with custom markers for each city on the itinerary.  Figure 7 below illustrates the combination of these layers.

![This is a VS screenshot of the Vacation_Itinerary.py code](C:\Users\Greg\Carleton\World_Weather_Analysis\Vacation_Itinerary\WeatherPy_travel_map_markers.png "Figure 7 - WeatherPy Travel Map with Custom Markers")

***Figure 7 - WeatherPy Travel Map with Custom Markers***

## 3 Summary of Results

PlanMyTrip's project was a great deal of fun, and I believe the client and their users will be very happy with the outcome.  Clients of PlanMyTrip will enjoy quickly being able to get to visual results, in either a tabular or map based view, that clearly identifies the holiday that awaits them.  This product has tremendous opportunities for enrichment, and hopefully PlanMyTrip will fund further development. 
