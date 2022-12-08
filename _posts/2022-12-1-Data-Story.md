---
layout: post
title:  "Data Story: John Mayer Edition"
author: Aubree Curtis
description: What can spotify data tell us about John Mayer's discography?
image: "/assets/images/john-mayer.jpeg"
---

For the past few blog posts, I've talked about my experience extracting data from Spotify using a free web API to get album and track information for one of my favorite artists -- John Mayer. 

As I mentioned above, I was able to access this data using a free web API from Spotify where I was then able to loop through all of John Mayer's albums and tracks available on his Spotify profile. If you'd like to see the full technical process, I have a [previous blog post](https://acurtis2023.github.io/stat386-projects/2022/10/19/Webscrape.html) that goes into more detail. Once I accessed these tracks and their associated features, I had to do some fundamental data cleaning to get it in a format that would be compatible for further analysis, and then I was ready to go!

When I first started this project, there wasn't anything groundbreaking I wanted to answer -- I just wanted to know what John Mayer's discography looked like! In general, what music of his is the most popular, and is there a reason?

In my [last post](https://acurtis2023.github.io/stat386-projects/2022/11/17/EDA.html), the main outcome variable that I wanted to analyze was his popularity score and what features seemed to impact his track and album popularity. After exploring these relationships, I found that ultimately, his most popular album is currently his most recent release in 2021, entitled *Sob Rock*.

### The Top Album Data Story

After discovering that Sob Rock was the most popular album to date, I created a graphic displaying its main features. *(A dashboard display of this image can be found [here](https://public.tableau.com/app/profile/aubree.curtis/viz/JMMostPopularAlbum/MostPopularAlbum#1))*

![TopAlbum](https://raw.githubusercontent.com/acurtis2023/stat386-projects/main/assets/images/SobRock.png)

It seems that Sob Rock has a pretty decent overall popularity score and also a relatively high danceability score, indicating that this album wasn't just popular among loyal listeners, but also to a relatively mainstream audience. This makes sense considering mainstream music tends to be pretty upbeat and catchy -- i.e. "danceable". 

What I found interesting about this album is that its valence score (indicating how positive or negative the lyrics are) was pretty in the middle, meaning the album is made up of either 1) both happy and sad songs, or 2) songs that are neither happy nor sad, but rather a neutral medium. With this, the data seems to indicate that John Mayer's fans are keen to upbeat ambivalence. Another fun aspect to this album is the abundance of tunes written in the key of E major (:

### Overall

Of course, there are several other directions I could have gone with this dataset besides just looking at John Mayer's most popular albums. If you're curious to see what else I designed using this data (such as his *least* popular album), I created two interactive dashboards that showcase audio features for every [album](https://public.tableau.com/app/profile/aubree.curtis/viz/JohnMayerAlbums/AllAlbums#1), as well as every [track](https://public.tableau.com/app/profile/aubree.curtis/viz/JMTrackInfo/AllSongs?publish=yes) on those albums!

As promised, my entire project is contained within [this github repository](https://github.com/acurtis2023/Spotify_Scrape), which includes the scripts I used to scrape tracks off of spotify, clean the data, and create an exploratory data analysis. 

Hopefully this project has inspired you to think about music that you enjoy, and perhaps now you'll consider analyzing your favorite artist on your own! 

Happy coding!