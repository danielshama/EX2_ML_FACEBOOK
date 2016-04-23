---
title: "Facebook"
author: "Adam & Daniel"
date: "April 23, 2016"
---


### Reuired Libaries

```{ echo=FALSE}
require(XML)
require(RCurl)
require(devtools)
require("Rfacebook")
```

### Data from facebook - Last added Feeds (23/4/2016)
##### Get only data about post-type and likes amount

```{ echo=FALSE}
feeds <- getNewsfeed(token, n = 600)
posts <- subset(feeds, select = c(type, likes_count))
```

### Display the data on graph
```{echo=FALSE}
counts <- table(posts$type)
barplot(counts, main="The most effective posts", xlab="Post Type", ylab ="Likes Number")
```


image: ![](likes.jpeg) 

##Conclusions
1. The home team usually wins the game, you can see in the density graph of final results that the density on home team (2) is higher.
2. Mostly in Halftime score , the home team leads and symmetrically have a similar chance of a tie. 
This implies that the chances of the away team to lead in first half are significantly lower.

Summary: Home teams have more confidence during the game. Away team getting tie result on the first half is a good result for the next half of the game.
