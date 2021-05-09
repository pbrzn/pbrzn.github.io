---
layout: post
title:      "CLI Data Gem: "Rex - The Movie Recommendation Bot""
date:       2021-05-09 00:41:15 +0000
permalink:  cli_data_gem_rex_-_the_movie_recommendation_bot
---

It all began with a problem that has haunted me from the day I first created my Netflix account: I am fundamentally incapable of choosing a movie to watch.

This problem always starts with a statement of hope and intent, "I feel like watching a movie tonight", as if to say *this time* it'll be different... *this time* I'll actually *pick* something instead of mindlessly scrolling for an hour only to end up watching The Simpsons for the millionth time. But, you know what they say about doing the same thing over and over expecting a different result...

I know that I'm not the only one who faces this issue on a nightly basis. So when presented with an opportunity to create a simple web-scraping CLI app, it didn't take long for me to decide that this could be the perfect solution to my problem: an app that recommends a movie based on whatever streaming service or services the user subscribes to. I named it "Rex", as in recommendations or 'recs'. It's not nearly as clever as I thought it was when I came up with it.

I had a dynamite concept and a basic flowchart of how I wanted the CLI to function: utilizing a web scraper to parse streamer and individual movie data into three classes: Streamers, Movies and Genres. It was an amitious undertaking, with collaborationg objects, multiple layers of data to sift through, and potentially a ton of sources to parse through as I want to be able to sift through *any* streamer I wanted, not just one specific streamer. Thankfully I found a web source that aggregates the top movies for all available streamers in one place: justwatch.com. This site was a lifesaver for me when building my gem. The first thing I coded was my Scraper class, using Nokogiri and Open-URI to parse the data from each streamer's page to pull the name and URL extension of each movie, then in a separate method I could parse each movie using the URL extension for the rest of the data I needed: year of release, genre(s), runtime and plot synopsis.

With my Scraper class built to organize all of this data into an array of hashes of movie information, I could build out my remaining classes. My Streamer class uses the Scraper methods to build out it's own library of Movie objects, while each Movie object builds out new Genre objects. From there, it was on to arranging my CLI class, which carries out the narrative of my program. As I dug into this element of my program, I kept finding new areas of functionality I could add, making the program more intuitive. This including creating error messages upon misspelled input, as well as creating methods to receive new recommendations or rerun the program with a new streamer to pull data from.

In spite of the complexity of the project, coding everything out was probably the part I struggled with the least. My real struggle came with all of the procedural elements that facilitate the actual programming: setting up my local environment, building my gem, getting my Github repo up and running and in sync with my local git. Because I wanted to get to the coding part right away, I ended up doing all of the procedural stuff out of order and spending more time fixing the messes I created than actually coding.

All in all, while building this project garnered it's fair share of headaches and frustrations, it was all worth it.  Now I not only have a fully functional program I created all on my own, I learned how important it is to take care in all the prep work before jumping into a project headfirst.
