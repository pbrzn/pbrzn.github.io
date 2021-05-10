---
layout: post
title:      "CLI Data Gem Project"
date:       2021-05-10 13:25:38 +0000
permalink:  cli_data_gem_project
---

## "Rex: The Movie Recommendation Bot"

It all began with a problem that has plagued me ever since I first signed up for a Netflix account: I am fundamentally incapable of choosing a movie to watch. This problem always manifests with the same thought, a note of hope and optimism; "I feel like watching a movie." As if to say *this time* it'll be different. *This time* I'll actually *pick* something instead of mindlessly scrolling for an hour before giving up and watching season 4 of The Simpsons for the millionth time.

In the advent of the streaming era, I know I'm not the only person who experiences this issue on a daily basis. That's why, when presented with an opportunity to build a simple web scraping CLI app, I immediately thought of building an app that could recommend movies based on user input of a streaming service – with the option of choosing a movie genre to help narrow down choices. I named this app **Rex**, as in 'recs' or recommendations. It's not anywhere near as clever as I initially thought it was when I came up with it.

Now it was time to make my concept into something tangible. I should note that my first step here *should* have been building my gem and getting my repo set up. Instead I immediately started coding out of excitement and naivité, setting myself up for disaster down the line. More on that later. So I began by coding out my Scraper class. I wanted Rex to be able to parse data from *any* streamer, not just one. I found a website that collates data for all available streaming services – justwatch.com – and was able to pull info for the top 30 movies on any service using Nokogiri and Open-URI. Once my Scraper was able to scrape the data, I built three more classes: Streamer, Movie and Genre. My Streamer class uses the Scraper methods to build out each Streamer object's library of Movie objects. On top of that, anytime a Movie object is initialized, it either finds or builds out new Genre objects, which is then added to each Genre's movies array.

From there it was on to building my CLI class, which carries out the narrative of the gem, providing instructions for the user leading to a recommendation. This was the most fun part of my building my program, as I kept finding new areas of functionality I could add as I was building it out. I added features like a #rerun method that reruns the program starting from scratch with a new streamer, and a custom error that executes any time you misspell any input instead of just breaking the program.

As I was in the middle of building all of my code, that's when I decided to start doing all of the procedural stuff that I neglected to do at the beginning of the project. This is where nearly all of my headaches came from. Again, I cannot stress how smoothly all of this would have gone if I had just done all of this *first* . So I set up my repo, but I didn't have it set up properly so my master branch wasn't actually the master branch (that was the 'main' branch), and I couldn't merge my two branches because they were out of sync with one another. I ended up getting so frustrated with it all I gave up on that repo and started fresh with a new one that was set up properly. Then, after all of my code as done, *that's* when I decided to actually build out my gem. When I started the project I created a Gemfile and set up Bundler to handle dependencies, but that was it. So now I had to build out the rest of the gem and sync that with my Git and Github. Needless to say I created a hot mess for myself. In a way I'm glad I made all of these mistakes. Now I know what *not* to do. Sometimes you just have to learn the hard way.

In the end it was all worth it. I have a CLI gem that functions beautifully that I built all on my own.
