---
layout: post
title: Movebank - Spanish Kestrels 
description: Exploratory Data Analysis (EDA), GIS 
image: assets/images/Kestrel.jpg
nav-menu: false
---

Whenever I go somewhere, I'm quick to try to learn the local plants and animals that call a place *home*. It's a large portion of what makes me feel like I belong somewhere, and the UK was no exception. Magpies, Muntjac, Sarcococca - there were no shortage of new neighbors to learn about. I still remember seeing a Kestrel here for the first time, awkwardly craning my neck to catch a glimpse of it alongside the A-14, wings aflutter as it searched for breakfast. I've always liked hawks, having grown up watching Ospreys catching fish, and the Kestrel was no exception. What made it new was its ability to hover in place, a technique known as Wind Hovering. You'll often see them over country fields, quick and keen-eyed, suspended in the air in a way that almost seems more reminiscent of a Hummingbird than any sort of hawk. I find them intriguing, and as I'm so oft to do, this makes me want to make sense of them on some level. 

I want to use this page as a sort of journal, documenting how I’ve explored kestrels and their behavior through the lens I know best: data science and mapping. I don't expect any of it to amuse anyone besides myself, but for me it serves the dual purpose of both investigating something I'm interested in, and hopefully re-invigorating my interest in data science.

This idea was made possible through the creation of [Movebank.org](https://www.movebank.org/),  a fantastic reposity of animal tracking data from around the world. I found a dataset that [tracked several Kestrels through southern Spain](https://www.movebank.org/cms/webapp?gwt_fragment=page=studies,path=study2970193504). It covered a population of 61 individuals, providing over roughly 2,500,000 data points about their movements over a period of six years. 

### Key Variables
Along with the dataset, Movebank provides a really good set of definitions for each variable they collect against. There's a few variables that stood out to me, that maybe I'll get to use or look into in some way. 

 - **gls:light-level**: According to the definition provided, this refers to "Light-level values measured by a solar geolocator. Range and units may vary by provider and tag settings. Best practice is to define values in the reference data." I don't see any additional information about this variable, but I wonder if I could use this as a proxy for when they're in their nest? They are active between dawn and dusk, so I could imagine this having value in filtering out un-needed records. 
 
 - **animal-sex**: The additional reference data provided by the authors also provides sex information for each tracked individual, which I think could be interesting if I tried to apply a machine learning model to this data. That would be a long ways out, but maybe there's enough in their activity to indicate the gender of a given bird. Doing that from just geospatial data would be interesting.  

### Identifying Active Periods
My first goal was to look into how I could tell when the birds were in their nest, or were active. I learned that Kestrels are diurnal (daytime) hunters and rely almost entirely on sight to locate their prey. With that in mind, maybe we could use the gls:light-level variable as a proxy for when they're in their nest, and find a certain threshold that could help us separate out our data into 'active' and 'passive' subsets. We can plot this data as a first test of this idea:

    plt.scatter(kestrel['timestamp'].dt.hour, kestrel['gls:light-level'])

From this plot, we can get a quick idea of what our cut-offs might be.
Links if I continue this:
https://www.timeanddate.com/weather/@2519128/historic?month=1&year=2025
https://www.movebank.org/cms/movebank-content/movebank-attribute-dictionary#event_attributes
https://open-meteo.com/en/docs/historical-forecast-api?start_date=2024-11-28&end_date=2025-06-29&hourly=wind_speed_180m,wind_direction_180m,wind_speed_10m,wind_direction_10m&latitude=37.0427&longitude=6.4344&timezone=auto&daily=rain_sum,temperature_2m_max,temperature_2m_min#hourly_weather_variables
https://www.aemet.es/en/eltiempo/observacion/ultimosdatos?k=and&w=0
https://www.movebank.org/cms/webapp?gwt_fragment=page%3Dstudies%2Cpath%3Dstudy2970193504%2Bfile

    

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYxNTEzMzkzNywtOTUxODQ4NjYyLDIwMD
c0OTg3NzAsLTYyNjQ3MjA4NiwxMDk3OTAzODI2LC0yMTQ1MjM4
NDUxLDEzMTcyMjkzODAsNTc0MzYxOTYwLDIwMTM0MTU0MzUsMT
A2ODQ2OTA5NiwtNjQwMzc4NDg1LC0xOTgyNTMyMTQzLDQ5Nzgx
ODgxMF19
-->