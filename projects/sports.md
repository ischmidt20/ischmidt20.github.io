---
title: Sports
---

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
