---
layout: post
title:      "Class Variables and Methods Lab"
date:       2018-04-21 19:19:05 -0400
permalink:  class_variables_and_methods_lab
---

At this stage of the curriculum, I’m about halfway through Object Oriented Ruby. It’s had me  wondering how building objects in Ruby will apply to projects in real life. I realized today that the Class Variables and Methods Lab I just finished is a good example of when I might build Ruby objects for a real world project. 

In this lab, we were asked to build a class which will hold information about music and artists. We needed to ask the class about its songs; who are the artists and what genres are their songs in? Similar to how I’d imagine a music streaming app processes data about music. Luckily, the lab had a guide for what needed to be built with all the data from the Song class.

First, I had to define my Song class and initialize an instance of a song using `#initialize`. A song is made up of data including an artist, a genre, and a song name, so I initialized my instance of Song with name, artist, and genre as arguments. Then I created an `attr_accessor` for the data, or attributes, so I could use them as instance variables to initialize a song and access them outside of `#initialize` within the whole class.

Next, I had to tell my class to keep track of songs being created, so I made `@@count` and set it at zero because no songs had been made yet. Then, inside `#initialize`, I set my count class variable to increment by one each time a new song was initialized. 

After that, I wrote `#self.count` to ask the Song class to tell me the total number of songs made. I told it to puts the value of the count class variable, which was keeping track of the number of songs. 

I also wrote class methods `#self.genres` and `#self.artists` to give me arrays of the artists and genres created. For both of these methods to produce an array with no duplicated attributes, I had `#self.genres` and `#self.artists` search through `@@genres` and `@@artists` for any duplicate attributes using `#uniq` upon initializing. I then had to set `@@genres` and `@@artists` to an empty array to hold my genres and artists attributes upon initializing. 

The last methods I needed to finish the lab were `#self.genre_count` and `#self.artist_count`. These methods had to return a hash with genre names and artist names as the keys. I needed the value pairs of these keys to be the number of each song in the genre and the number of songs by an artist, in their own methods respectively.

For both methods, I used `#each` to iterate over the hashes and if/else statements. I started out with an empty hash. I had `#each` compare the item (`|genre|` or `|artist|`) in `@@genres` and `@@artists` (which stored the genres and artists attributes for each Song object) to what was being put in my empty hash while iterating. If a genre or artist already existed, it was incremented by one. If a genre or artist did not exist, it was created as a new key/value pair. Lastly, I called my newly built hashes with total counts.

I have more to learn about Object Oriented Ruby. In particular, I’m soaking in as much as I can about when to use `attr_accessor`, `attr_reader`, and `attr_writer`. But I can see the methods we built in this lab could be used in a music streaming app or web player, similar to Spotify or iTunes. 

