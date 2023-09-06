---
title: Bike Lanes— A Gateway to Gentrification
---

by Khoa Đỗ, Rowan Pan, and Isaac Schmidt - CP101

**Note:** Due to expiration of Carto license, maps do not render

### Executive Summary

Bike lanes are often seen as harbingers of gentrification ([Stein](https://www.washingtonpost.com/news/local/wp/2015/11/12/why-are-bike-lanes-such-heated-symbols-of-gentrification/)). Our analytical study attempts to find an association between the existence of bike lanes at gentrification, at the census tract level. We collected geospatial data on bicycle facilities from open data portals from four urban areas across the United States—San Francisco Bay Area, New York, Chicago, and Denver, and joined it with gentrification indicators provided by UC Berkeley professor Dr. Karen Chapple and the [Urban Displacement Project](https://www.urbandisplacement.org/).

After merging the data from the Urban Displacement Project with the bikes data according to GEOID for each city, respectively, we proceeded to conduct analysis looking to find relationships between the existence of bike lanes and their lengths with the processes and severity of displacement dynamics like exclusion and gentrification. What we found is exploratory in nature but fascinating nonetheless. In the four cities we examined, we discovered two distinct model relationships — a schism you can say — of the direction of the relationship between gentrification and bike lanes. In this bike lane and gentrification context, there seems to exist an East-West geographical divide in this regard. To see what we mean, take a tour with us below.

### Outline

1. [Background](#background)

2. [Data Collection and Cleaning](#data-collection-and-cleaning)

3. [Methods](#methods) — [Ethical Concerns](#ethical-concerns)

4. [Results](#results): [San Francisco](#san-francisco-bay-area), [Chicago](#chicago), [Denver](#denver), [New York](#new-york)

5. [Conclusions](#conclusions)

6. [Sources](#sources), [Appendix](#appendix)


### Background

As concerns over the environmental problems of car use grow, and American urban areas slowly realize the consequences of sprawl and the benefits of density, there has been a movement towards making cities easier to navigate for pedestrians and bicyclists. To encourage "active movement," cities have been redesigning streets to incorporate bike lanes and make them more pedestrian-friendly. However, there is also a competing concern over gentrification. Easy to recognize but hard to define, gentrification is a form of neighborhood change characterized by the displacement of one group of people by another. Often, those being forced out are minority or lower-income residents, and the replacements are wealthier and largely white.

The installation of a bike lane on a local street is increasingly seen as a sign of gentrification to come, just like the construction of loft apartments or the opening of a new expensive restaurant. Within the past decade, residents in Portland, Oregon, and Washington, D.C. have protested city plans to run bike lanes along their neighborhood streets, and political support for new lanes in bike-crazed New York has dwindled. While discussions over gentrification are often based on anecdotes and qualitative research, our analysis attempts to determine a quantifiable link between the existence of bike lanes and gentrification.


### Data Collection and Cleaning

The first question we needed to answer is how to categorically determine if a given neighborhood is gentrifying or not. Fortunately, this work has been done for us by the [Urban Displacement Project](https://www.urbandisplacement.org/) (UDP), built by researchers at UC Berkeley. Using data from the U.S. Census Bureau's American Community Survey, and other indicators such as the existence of a commuter rail station, UDP categorizes census tracts in urban areas at different stages of gentrification, such as "At Risk," "Ongoing Exclusion," or "Not Losing Low-Income Households." The website provides data for the San Francisco Bay Area and New York, among other cities, and Dr. Chapple provided us with similar data for the Chicago and Denver areas. For each census tract in the region, we have the gentrification status category as determined by UDP, along with the tract's unique 11-digit FIPS ID.

| ![](/assets/img/bikes-flowchart.png){: height="400px" width="300px"} |
|:--:|
| Flowchart for data processing in ArcMap |
{: .right}

The next step was to determine the strength of the bike network within a tract. From municipal governments' and regional associations' open data portals, we we downloaded line vector shapefiles representing the existing bike facilities in each city. In most cases, the dataset was continuously kept up-to-date, with the most recent updates in February or March 2020, but the Bay Area dataset was dated to October 2018. The data was initially provided in the WGS84 projection, so the first thing we did was project each city's data into the appropriate state plane projection, to ensure more accurate calculations. For each dataset, we then used the Calculate Geometry tool in ArcMap to determine each lane's length in meters.

Each city's original data contained a "class" attribute of some sort, but we needed to standardize it for the purposes of our analysis. We chose the breakdown explained [here](https://www.sfmta.com/getting-around/bike/bike-improvements-toolkit) by the San Francisco Municipal Transportation Agency. Different cities had different starting places, but the end result was that each bike lane was assigned class 1, 2, 3, or 4. Class 3 only represents signage and road markings, as opposed to an actual segregated bike lane, so we chose not to include it in our analysis. Furthermore, the data provided by MTC did not denote any bike lanes as class 4, which limited our analysis in that regard. See the table below for the description of each class, and see the [appendix](#appendix) for how we re-classified each dataset.

| Class | Description |
|:--|:--|
| 1 | Off-street paved bike path, typically shared with pedestrians |
| 2 | Traditional bike lane, painted line separating bikes from vehicles |
| 3 | Not a separated lane, only symbols and signs promoting bike traffic, such as "sharrows" |
| 4 | Protected bike lane, separated from vehicles by a buffer or barrier, a.k.a. "cycle track" |
{: .wide .border}

The next step was to join this line data to the tract as a whole. We downloaded tract boundary TIGER/Line® shapefiles from the U.S. Census Bureau, for California, Colorado, Illinois, and New York, and again projected each into the appropriate state plane projection. We then used the Tabulate Intersection tool to determine what portion of each bike lane fell within each tract. To account for bike lanes along a tract boundary in real life, but which may not be purely coincident in their digitized representations, we included a small tolerance, so that if a bike lane was within 5 meters of a boundary in ArcMap, it would be considered as along that boundary and thus count for both tracts. For each city, the output was a table, where each row corresponded to a "lane-tract"—the specific portion of the bike lane that was in a given tract. Thus each lane could have multiple rows, as could each tract. Also included was the tract's FIPS ID, along with the bike lane section's length (in both meters and miles), its class, and the lane's unique ID.

The resulting table allowed us to aggregate the data to find the total length of bike lanes within or along each tract. This data should perhaps have been normalized, such as by tract population or land area, or even more elaborate metrics such as the total length of the tract's road network, or the size of the workforce it hosts. However, for the sake of time and simplicity, we chose to only look at lane-miles per tract.

Unfortunately, this form of data collection leads to limitations. One is the time mismatch between the bike data and the UDP data. For the most part, the data we collected are a snapshot of bike lanes <em>now</em>, as opposed to 2015, the date of the UDP. Furthermore, with the exception of San Francisco, the bike data only shows data for the central city, and not the region as a whole. Another revolves around the accuracy of the bike data. For example, personal observations showed that the Bay Area dataset was missing some bike lanes in Berkeley. Additionally, when there are bike lines on both sides of the street, the data sometimes treated this as one bike lane and in other cases as two bike lanes, which could lead to an over- or under-counting of the true total length of bike lanes. A deeper analysis would involve spending more time cleaning these datasets to ensure consistency and accuracy. Regardless of these issues, we hope that some conclusions can still be drawn from our research.


### Methods

When we first started this project, our goal was to perform a time series analysis, where we could analyze a given tract over time, tracking its bike facilities and gentrification status over the years. Our hopes were quickly dashed as the UDP considers tracts at only one point in time, and for the most part, the bike lane data did not have information on when they were installed.

Because our data has limited capability, our analysis is more exploratory than truly concrete. For each urban area, we simply provide a chart showing the average total length of bike lanes (classes 1, 2, and 4) across all tracts with a given UDP type. We then briefly discuss these findings, and conclude with some trends that we found across all cities. Because the typologies across urban areas are not 100% consistent, we can not concretely compare the behavior of different typologies across cities, but we still discuss some qualitative insights.


#### Ethical Concerns

The biggest concern with our analysis is that the data is very coarse. One bike lane on a commercial thoroughfare probably does not have that large an effect on the makeup of overall tract, which usually spans dozens of blocks. Secondly, our analysis merely looks at a possible association between bike lanes and gentrification—nothing more. To say that the installation of a bike lane in a low-income neighborhood would or would not help bring about gentrification is misleading and probably incorrect. There are without a doubt underlying factors that impact both.

Another important point is that bike lanes are often used by people who live outside of the census tract. Many commutes and other trips cross multiple tracts, which means the beneficiaries of a bike lane consist of more than just tract residents. Further analysis could incorporate travel surveys or the American Community Survey to try and determine what portion of a bike lane's users are actually local, and how that plays into neighborhood change.

Finally, whenever we build a model, especially in urban analytics, we are always missing context. The Urban Displacement Project has done a terrific job categorizing different neighborhoods, but it can not be taken entirely at face value. Looking at UDP's maps, or our reproductions below, one might assume that two tracts in the a given category might be the "same"—that there is no difference between them. We must make this assumption for the purposes of our analysis, but by doing so we lose the individual stories that make cities, cities. While we present our results below and draw conclusions from them, it is important to be cognizant of what we are looking at and what we are not.

### Results

#### San Francisco Bay Area

![](/assets/img/bikes-sf.png){: .image-center height="466px" width="700px"}

We begin with San Francisco, the closest city to Berkeley of the four. San Francisco is the financial capital of the west coast and one of the most famous—or rather infamous—cities that showcases the splendor and squalor of the modern American city. Vivid juxtaposition of wealthy elites and the homeless living within blocks of each other provides the setting for which the Urban Displacement Project is done. The development of ride-sharing services, especially that of bicycles, is a big development so far. The setting of SF is a perfect place for conducting analysis of gentrification typology and bike lanes. In this table, we can see that in SF, long bike lanes are correlated with generally low risk and mild forms of gentrification. More advanced patterns of displacement, exclusion, and gentrification are in general associated with shorter bike lengths. This realization is the basis of our first model that bike lane length is an indicator of the likelihood a particular community is at risk of being displaced and gentrified in San Francisco. We will call this the "San Francisco Model" going forward.

A clearer image of displacement in the city of San Francisco can be seen in the interactive map below:

<iframe src="https://ischmidt20.carto.com/builder/0dfe957f-86fa-45e8-82c7-b4e653a5cd24/embed" width="100%" height="400" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

<br>

#### Chicago

![](/assets/img/bikes-chicago.png){: .image-center height="450px" width="700px"}

Ah, here we come to the "Windy City". Chicago is the midwestern city we will be examining next. This will be an interesting case study because as we know, Chicago is a major leader in the US in terms of statistics like homicide rates and violent crime, not particularly things a city wants to be associated with. Let us continue our analysis. Before we begin, we would like to point out that the terminology that is being used is slightly different than that of SF but the general idea is the same. The trend seems to have detracted from that of what we see in San Francisco. For one, the highest amount of exclusion taking place in Chicago is correlated with longer average bike lane lengths. Lower levels of gentrification like "Not Currently at Risk of Gentrification" and "Early Ongoing Gentrification" has the lowest average bike lane lengths. We will call this the "Chicago Model" going forward.

This poses as perplexing question: Is the model of Chicago or San Francisco more revealing of more prominent and common patterns of bike lanes and gentrification?

<iframe src="https://ischmidt20.carto.com/builder/99e1c26b-4cf1-4e94-a9d1-c5f358d54837/embed" width="100%" height="400" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

<br>

#### Denver

![](/assets/img/bikes-denver.png){: .image-center height="454px" width="700px"}

The next city on our tour is Denver, Colorado. Although not as famous as its counterparts, Denver is a respectable city in its own right.

We are moving across to different regions of the United States to see if there is any correlation of the different patterns we have seen before with geographical region. Looking at the graph of Denver, it seems to show that Denver seems to resemble the trends of San Francisco more so than Chicago. In Denver, longer bike lane lengths seem to be associated with undergoing but not severe processes of exclusion. So that means the relationship between average bike lane length and severity of gentrification is more closely related to an inverse one.

Hmm, does there exist an East-West divide in the United States in terms of gentrification direction?

<iframe src="https://ischmidt20.carto.com/builder/aa6adc28-58c5-4c68-9d7c-f3f431566f3d/embed" width="100%" height="400" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

<br>

#### New York

![](/assets/img/bikes-newyork.png){: .image-center height="451px" width="700px"}

To act upon our suspicions, let us travel to the "Big Apple".

Here we come to New York, arguably the most famous city in the United States. The natural question becomes: Does New York City resemble more of San Francisco's patterns or Chicago's patterns? Well, clearly the data shows New York more resembles Chicago with an even more clear direction toward the correlation of more gentrification and longer bike lane lengths and away from the San Francisco model. A follow-up question would be "why is this the case"? What are factors in Chicago and New York that leads to this analytical result that we don't reach in San Francisco? Once again, our analysis is exploratory in nature because of the limited capability of the data that we obtain at hand. However, those are very worthwhile questions for urban planners to explore in the future!

<iframe src="https://ischmidt20.carto.com/builder/4deb5cb1-ed7c-4db6-9de5-75593e77f4cd/embed" width="100%" height="400" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

<br>

### Conclusions

The data provided by the Urban Displacement Project and Professor Karen Chapple allowed us to do some preliminary exploratory analysis of urban dynamics that involve the interaction between processes like the varying degrees of exclusion, displacement, and gentrification and match them with manifestations on the ground—literally. We conducted similar analysis for four cities with bike data that UDP was conducted in: San Francisco, Chicago, Denver, and New York. These are all unique cities in their own right, bringing different sets of pre-existing conditions that is fascinating for urban planners to study. In our simple analysis above, we have identified and unveiled something we would like to call the "East-West Urban Divide". This is a term describing the divergence in trends we see between the two western cities (San Francisco and Denver) and eastern cities (New York City, and Chicago). In San Francisco and Denver, more severe forms of exclusion is correlated with shorter bike lane lengths. On the other hand, in New York and Chicago, gentrification is more aligned with longer lengths of bike lanes. The trends are obvious enough to see on the graph but the underlying processes leading to the data visualizations are not so obvious. If possible,  the remaining questions of "Why does this divide exist" and "How did this divide come about" would be very natural extensions to our simple analysis in this project.

If we were to describe our project in five words, those will be:

- Length matters
- Location, Location, Location

These will remain the morals of the story.

Thank you so much for following along with us on our data tour! Thank you CP101 course staff!

#### Sources

- Chong, V. *Bike Facilities Toolkit*. SFMTA; San Francisco Municipal Transportation Agency. 2017, September 18. <[https://www.sfmta.com/getting-around/bike/bike-improvements-toolkit](https://www.sfmta.com/getting-around/bike/bike-improvements-toolkit)>. (accessed May 13 2020).

- City and County of Denver. Existing Bicycle Facilities. 2020. <[https://www.denvergov.org/opendata/dataset/city-and-county-of-denver-existing-denver-bicycle-facilities](https://www.denvergov.org/opendata/dataset/city-and-county-of-denver-existing-denver-bicycle-facilities")>. (accessed April 22 2020).

- City of Chicago. Bike Routes. 2020. <[https://data.cityofchicago.org/Transportation/Bike-Routes/3w5d-sru8](https://data.cityofchicago.org/Transportation/Bike-Routes/3w5d-sru8)>. (accessed April 22 2020).

- City of New York. Bicycle Routes. 2020. <[https://data.cityofnewyork.us/Transportation/Bicycle-Routes/7vsa-caz7](https://data.cityofnewyork.us/Transportation/Bicycle-Routes/7vsa-caz7)>. (accessed April 22 2020).

- Metropolitan Transportation Commission. Regional Bike Facilities. 2018. <[http://opendata.mtc.ca.gov/datasets/regional-bike-facilities](http://opendata.mtc.ca.gov/datasets/regional-bike-facilities">http://opendata.mtc.ca.gov/datasets/regional-bike-facilities)>. (accessed April 27 2020).

- Stein, P. Why are bike lanes such heated symbols of gentrification? *Washington Post*. 2015, November 12. <[https://www.washingtonpost.com/news/local/wp/2015/11/12/why-are-bike-lanes-such-heated-symbols-of-gentrification/](https://www.washingtonpost.com/news/local/wp/2015/11/12/why-are-bike-lanes-such-heated-symbols-of-gentrification/)>. (accessed May 13 2020).

- US Census Bureau, Geography Division. TIGER/Line® Shapefiles: Census Tracts. 2019. <[https://www.census.gov/cgi-bin/geo/shapefiles/](https://www.census.gov/cgi-bin/geo/shapefiles/)>. (accessed May 4 2020).

- Zuk, M., & Chapple, K. 2015. Urban Displacement Project. <[https://www.urbandisplacement.org/](https://www.urbandisplacement.org/)>. Additional data provided by Chapple.


#### Appendix

For each city, here is how we re-classified each bike lane. The San Francisco Bay Area data already provided a numerical class feature so we did not need to do make any adjustments. For New York, the process was a little more elaborate. There were two fields we considered: `tf_facility` and `ft_facility`. If both were of the same class, we used that class. In the case where one was filled and the other was empty, we used the filled field. In the case where both were filled, but were of different class, we picked the "lower" class, using the order 1, 4, 2, 3.

```
Chicago				Denver				New York
displayrou		Class	EXISTING_F		Class	tf_facility		Class
ACCESS PATH		1	Bike Lane		2	Bike-Friendly Parking	3
BIKE LANE		2	Buffered Bike Lane	4	Boardwalk		1
BUFFERED BIKE LANE	4	Neighborhood Bikeway	3	Buffered		4
NEIGHBORHOOD GREENWAY	3	Protected Bike Lane	4	Buffered Conventional	4
OFF-STREET TRAIL	-	Shared Roadway		3	Curbside		2
PROTECTED BIKE LANE	4	Shared Use Path		1	Dirt Trail		-
SHARED-LANE		3	Trail			-	Greenway		1
								Link			1
								Protected Path		4
								Sharrows		3
								Sidewalk		1
								Signed Route		3
								Standard		2
```
