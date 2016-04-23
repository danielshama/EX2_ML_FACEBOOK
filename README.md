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
# The Most Effective Posts
### Data from facebook - Last added Feeds (23/4/2016)
##### Get only the data about post-type and likes amount

```{ echo=FALSE}
feeds <- getNewsfeed(token, n = 600)
posts <- subset(feeds, select = c(type, likes_count))
```

### Display the data on graph
```{echo=FALSE}
data <- table(posts$type)
barplot(data, main="The most effective posts", xlab="Post Type", ylab ="Likes Number")
```


![](likes.jpeg) 

##Conclusions
As you can see, we can clearly see the difference between types of posts. 
There is a clear preference for the posts that contain external links (such as news, etc.). 
Second priority is the type of video content.
