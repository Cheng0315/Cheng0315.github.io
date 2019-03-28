---
layout: post
title:      "3 Things You Should Know Before Building an E-Commerce Application"
date:       2019-02-22 12:25:52 -0500
permalink:  3_things_you_should_know_before_creating_an_e-commerce_application
---


After spending over 2 weeks working on an e-commerce application and making tons of mistakes, I've learned many things about building an e-commerce application and have gathered three important things I think you should know before start building your own e-commerce application, as they will help you save times and avoid headaches.

1. Store your shopping cart's id - not the cart object or item object - in the session.
When I first started working on my e-commerce application, I thought it would be a good idea to store objects in the session, as it would be easier for me to retrieved data. However, as I got further into the project and started adding in more objects to the session, the session becomes full and stopped taking data I passed to it. Because of that, I had to make many changes in my application to get it to working without having to store object in the session.

2. Know how you want your shopping cart to behave.
For me, I want to create a shopping cart where users can add items to cart without having to log in. To accomplish this, I stored two kinds of data in my session. 1. the id of the user's cart. 2. an array of items' ids if the user is not logged in. If the user is not logged in and adds an item to cart, I would add the item's id to the array in the session. If the user is logged in and adds an item to cart, I would create the association between the item and the user's cart and save them to the database. If the user adds an item to cart without logging in and then decided to log in after, I would iterate through the array of items' ids in the session, find the items, and associate them with the user's current cart. 

3. Know when to use your Google-fu.
Even with good planning, you are going to come across things and issues that you were not expecting or not sure how to solve. Instead of spending over 30 minutes to an hour trying to figure it out, google it. This will saves you a lot of time and let you move on to the next part of your project.

I hope you find one or two of these tips helpful. If you would like to checkout my e-commerce application, you can do so [here](https://github.com/Cheng0315/swift-kart).
