---
title: Optimization
---

### **Supply Chain Management**
![](/assets/162_graph.png){: .image-right height="440px" width="340px"}
- **Co-Authors**: Yulie Park, Christian Simeon, Yifan Xia

For our final project in a linear programming class, we were told to optimize the supply chain for a fictional sugar cane company. Sugar cane was bought from different plantations and shipped to different refineries, who in turn shipped molasses to different customers. There were a number of parameters in our model, including the different shipping costs from location to location, the varying productivities and capacities of the different refineries, and maximum supply and minimum demand. Our decision variables were the amount of sugar cane to buy from each supplier and where to ship it, and how much molasses to ship from each refinery to each customer. I wrote the [AMPL code](/assets/162_ampl.mod.txt) to formulate and solve the model, and drew up a nice diagram displaying our optimal results.


### **Circles of Suck**

![](/assets/circle.png){: .image-right height="350px" width="350px"}
Team A beats Team B, then Team B beats Team C. The transitive property suggests that Team A is better than Team C, but what if Team C also beat Team A?! Redditors on [r/CFB](https://www.reddit.com/r/CFB/) and [r/CollegeBasketball](https://www.reddit.com/r/collegebasketball/) like to call this a "circle of suck", where every team has a transitive win over every other. Computer scientists will recognize this as a Hamiltonian cycle, for a directed graph where nodes represent teams and edges the games between them. I've made Circles of Suck for all of NCAA D1 college basketball, which consists of over 350 teams. Recently, I used the [Concorde solver](http://www.math.uwaterloo.ca/tsp/concorde.html) to find the circle with the maxmimum the combined margin of victory across all the games involved, thus emphasizing the "suckiness". Check them out [here](https://docs.google.com/spreadsheets/d/1CitF3V-Tllnj3VQM9zcF16iQcKSnn0cxGYHm3xkT5PQ/edit?usp=sharing). I also created a "circle of equality" for the 2018-19 Premier League season, which you can see to the right.

### **Problems I'm Interested In, But Haven't Solved**

- **[Pocket Trains](https://apps.apple.com/us/app/pocket-trains/id635931971)** is a mobile game where players operate their own railroad service. There is a select set of cities, and select tracks between them. Players build tracks, then assign them to different railroad lines. There is a fuel cost to traversing a track based on its length, and then a coin reward for delivering cars from one city to another, based on the Euclidean distance between them. We can consider the map to be a graph where the nodes are the cities, and the edges the tracks. The objective is to assign each track to a line such that the overall "straightness" of the system is maximized, with additional constraints on the composition of each line.

- How to solve the **Travelling Salesman Problem** when the salesman uses public transit, and we want to minimze time? Specifically, given the Amtrak rail system in the United States, how can we find the optimal tour that visits a select set of stations? Additionally, what if the salesman is a baseball fan, and wants to see a game at all 30 ballparks? Clearly, this is even harder then the standard TSP, because the costs of travelling between cities varies depending on the previous steps the salesman has taken. Introducing the scheduling constraints adds a whole new layer of complexity, because now our salesman needs to stop in a city and stay to watch a game. Interested in thoughts on this!
