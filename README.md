# World_Weather_Analysis

## Overview of Project 

### Purpose

The purpose of this project is to modify a few features of the PlanMyTrip app.\
Specifically,
- Adding the weather description to the weather data.
- Filter the data for user input temperature zone, to identify potential travel destination, and nearby hotels.
- Choose four cities to create a travel itinerary that shows a travel route between the four cities as well as a marker layer map.

### Resources used
- Data Source : schools_complete.csv, students_complete.csv
- Software : Python 3.7.9, Pandas 1.1.3, Numpy 1.17.0, Anaconda 1.7.2, Jupyter Notebook 6.1.4, citipy, requests 2.24.0, Weather API from OpenWeatherMap, Google Maps Directions API, Google Maps Places API

## Summary 
### Part 1: Retrieving weather data for cities.
Initially, 2000 random latitudes and longitudes were generated. Then, using citipy, 760 cities were identified close to the randomly generated coordinates.\
Using the OpenWeatherMap Weather API, the following weather details (as recorded on 27th May 2021) were recovered for 692 cities.
- City Name
- Country Code
- Latitude and Longitude 
- Maximum Temperature recorded 
- Humidity
- Cloudiness
- Wind Speed
- Weather Description

The weather data for each city was arranged into a DataFrame, and then exported into a csv file (Fig. below).

![city_weather_df](https://user-images.githubusercontent.com/71800628/120078237-12daca80-c074-11eb-9b82-6e242bafb8eb.png)

### Part 2: Retrieving hotel information for cities in preferred weather zone.
The user was asked for the preferred maximum and minimum temperature for vacation places.\
This information was used to filter the cities previously obtained (in Part 1) that fell into the preferred temperature zone, and put into a DataFrame.\
Google Maps Places API was used to recover information for the nearest hotel to these cities, and the hotel name was stored in the DataFrame. Cities for which hotel information could not be retrieved were omitted. This information was stored in a csv file (Fig. below).\
Furthermore, a marker layer map was created with pop-up markers for each city on the map showing the hotel name, as well as the weather data for that city (Fig. below).

![city_hotel_df](https://user-images.githubusercontent.com/71800628/120078253-29812180-c074-11eb-857d-3d22decd8699.png)

![cities_preffered_zone](https://user-images.githubusercontent.com/71800628/120078257-356ce380-c074-11eb-83a5-e2cad42307df.png)

### Part 3: Creating an itinerary.
Four cities in the same country were chosen, where a customer may want to visit. Using the Google Maps Directions API, a route for a rountrip connecting the four cities was created (Fig. below). A marker layer map with pop-up marker, showing hotel and weather details, for these four cities was also created.

![India_route_4cities](https://user-images.githubusercontent.com/71800628/120078262-40c00f00-c074-11eb-87e1-7fefdca50a21.png)
