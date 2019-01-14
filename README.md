# IBM Data Science Professional Certificate Capstone Project
# Where to Put Bike Sharing Stations in Bogota

## 1. Introduction
Bogota is ranked as the fifth most traffic congested city of the world. It takes the first place among South American capitals. According to the Global Traffic Scorecard of INRIX (2018), a Bogota citizen loses 75 hours a year in traffic jams. In fact, most Latin American cities have to deal with a rapid and unplanned urban growth which represents a major challenge in mobility and traffic dynamics.

Given this panorama, the promotion of the bicycle as a daily and safe mode of transport has become a common objective within the policies of sustainability and equity in large cities. The use of the bicycle not only reduces carbon emissions within big cities, it also helps to alleviate traffic congestion, decreases travel times, and favors people's health and wellbeing.

Nevertheless, Bogota is famous across the world for being a bike friendly city. It has a population of around eight million people and cycle paths covering more than 360km (220 miles) of the city’s surface. Almost 84,000 people use Bogota’s cycle route network every day, which only stands for around 1% of the total population. This has made local government to ask themselves 'How to make the bicycle a daily and safe means of transport for most people?'.

I think that a bike-borrowing system would be appropriate for a city like Bogota in order to answer this question. This solution also deals with other concerns among citizens which include vandalism, parking or storage, and maintenance. 

But then again another question arises and this is **which would be the ideal locations to put bike-sharing points within the city?**

## 2. Data

Bogota is divided in 112 Units of Zonal Planning (UPZ in Spanish), each one pertaining to one of the 20 total existing boroughs. For this case I used only 3 of the 20 boroughs with their corresponding UPZs, where most of the cultural life and commercial activity of the city takes place. These are **Chapinero**, **Teusaquillo** and **Barrios Unidos**.

I used beautiful soup to scrape this Wikipedia page https://es.wikipedia.org/wiki/Unidades_de_Planeamiento_Zonal and get a dataframe that included each UPZ’s location and the borough to which it belonged.

To solve the problem of ideal location for bike-sharing stations I used the Foursquare API to get the top venues of each UPZ and cluster them using a Density-based spatial (DBSCAN) machine learning algorithm which groups together points that are closely packed together (points with many nearby neighbors), marking as outliers points that lie alone in low-density regions. The center of the clusters would be defined as the location of the bike-sharing stations.

Finally, a GeoJSON file including the bike-path in the city of Bogota helps to visualize how far these stations would be from a bike route.

