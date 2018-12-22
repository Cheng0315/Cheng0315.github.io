---
layout: post
title:      "CLI Portfolio Project: Beautiful Places to Visit"
date:       2018-12-20 21:43:58 -0500
permalink:  cli_portfolio_project_beautiful_places_to_visit
---


I created a Ruby Gem that provides a command line interface to the user to view information on beautiful places they can visit. This gem focuses on scraping data from a web page and displaying that data to the user based on the his/her input. 

Before starting on the project, I thought to myself, "what will be the best way to approach this project, how many classes will I need, how will each of these classes behave, how will my program flow from the beginning to the end, and what will the output be like after my project is done." 

After some planning, I came up with four classes: Scraper, CLI, US Destination, and International Destination. Each of these classes will have their own function. The cli class will handle printing instructions for the user, getting the user input, and retrieving data from the two destination classes. The scraper class will scrape data from the web page and pass those data as arguments into either the US or the International class, where each of those classes will create their own destination objects based on the arguments that get passed in. 

I began my coding with the cli class, implementing methods that print instructions for the user, ask the user for input, and print data as if they were retrieved from the destination classes. 

After the cli class worked properly, I started working on the scraping class. As I got to the scraping part, I realized that all the html elements that contain the data I needed for all my destinations are on the same level of a single parent. That is, each html element that contains information about a destination, for all the destinations, is the first generation child of a single html element. My thought process was, "How do I collect these data efficiently? I can't just select each element at a time, collect the data, and store them in their proper hash, as that will go against the principle of code efficiency." I tried to select the element that contains the name of the destination (<h2></h2>, for example) using css selector and at the same time tried to select the other elements that contain data related to that destination, but all I got was errors, as selecting an element, or any element, will only allow access to content inside that element, not content inside other elements that are on the same level of the same parent or anywhere else. Therefore, this method is invalid. 

I decided to break away from the scraping class and started working on the destination classes. I wanted to have two destination classes, one for creating destination objects in the US and another for creating destination objects outside of the US. I wanted to create a distinction between the two. However, as I started to build them, I started to notice the similarities between the two, and as every developer knows, "Don't Repeat Yourself." I decided to delete one of the destination classes and change the name of the other to just "Destination."

After eliminating one of my two destination classes, I started to work on my scraping class again. I came to the solution that I will select an element by its type, which will allow me access to the contents of other elements of the same type, and collect all the data I need and store them in an array. For instance, if I select the <h2></h2> element, I can access all the name of the destinations, collect them, and store them separately in an array. I did the same thing for the other data - e.g. the average airfare to travel to each destination, the average cost per night for hotel, etc. Then I used the each_with_index enumerator to iterate through the destinations array and used the index to grab the other data related to the destination from the other arrays and pass them as arguments into the destination class. Doing so allowed me to create the destination objects I wanted and stored them in a array in the destination class. 

After having all my classes working properly and interacting with one another, I started to think of how I want to retrieve the data (destination object) from the destination class. I decided to go with a retrieve_data method that will retrieve a destination object based on the user's input. With that, I was able to complete my cli project that displayed information on beautiful places the user can visit based on the user input.
