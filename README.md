# Marshmalians
Fabiha Ahmed, Max Zlotskiy, Connie Lei, Cynthia Cheng

## Data Description and Source
+ A record for every tree in New York City in 2015 and includes the tree's location by borough and latitude/longitude, species by Latin name and common names, health, and issues with the tree's roots, trunk, and branches.<br>
https://www.kaggle.com/nycparks/tree-census/data

+ A directory of homeless shelters in New York City.<br>
https://data.cityofnewyork.us/Social-Services/Directory-Of-Homebase-Locations/ntcm-2w4k

+ A record of house fires reported and the dispatch data for them.<br>
https://data.cityofnewyork.us/Public-Safety/Fire-Incident-Dispatch-Data/8m42-w767

+ A dataset of rat sightings throughout New York City in 2015.<br>
https://nycopendata.socrata.com/Social-Services/Rat-Sightings/3q43-55fe/data

## Relevance/Significance
Track progress of trees throughout NYC. Get familiar with our city's publicly-funded vegetation. Earth Day! Notice possible effects trees may have on, such as possible effects on number of housefires reported or rat sightings in a certain area.

Although we use a small subset of the data, we find that it is sampled to represent each region fairly. 

## Explanation, in broad strokes if necessary, of how you aim to make this data come alive.
First, we want to show people where the densest populations of curbside trees are. They’ll be on a map of NYC, at their real locations. Next, we want to tell people about the trees – specifically, their species and health. Finally, we want to show the correlation between fires reported and number of curbside trees per zipcode on a scatter plot. 

## What will be shown, absent user interaction?
The map page will show the trees plotted along the NYC map. On the "statistics by borough" page, sums calculated from the entire city will be displayed. The "fire and forestry" page will always show the same scatter plot.

## How will user interact with your visualization?
The user will get to filter what they see on the map, by choosing to see trees, homeless shelters, rat sightings, or all of them together. Some datasets (tree dataset) will provide more information when the user hovers over a ceratin dot or clicks on one. The map isn't the only responsive element. The entire "statistics by borough" page can be controlled by the user. At the top are buttons that let you select for which borough you want to see charts about. The page is reloaded to grab filtered data from the server, and then javascript recreates the pie/bar charts. In addition, the table showing the exact number of species is also filtered by geography.

## What questions will your visualization allow user to explore? What questions will it provoke?
It will allow the user to explore the status of trees today in NYC, their health and condition. It’ll provoke questions of the green space within the city, why does the map look the way it does, etc. It will also draw their attention to other issues such as availability of homeless shelters or a potential rat problem in NYC.

## Explanation of D3 feature utilization.
+ Dots on the map were created with d3. Each represents a tree. Green dots for excellent health, yellow for good, red for poor health. When they are clicked, their information is retreived from d3's cache and displayed in a panel to the right.
+ The pie chart of tree species was created using a library(http://d3pie.org) that works in conjunction with d3.
+ The histogram of trunk diameters was created using vanilla d3. After the data received from the server is parsed by javascript, it is used to create horizontal bars whose width is proportional to the amount of trees with that diameter. A delayed animation is used for this.
+ The scatter plot was created using d3. The scale was hardcoded, but didn't have to be. The dots, on the other hand, were part of the svg and were created by d3. Each of them is animated in the beginning to explode out of one corner of the graph, and then they respond to mouse events to display their coordinates.
