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

 - **gls:light-level**: According to the definition provided, this refers to "Light-level values measured by a solar geolocator. Range and units may vary by provider and tag settings. Best practice is to define values in the reference data." I don't see any additional information about this variable, but I wonder if I could use this as a proxy for when they're in their nest? They're active between dawn and dusk, so I could  

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNDU3MzMxMjgsNTc0MzYxOTYwLDIwMT
M0MTU0MzUsMTA2ODQ2OTA5NiwtNjQwMzc4NDg1LC0xOTgyNTMy
MTQzLDQ5NzgxODgxMF19
-->