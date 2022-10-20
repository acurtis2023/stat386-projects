---
layout: post
title:  "Spotify Scrape: John Mayer Edition"
author: Aubree Curtis
description: I scraped the discography of my favorite artist -- let me show you how I did it!
image: "/assets/images/john-mayer.jpeg"
---

John Mayer has got to be one of my favorite artists of all time -- I've seen him in concert 6 times, gone to concerts in 3 different states, and I've got a joint playlist with my mom that shares our top favorite songs. 

Are there certain aspects of John Mayer's artistry that make me so prone to enjoying his music? In today's digital world of music, there are a lot of specially-calculated metrics that define a song -- can I come up with a statistically-backed explanation as to why I like his music? Do all of his songs follow similar patterns and trends in terms of style, key signature, length, etc.?

In order to get a closer look at his music (and to find data for my project that was interesting to me and not too trivial), I decided to try and scrape John Mayer's discography off of Spotify!

### *Hold on, you can legally scrape off of Spotify??*

Spotify is one of the largest, if not the largest, music streaming service providers in the world. Surely a billion-dollar company such as Spotify has numerous hoops that one has to jump through in order to legally access its data, right?

Short answer: yes. However, Spotify does have some established developer tools that help make this process less tedious and clearly define the policies and ethics of accessing their data.

Thankfully, Spotify has a free [Web API](https://developer.spotify.com/documentation/web-api/) that anyone can access when they agree to their Terms of Service. Creating an account on the Spotify Developers website provides you with a unique client id and client secret that authorizes your ability to scrape their data. Not too bad!

![Develop](https://raw.githubusercontent.com/acurtis2023/stat386-projects/main/assets/images/SpotifyDevelop.png)

I won't go super into detail on this process, but if you want to try it on  your own, Spotify has a [quick start guide](https://developer.spotify.com/documentation/web-api/quick-start/) that provides more instruction. 

**NOTE:** One significant aspect of the Spotify Web API is that it only allows scrapes of up to 100 tracks per session. While there may be ways to work around this in a convoluted way, for purposes of this assignment I had permission from Dr. Tass to just focus on the scrape from a singular session. John Mayer has several studio and live albums, which makes his total track list exceed 100 songs. To account for this, I created a playlist of just his studio albums, and used the last couple of indeces to add a few of my favorite live recordings. So while it's not John Mayer's *entire* discography, it's pretty close. 

### I got the API, now what?

Once I had my credentials, I just needed to get the URI for the playlist I wanted to scrape! On the mac desktop app, this can be obtained by pressing the three dots at the top of the playlist, going to *"share"*, and selecting *"Copy playlist URI"* while holding down the *'option'* key. 

![GetURI](https://raw.githubusercontent.com/acurtis2023/stat386-projects/main/assets/images/HowtogetURI.png)

<br>

Once I got the URI, Python (thankfully) has a relatively lightweight package called `Spotipy` that helps decipher the music data accessible from the Spotify Web API. For organizational and security purposes, I saved my client keys and URI in separate json files and called those rather than typing them directly. If you decide to take this route (which is recommended if you will be publishing code in a repository, etc.), you'll want to import the `json` package as well. 

```
import spotipy
from spotipy.oauth2 import SpotifyClientCredentials
import json

# access my json file and assign my private client credentials
credentials = json.load(open('authorization.json')) 
client_id = credentials['client_id']
client_secret = credentials['client_secret']


# access my json file with the playlist uri from my John Mayer playlist
playlist_index = 0
playlists = json.load(open('playlists.json'))
playlist_uri = playlists[playlist_index]['uri']
```

<br>

From here, I assigned my client credentials via spotipy with these two lines of code:
```
client_credentials_manager = SpotifyClientCredentials(client_id=client_id,client_secret=client_secret)
sp = spotipy.Spotify(client_credentials_manager=client_credentials_manager)
```

### Time to scrape

Now that I'm certified, its time to grab the actual data -- aka the fun stuff. 






