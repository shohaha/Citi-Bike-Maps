# Citi-Bike-Maps

In this activity, you’ll use the  Citi Bike API to get the status and location of every Citi Bike station in New York City. This activity also includes a bonus portion. Click [here](https://shohaha.github.io/Citi-Bike-Maps/) to view website.

## Preview of Website

<img width="1190" alt="Screenshot 2022-07-12 at 21 23 58" src="https://user-images.githubusercontent.com/96545188/178588158-31e50022-7da2-46e0-ab03-446c21325607.png">

## Instructions

1. Use the [Citi Bike station information endpoint](https://gbfs.citibikenyc.com/gbfs/en/station_information.json) to get information about the station names and locations.Take a moment to study the data that the endpoint sends back in your browser. Note the following details:

        * Each object in the `stations` array has `station_id`, `name`, `capacity`, `lat`, and `lon` properties.

        * The [logic.js](static/js/logic.js) file contains coordinates that can be used to position a Leaflet map over New York City.

2. Create a function named `createMap` that takes `bikeStations` as an argument. This function will create both the tile layer and an overlay with the pins for each station.

3. Create a second function named `createMarkers` that will take `response` as an argument.

    * Use the response from a future D3 call, loop through the stations, and then create a marker to represent each station.

    * Give each marker a popup to display the name and capacity of its station.

4. In the `createMarkers` function, pass the resulting bike markers to the `createmap` function as a `layerGroup`.

5.  Using D3, retrieve JSON data from the [Citi Bike station information endpoint](https://gbfs.citibikenyc.com/gbfs/en/station_information.json), and then call the `createMarkers` function.

### Bonus 

Try the following bonus activity for an extra challenge. Follow these steps: 

1. Write code to perform a second API call to the [Citi Bike station status endpoint](https://gbfs.citibikenyc.com/gbfs/en/station_status.json). Take a few moments to study the data that the endpoint returns. In particular, notice `station_id`, `num_bikes_available`, `is_installed`, and `is_renting`.

2. Using the data returned from the second API call, add the following functionality:

    * In the popup for each marker, display the number of available bikes.

    * Add a layer control, and then split the markers into these layer groups:

        * **Coming Soon:** This applies if a station isn't yet installed.

        * **Empty Stations:** This applies if a station has no available bikes.

        * **Out of Order:** This applies if a station is installed but not renting.

        * **Low Stations:** This applies if a station has less than five available bikes.

        * **Healthy Stations:** This applies if a marker doesn't fall into any of the previous layer groups.

3. Use a Leaflet plugin to create different types of markers to represent the layers. The following step shows an example map that uses [Leaflet.ExtraMarkers](https://github.com/coryasilva/Leaflet.ExtraMarkers). However, feel free to use another plugin if you prefer.

4. Add a legend to your map to explain the different markers. 

5. Complete the app then edeploy it to GitHub Pages.
