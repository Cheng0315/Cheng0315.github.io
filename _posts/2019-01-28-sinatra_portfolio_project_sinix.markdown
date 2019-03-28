---
layout: post
title:      "Sinatra Project: Sinix"
date:       2019-01-28 22:53:17 -0500
permalink:  sinatra_portfolio_project_sinix
---


Creating a web application from scratch can be intimidating for new web developers. For my Sinatra Project, I created an application that generates the structures of a sinatra web application to help new developers structure their web applications. 

To generate the structures for an application, all one needs to do is clone the [repository](http://github.com/Cheng0315/sinix), then follow the instructions on the README.MD file. After the installation, run the application in the browser, then create an account. Once inside the account, click on 'create new project’ at the top left of the screen, then select the number of models for the project, then input the name of the project, the name of the models, and a description about the project. After that, click ‘create project’ and the application will generate the names for the folders and files for the project and the codes that go inside those files. All one needs to do after that are create the folders and files similar to the ones shown in the application, then copy the code from the application and paste them inside the appropriate files of the project, and the project’s structure is done. 

### My approach to creating this application

I started by coming up with a plan on how I should work on this project from the beginning to the end. The plan was to start with the skeleton of the application, which are the models, classes, folders, files, and gems. Then I'll work on the user model, which are the user's view files and the user's routes inside the user controllers class. After that, I'll work on the other two models (project and project-type) and finish the project with css and bootstrap 4. 

With some planning, I was able to set up my project's skeleton quickly and finish with the user model. I continued onto the project model and created a form that asks the user to select a number for the number of models he/she will use for the project. Then I created another form that takes in that number and uses that number to generate the number of input fields for the model’s name. Along with the input fields, I also created two additional input fields, one for the project's name and another for the description. Then I created a route that takes in those inputs and uses the parameter that contains the project's name to create an instance of the project class. Then I stored the models’ names inside the instance project, however, I was getting error messages saying that it could not store the names of the models. I wasn't sure why, so I put 'binding.pry' inside the route and had a closer look at the parameters. I realized that because I'm using a loop to create the input fields for the models, the names of all of the models are stored in a nested hash, and hash is not a data type in the database; therefore, I cannot store the names of the models inside the instance project. 

One solution I came up with was to retrieve the models’ names from the parameters and put them in an array, then join them on a space and store them as a string inside an attribute of the instance project, and when I want to retrieved the models name, I'll just split them on space and get the names of the models that way. But that wouldn't be a good way to store data. Another solution I came up with, and decided to go with, was to add another model called 'model' and associate it with the project model as a belongs_to relationship and give it an attribute of name. That way I can just create instances of the model class and push them into the instance project's models array and store them that way. With that, I was able to create an instance project that contains the names of its models, and I can edit and update the instance project and models as I please. Then I finished the project with css and Bootstrap 4.

