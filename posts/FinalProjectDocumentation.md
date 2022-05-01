---
title: Final Project Documentation
description: This is for the Final Project
date: 
tags:
  - Final Project Documentation post
layout: layouts/post.njk
---

## OpenAPI Document:
https://app.swaggerhub.com/apis/Group-5-IST402/term-glossary-edit/1.0.0

# Final Project Documentation
### OverView
The term glossary project allows users to add, view, and delete terms from a database. This database is leveraged through Planet Scale, a serveless database platform that is compatible with MySQL. As such, our code enables us to utilize SQL queries to perform specific actions depending on what task needs to be done. These are found in the form of API endpoints, of which the term glossary has four. These are the addTerm, removeTerm, termFinder, and ViewList javascript endpoints. 

### AddTerm End Point
The goal of the addTerm api endpoint is to add a term, definition, and context to a database, all of which is information entered by the user. The addTerm endpoint imports the PlanetScale Database. It then utilizes a handler passing an http request and response. The http request stores the term, definition, and context that will be added by the user. An array named terms acts to store the three aforementioned variables of the request query. Finally, after establishing a connection to the PlanetScale Database, a SQL query inserts the term, definition, and context into the database, and assigns it a unique autoincremented numerical id so that the database can execute commands on this specific entry.

![Add term API](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7e9qhqyq5q5f9xm0rqwk.png)

This allows us to write the logic to call add term (api/addterm.js)



![Add Term SRC](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1rgqro7wiwskik4bzfgm.png)

This is how we are able to call add term in our index.htm (src/add-term-form.js)

The add-term-form responds to the user clicking the add-term button on the web application. Once a user clicks this button, the values entered into the term, definition, and context text boxes are stored as variables. A fetch command then connects to the addTerm api endpoint and executes the code using the term, definition, and context values acquired. The resulting data is then returned.

### RemoveTerm Endpoint
The removeTerm api endpoint aims to remove an entry in the database entirely, identifying a specific entry using the unique autoincremented ID each added entry is assigned by the addTerm api endpoint. After importing the PlanetScale Database, a handler function passes an http request and response, with the request retrieving the ID of the term in question. After connecting to the PlanetScale Database, a SQL query is executed that deletes the entry with the same ID as the one returned by the handler. A 200 response is returned if the code is successful. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7tf0rcqgn0ce5krqb47p.png)
API Query

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vb0e09o79ucz44kxffno.png)
Function in SRC/term-list.js

### TermFinder Endpoint
The termFinder api endpoint aims to retrieve a specific term and its definition/context based on a user's input. After importing the PlanetScale api endpoint, a handler function passes an http request and response, with the request retrieving the term entered by the user in the web application. After a connection to the database is secured, a SQL query is executed that aims to return any term within the database that matches the one provided by the user. 

![api/termfinder](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kss17a53itdlxk13ez0a.png)
API that creates term finder to be used in from planet-scale



![SRC/term-finder](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8nlys4cv5d6pa3ktdr0h.png)

Src/term-finder.js file that shows the logic behind our term-finder button.

### ViewList End Point
The viewList api endpoint aims to retrieve all contents currently within the database. After importing the PlanetScale Database, a handler function passes an http request and response,. Once a connection is established with the database, a query is run that selects all the contents in the database, which is returned by the response. 

![View list API](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hwmvid0wx4xoloyvf40n.png)
This allows us to write the logic to call View List (api/viewList.js)


![View List SRC](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gp9u5geuw62jzgibopvn.png)

This is how we are able to call view list (src/term-list.js)

The term-finder is utilized in the retrieval if a specific term specified by the user. Importing LitElement, html, and css creates a base class for our web application (more information on lit can be found in the resources). A constructor is made which passes the variables id (Number), listMap (array), term (String), definition (String), and contrxt (String). Respectively, these variables are set as either null for integers, blank for strings, or an empty array for arrays. The findTerm method utilizes the term input by the user and passes it through the 'api/termFinder'. This data is returned in the form of an array. The render method runs on each update which updates the html of the page to register and returns the results if there are any matches in the database or none at all. 

The term-list is utilized in the deployment of the deletion of a term, viewing a specific term, as well as the viewing of all terms. Importing LitElement, html, and css creates a base class for our web application (more information on lit can be found in the resources). A constructor is made which passes the variables id (Number), listMap (array), term (String), definition (String), and contrxt (String). Respectively, these variables are set as either null for integers, blank for strings, or an empty array for arrays. The method getList uses a fetch command on 'api/viewList', which retrieves and returns the result of the viewList api endpoint. The method deleteTerm takes an argument 'e', which is the entry that is clicked on. The selected entry's ID is then acquired and returned. The entry's ID is then run through the removeTerm api endpoint within a fetch command, and the modified list is then returned. Regardless of which method is used, the render method runs on each update which updates the html of the page to register and visualize any changes which may have occurred in the database. 

## Simplified Workflows of api endpoints
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oadydewm00pkcuvkzcav.jpg)


## Links for term-glossary repo: 
https://github.com/briangan123/term-glossary

https://term-glossary.vercel.app/

## Link to github documentation repo: 
https://github.com/briangan123/Documentation

## Background resources
Vercel: https://vercel.com/docs
Planet Scale: https://docs.planetscale.com/
OpenAPI (Swagger): https://swagger.io/docs/specification/about/ 
Lit: https://lit.dev/docs/v1/






