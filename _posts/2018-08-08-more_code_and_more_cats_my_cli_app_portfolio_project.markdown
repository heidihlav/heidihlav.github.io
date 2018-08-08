---
layout: post
title:      "More code and more cats: My CLI App Portfolio Project"
date:       2018-08-08 18:30:31 +0000
permalink:  more_code_and_more_cats_my_cli_app_portfolio_project
---


The CLI App is my first portfolio project in the Flatiron Web Dev program. Come to think of it, it's my first programming project ever. The challenges I faced were varied and many, and I fully expected them. 

We were tasked with using Object Oriented Ruby to build a gem which would scrape a website for information at least one level deep. We were to present a user this information in a CLI (command line application) using list or detailed views. I chose to scrape the [fostering information page of Friends For Life](http://www.friends4life.org/how-to-help/foster), a local no-kill animal shelter where I adopted one of my cats, Bhindi. 

##The trouble with scraping

My original idea was to scrape the page for all of the pets in their foster program, and then to scrape each individual pets' pages for their biographies. I envisioned my app being like an interactive library for users to read about all the adorable cats and dogs who need love and care while they wait for a forever home. 

When I got to writing it, I realized what I wanted to do was going to be way more complicated than I thought. I only saw the treasure at the end of the rainbow - the two separate scraper methods I would need to write to get pet names, pet biography urls, and pet biographies. I didn't realize it until writing out the two methods, but I essentially needed to scrape 21 websites to be able to get all of the information I wanted. Which made for some complicated iterating. I had to get `.gsub` involved to address the space in one cat's name in her biography url, because each pet had a different biography url. I had to append the beginning of the url to each pets' relative path so it would display the correct link in the CLI. 

Then my `.scrape_names` method started returning strange errors at the end of its iterating. Undefined method ".name" for nil class? Undefined method “.name” for Integer:0? 

##Pets class

Since my scraper methods were returning what I wanted only in Pry before the end of the methods’ iterating, I thought maybe I’d look for the issue in my Pets class. I knew I was supposed to be creating Pet objects to store the scraped data, but didn’t know how. They really didn’t seem to have anything to do with my project. I’d get the scraper methods to return the data I want - names, bios, urls - and then call those methods in my CLI. 

Not quite, a fellow student showed me while in a study group. The Pets class creates and stores objects which will hold the data I scraped from the website. I threw around some instance variables for good measure. Told my `@@all` to save its instances, and moved on to my CLI.

##CLI

I felt my CLI was the part I had the least trouble with. I wrote out pseudo-code to begin the project where the user would interact, and felt I had a good idea of the direction all of my code needed to go based on what the user would see. I could greet the user and accept input, but kept hitting errors. It really didn’t occur to me until later to start Pry’ing into my CLI methods to see what was actually being passed there from the scraper methods.

##Redo

I eventually trashed my code written up to that point. I had a gut feeling I wasn’t understanding something to do with classes and iterating, but I couldn’t figure it out. On a Saturday afternoon before the project was due, I opened up Avi’s DailyDeals walkthrough video on one side my screen, and put my code editor on the other, and I spent that afternoon coding with the video. I completely restructured my app. I figured out my scraper methods were returning an array of “nil” strings, because (hello!) `.each` or `.map` returns the original array! I figured out I needed to call the variables I stored my scraped data in as an argument on a new Pets object, which would then store my Pets objects in `@@all` and allow me to iterate on them in my CLI. With help in a study session, I got down the logic in my `.menu` method which would allow the user to see a list of names of pets, choose a pet by number, alert them if they typed in a wrong number, and exit when ready. 

The whole process was definitely difficult, but I have a much better understanding of object classes and scraping. I get to see the end result of everything I learned in Ruby:OO, and I stepped out of my comfort zone to ask for help from fellow students. I’m learning to be less afraid of failure and trust the process. 

[Here’s the link ](https://github.com/heidihlav/foster-cli-app)to my CLI project code, in case you’re curious.  


