# PREDICTING THE HITS : CAPSTONE PROJECT

## Problem Statement:

- Imagine you are that music exec, who always had a passion for music but not exactly the voice or instrumental skills. You have an ear for knowing what's on trend, what get's people moving.. Currently you're on the lookout for the next star to join your label but lately you and your team having been striking out in finding said talent. Now you realize that while intuition is a great thing to possess, you need a more reasonable way to aid your decision making process.

- Now imagine you are the artist this music exec is looking for; the next best thing. You've always thought your music was edgy, fun and quite literally, the new wave. You've written and recorded songs of your own, remixed/sampled older songs but your name still isn't quite out there like you hoped it would be. You're hoping for that one big break that will light the way and draw in your fan base.  As an artist, it's more that the money for you. It's a way to share your gift with the world. You're hoping that your music is a source of inspiration, a light in a dark tunnel, a turn up on a Friday or Saturday night or maybe your goal is to be the artist that creates a song so memorable that it draws an instant smile on the face of the listener because it strikes a good memory. Whatever it may be, you have the will and ambition to get there but what you're missing is a solid road map on how to reach your goals.

- Now how do we mirror these two problems and find a solution that is equally beneficial? Here at MusiqGuru's we're here to help you figure out the answer to this conundrum.

### We are looking to answer this question:
**Using the audio features and lyrics of a song, can we predict if a song will make the Billboard Hot-100 top 10 list?**
- How do we do it you may ask? Data! We believe using data to solve our problems!
- In this project, we will use data scrapped from Billboard's Hot-100 list charts over the past 20 years, use Genius' API to pull lyrics and Spotify's API's to pull necessary data that may help in answering our query.

Let's dive in!

## Why the Billboard Hot-100?

### History:
- The Billboard Chart was first introduced to the world in July 1940. At the time, it was rightfully known as the "Music Popularity Chart" but by the late 1950s it was eventually consolidated into the "Hot-100".
- Since then, it has been viewed as a marker of success for an artist. Talents such as Drake, Adele, Arianna Grande and Rihanna are just a few hit names on this list.
- The top 10 songs are also the ones that get the most air play. With increase in airplay, the greater the likelihood of selling more records of course!
- I believe this is a good way to measure success so we'll start with this

## Data Scraping and Cleaning:
### Billboard.py
- I collected about 108,000 rows of data from the Billboard Hot 100 charts dating all the way back to January 1st 2000. I was able to accomplish this thanks to a fabulous API by Allen Guo called Billboard.py
- After collecting the data, I then did some minor cleaning like changing data types and creating new columns for top10 specific songs. It was during this process that I discovered just how competitive it is to make this list!

### Spotipy
- After the collection, it was time to pull audio features, the Spotipy API really came in handy here as it allowed me to pull audio features such as danceability, energy, valence and much more! See the dictionary below.
- I collected a sample of 1000 songs which included top10 songs and randomized songs by new artists as well

### Genius API
- I then scraped lyrics from Genius.com using their API. I was able to collect over 1000 lyrics for the purpose of this project. This included lyrics from our top10 songs and of course the randomized new artist playlist above.

## EDA:

#
