---
layout: post
title:  "Spotify Scrape: John Mayer Edition"
author: Aubree Curtis
description: I scraped the discography of my favorite artist -- let me show you how I did it!
image: "/assets/images/john-mayer.jpeg"
---

John Mayer has got to be one of my favorite artists of all time -- I've seen him in concert 6 times, gone to concerts in 3 different states, and I've got a joint playlist with my mom that shares our top favorite songs. Needless to say, in the spirit of finding data for my project that was interesting to me and not too trivial, I decided to try and scrape John Mayer's discography off of Spotify!

### *You can legally scrape off of Spotify??*

Spotify is one of the largest, if not the largest, music streaming service providers in the world. Surely a billion-dollar company such as Spotify has numerous hoops that one has to jump through in order to legally access its data, right?

Short answer: yes. However, Spotify does have some established developer tools that help make this process less tedious and clearly define the policies and ethics of accessing their data.

Thankfully, Spotify has a free [Web API](https://developer.spotify.com/documentation/web-api/) that anyone can access when they agree to their Terms of Service. Creating an account on the Spotify Developers website provides you with a unique client id and client secret that authorizes your ability to scrape their data. Not too bad!

![Develop](https://raw.githubusercontent.com/acurtis2023/stat386-projects/main/assets/images/SpotifyDevelop.png)

I won't go super into detail on this process, but if you want to try it on  your own, Spotify has a [quick start guide](https://developer.spotify.com/documentation/web-api/quick-start/) that provides more instruction. 

**NOTE**
One significant aspect of the Spotify Web API is that it only allows scrapes of up to 100 tracks per session. While there may be ways to work around this in a convoluted way, for purposes of this assignment I had permission from Dr. Tass to just focus on the scrape from a singular session. John Mayer has several studio and live albums, which makes his total track list exceed 100 songs. To account for this, I created a playlist of just his studio albums, and used the last couple of indeces to add a few of my favorite live recordings. So while it's not John Mayer's *entire* discography, it's pretty close. 

### So I got the API, now what?

Once I had my credentials, I just needed to get the URI for the playlist I wanted to scrape! On the mac desktop app, this can be obtained by pressing the three dots at the top of the playlist, going to *"share"*, and selecting *"Copy playlist URI"* while holding down the *'option'* key. 

![GetURI](https://raw.githubusercontent.com/acurtis2023/stat386-projects/main/assets/images/HowtogetURI.png)

Once I got the URI, Python (thankfully) has a relatively lightweight package called "Spotipy" that helps decipher the music data accessible from the Spotify Web API.

![Spotipy](https://raw.githubusercontent.com/acurtis2023/stat386-projects/main/assets/images/credentials.png)


