---
layout: post
title:      "3 Things You Should Know Before Building an E-Commerce Application"
date:       2019-02-22 12:25:52 -0500
permalink:  3_things_you_should_know_before_creating_an_e-commerce_application
---


After spending over 2 weeks working on an e-commerce application and making tons of mistakes, I've learned many things about building an e-commerce application and have gathered three important things I think you should know before you start building your own e-commerce application as they will help you save times and avoid headaches.

1. Store your shopping cart's id and items' ids - not the cart object or item object - in the session.
When I first started my e-commerce application, I thought it would be a good idea to store item objects in the session as it would be it easier for me to retrieved data that way. However, as I got further into the project and started adding in more items objects to the session, I realized that there are only so much data the session can store before it reach its maximum capacity and can no longer store any data I passed to it. Because of that, I had to make many changes in my application to get my application to work properly without having to store items object in the session.

2. Know how to create a working shopping cart.
By that, I mean know how to create a shopping cart that is similar to Amazon and eBay shopping cart, where users can add items to cart without having to log in. To accomplish this, store two kinds of data in your session. 1. the id of the user's cart if the user is logged in. 2. an array to store ids of items if the user is not logged in. If the user adds an item to cart and is not logged in, add the item id to the array in the session. If the user adds an item to the cart and is logged in, create the association between the cart and the item and save them to the database. If the user adds item to cart without logging in and then decided to log in afterward, iterate through the session array, find the items based on the ids, and associate them with the user's current cart. 

3. Know how to use your Google-fu.
Even with good planning, you are going to come across things and issues that you are not expecting or not sure how to solve. Instead of spending 30 minutes to an hour trying to figure it out, google it. There are many times when I tried to solve a difficult coding problem in my applications and once I solved it I realized that the code I came up with is not very efficient or is repetitive. Most of the times when you searched for solution through google you will find that the solutions are quite efficient and you can learn a lot of things from those solutions.

That's it for this blog. I hope you find one or two of these tips helpful. If you would like to checkout my e-commerce application, you can do so [here](https://github.com/Cheng0315/swift-kart).
