---
---

Below are a collection of some of my favorite projects I have worked on. They may be born out of research, class assignments, formal extracurriculars, or pure personal interest.

# City Planning x Data Science

### **SB-1120 Policy Brief**
- **Co-Authors**: David Garcia, Julian Tucker

Senate Bill 1120, at the time of this writing, is proposed legislation in California that would allow for single-family residential lots to be split into two equally-sized lots. New construction could be built on the split lot, thus increasing density in residential neighborhoods. The Terner Center here at Berkeley was working on a policy brief in support of SB-1120, and they called on me to run the numbers. Namely, I determined the total counts and percentages of parcels throughout the state to which this new law would apply, which are referenced throughout the report. I'm definitely proud to have published my first "formal" work! Read the [blog post](https://ternercenter.berkeley.edu/news/single-family-zoning-reform-SB-1120) and check out the full brief ([PDF](http://ternercenter.berkeley.edu/uploads/Single-Family_Zoning_Reform_An_Analysis_of_SB_1120.pdf)).

### **Bike Lanes and Displacement**
- **Co-Authors**: Khoa Đỗ, Rowan Pan

For a class assignment, my group and I looked at the relationship between the existence of bike lanes and urban displacement, as measured by the [Urban Displacement Project](https://www.urbandisplacement.org/). I collected bike lane shapefiles from various city open data portals, which I then used to calculate the total length of bike lanes per census tract. My groupmates then used that information to look at potential associations with the typologies created by UDP. We then structured our results as a blog post, which you can read [here](https://www.ocf.berkeley.edu/~ischmidt/2020/cp-101-assignment-3/).

### **BART and Accessibility**
- **Co-Author**: Rowan Pan

For another assignment, my partner and I investigated factors affecting accessibility to BART, particularly looking at the location of the Warm Springs and Fremont stations. I built my own network based on a county street centerlines shapefile, which I used to calculate distance and walking times to BART for various locations. We also used data from the American Community Survey to try to determine the makeup of the neighborhoods these stations serve. Read our report [here](https://www.ocf.berkeley.edu/~ischmidt/2020/cp-101-assignment-2/)!

# Sports

### **San Francisco Giants**
- **Team**: Josh Asuncion, Frank Bruni, Kyle Kishimoto, Tyler Vanderley

This was the first project I led as a member of [SAGB](https://sportsanalytics.berkeley.edu/)! My team and I worked with Michael Gries of the San Francisco Giants, who tasked us with presenting baseball swing data collected with [Blast](https://blastmotion.com/). We were given data in JSON format on hundreds of swings for different minor league players, containing metrics such as "on-plane efficiency" and "attack angle." Our final deliverable was a portfolio of visualizations representing each of the different metrics. We concluded this project by presenting to Giants' front office executives at their spring training facility in Scottsdale, Arizona!

### **u/cbbBot**

I am avid redditor, particularly in sports communities. Many of these subreddits have bots that automatically create and update threads for each game, where users can discuss the game and check scores and statistics. In 2016, I reached out to the moderators of [r/CollegeBasketball](https://www.reddit.com/r/collegebasketball/) suggesting they build such a bot. Their response—"are you volunteering?" I was only in high school, and I was a novice programmer at best, but I figured I'd give it a shot. I started with asking myself *"how do I make a single Reddit post?"* and gradually built up from there. My bot first "deployed" in January 2017, and it has been in use ever since!

Since release, it has undergone a number of rewrites as I have learned more and more, but the basic functionality has remained the same. Every day, the bot automatically schedules thread creation for any games involving Top 25 teams. It also listens for user requests to create threads for other games that may not be automatically scheduled. Then, for each game, one hour before its scheduled start, the bot posts a thread to Reddit with all the information about the game (teams involved, records, TV network, etc.), primarily sourced from ESPN. Throughout the game, the bot will update the thread with the current score and time remaining. In the 3.5 years it has been active, it has accumulated over 140,000 karma! Check out the bot account [u/cbbBot](https://www.reddit.com/user/cbbbot), and the code on [GitHub](https://github.com/ischmidt20/cbbBot/)!

### **Golden State Warriors**
- **Team**: Grant Hurdle, Ari Pickar, Jason Shan, Daniel Waldman

The first project I worked on with SAGB was a consulting project with the Golden State Warriors, where our job was to try to project college basketball players to the NBA. The goal was to find players that may be undervalued—the type of player the Warriors might draft with their second round pick. We worked on this in Spring 2018, and our model was really high on [Kendrick Nunn](https://www.basketball-reference.com/players/n/nunnke01.html). I was a freshman, so I wasn't too involved in the technical details of the model, but I scraped all of the box score and season statistics data from College Basketball Reference, which we used as inputs to our model.

### **Soccer Highlights**

Of course highlights are popular in any sport, but even moreso in soccer. The time zone differences and the sheer quantity of matches lead to a large market for extended highlights, where full matches are condensed down to 10-15 minutes. Creating these highlight packages takes a long time—you have to have watched the match, pinpointed the worthy moments, and then manually sliced your match recording into the different clips and smashed them all back together. To make life easier, I wrote a Python script that automatically creates highlights videos using match events from the [hidden ESPN API](https://gist.github.com/akeaswaran/b48b02f1c94f873c6655e7129910fc3b). See one of the resulting videos [here](https://streamable.com/ck02rs)!

# Modelling

### **Stock Price Analysis**
- **Co-Authors**: Holly Cheek, Justin Han, Leonard Yang

For a Time Series class I took in Spring 2020, our final project was to analyze an anonymized stock price, and predict its future performance. We explored a bunch of different models, ranging from parametric models to SARIMA to basic differencing. We combined all of our findings into a professional-style report, and summarized our findings in a silly blog post. Our model predicted future prices better than at least two-thirds of the class! Not only was this an exercise in different modelling techniques, but in Markdown and LaTeX syntax as well. Read our "blog" [here](https://www.ocf.berkeley.edu/~ischmidt/2020/stat-153-project/), or our more detailed final report [here](assets/stat153.pdf), which also includes all of our R code.

# Maps

### **Sacramento County Housing Suitability**
- **Co-Authors**: Bernard Gburek, Valery Yanez

In Fall 2019, I took a class on Geographic Information Systems (GIS). For a final project, we conducted a suitability analysis to find the best place to construct and sell a home in Sacramento County. We collected geospatial data on all sorts of different features, ranging from recent home sale prices to transporation to flood plains. I even used a centerlines file to build a network to calculate travel times to and from important locations such as schools and Amtrak stations. The end product was a raster-based suitability model to determine the "optimal" place for new construction. See our final suitability map [here](assets/c188.png)!

### **BART and Housing Prices**

Freshman year, I took a class in the geography department simply titled "California." For a new resident, it was a nice primer on CA history, but for our final project, we had to make a [map](assets/50ac.pdf). Being the public transit fan that I am, I chose to look at BART and its relationship with housing prices. I plotted BART stations as points alongside block group polygons joined with American Community Survey data. This was the first map I ever finished, and I'm quite proud of it. My TA didn't like that I didn't label the stations and thought that the system map in the top-left corner was intended to fill space, so I assume she'd rather see text covering all of San Francisco and a big empty Marin Peninsula. This map is less than 3 years old, but note how out-of-date it already is! Thank you BART!

# Linear Programming

### **Supply Chain Management**
- **Co-Authors**: Yulie Park, Christian Simeon, Yifan Xia

For our final project in a linear programming class, we were told to optimize the supply chain for a fictional sugar cane company. Sugar cane was bought from different plantations and shipped to different refineries, who in turn shipped molasses to different customers. There were a number of parameters in our model, including the different shipping costs from location to location, the varying productivities and capacities of the different refineries, and maximum supply and minimum demand. Our decision variables were the amount of sugar cane to buy from each supplier and where to ship it, and how much molasses to ship from each refinery to each customer. I wrote the [AMPL code](assets/162_ampl.mod.txt) to formulate and solve the model, and drew up a nice [diagram](assets/162_graph.png) displaying our optimal results.

### **Circles of Suck**

Team A beats Team B, then Team B beats Team C. The transitive property suggests that Team A is better than Team C, but what if Team C also beat Team A?! Redditors on [r/CFB](https://www.reddit.com/r/CFB/) and [r/CollegeBasketball](https://www.reddit.com/r/collegebasketball/) like to call this a "circle of suck", where every team has a transitive win over every other. Computer scientists will recognize this as a Hamiltonian cycle, for a directed graph where nodes represent teams and edges the games between them. I've made Circles of Suck for all of NCAA D1 college basketball, which consists of over 350 teams. Recently, I used the [Concorde solver](http://www.math.uwaterloo.ca/tsp/concorde.html) to find the circle with the maxmimum the combined margin of victory across all the games involved, thus emphasizing the "suckiness". Check them out [here](https://docs.google.com/spreadsheets/d/1CitF3V-Tllnj3VQM9zcF16iQcKSnn0cxGYHm3xkT5PQ/edit?usp=sharing). I also created a "circle of equality" for the 2018-19 Premier League season, which you can see [here](assets/circle.png)!

### **Problems I'm Interested In, But Haven't Solved**

- **[Pocket Trains](https://apps.apple.com/us/app/pocket-trains/id635931971)** is a mobile game where players operate their own railroad service. There is a select set of cities, and select tracks between them. Players build tracks, then assign them to different railroad lines. There is a fuel cost to traversing a track based on its length, and then a coin reward for delivering cars from one city to another, based on the Euclidean distance between them. We can consider the map to be a graph where the nodes are the cities, and the edges the tracks. The objective is to assign each track to a line such that the overall "straightness" of the system is maximized, with additional constraints on the composition of each line.

- How to solve the **Travelling Salesman Problem** when the salesman uses public transit, and we want to minimze time? Specifically, given the Amtrak rail system in the United States, how can we find the optimal tour that visits a select set of stations? Additionally, what if the salesman is a baseball fan, and wants to see a game at all 30 ballparks? Clearly, this is even harder then the standard TSP, because the costs of travelling between cities varies depending on the previous steps the salesman has taken. Introducing the scheduling constraints adds a whole new layer of complexity, because now our salesman needs to stop in a city and stay to watch a game. Interested in thoughts on this!

# Papers

Here is a sampling of some of the term papers I have written. The quality may not be the best, but what's the point in writing something if nobody but you and your TA is going to read it? Check these out, maybe you'll learn something. ¯\\_(ツ)\_/¯

### **AC Transit Flex**
- **Co-Authors**: Rene Gamino, Elizabeth Rajphackdy

In Spring 2020, I took a class on "urban transportation". Our term paper assignment was to dive in-depth into a specific Bay Area transportation project, from describing its history to analyzing its efficacy. My group chose [AC Transit Flex](http://www.actransit.org/flex/) a relatively new demand-based public transit line that serves the less dense areas of Fremont and Newark. Unfortunately, I can't share the paper, but I just wanted to note how interesting it was reading the [internal reports](http://www.actransit.org/wp-content/uploads/board_memos/14-247b%20Line%20275.Flex%20Service.pdf) about it and listening to the recordings of Board of Directors meetings and all of the different arguments the planners and board members had. I have never actually ridden Flex, because COVID-19 hit before we got a chance to do so.

### **Monaco 2070**

For my first city planning course, our term paper assignment was to pick a city and outlay a "vision" for how that city might look in 50 years. During one of our class discussions, a student mentioned they were considering Malta, and I decided to follow the microstate idea and picked Monaco. Monaco is unique in that it is very small, very rich, and its own country. Recently it is suffering from a severe lack of housing—even in the most expensive city in the world, demand is far exceeding supply. The city can't grow outwards (it either hits water or an international border), and growing upwards would mean losing it's charm, so I decided to base my vision around a radical underground housing plan. I reference other human underground spaces, such as in Montreal, and the informal underground housing market in China. While my plan is certainly quite unrealistic, this was quite a fun research exercise. I also got to improve my non-existent graphic design skills. [Please read!](assets/vision2070.pdf)

### **Food Miles**

This might be the most out-of-place section here, which may be why it's one of the last. In Spring 2019, I took a class called "Food and the Environment", through which we learned all about the food supply chain, its history, and its consequences for the world. For my term paper, I chose to write about the concept of "food miles", which is a measure of how far your food travels from its seeding ground to your plate. The dominant narrative is that more food miles are bad, bad for the environment and bad for your health, but I offer a critique. Check it out [here](assets/foodmiles.pdf)!

### **Japan and Korea Historiography**

Everyone in the Letters & Science College at Berkeley has to take at least one writing class, unless you got a 5 on the AP Lit exam, which I did not. Because I don't really like studying fiction, I chose to take my writing class in the history department. My specific course was focused on the relationship between Japan and Korea from the late nineteenth century through the modern day. My favorite reading from the course was *Tenma*, the story of Genryu, a satirical character bouncing around pre-war Seoul. I found a copy [here](https://ceas.uchicago.edu/sites/ceas.uchicago.edu/files/uploads/Tenma.pdf), although it's not the same translation I read. Anyway, for my term paper for this class, I wrote about the colonial relationship between Japan and Korea, arguing that it had always been Japan's goal to culturally assimilate Korea into its growing empire. This was the first college term paper I ever wrote, so hopefully it's not too bad. [Read it here!](assets/historiography.pdf)
