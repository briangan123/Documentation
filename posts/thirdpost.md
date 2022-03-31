---
title: Check-in 3
description: 
date: 
tags:
layout: layouts/post.njk
---

# API Endpoint Documentation

## Add Word
File Name: addTerm.js

Purpose it serves: The purpose of this file is to add a term the user inputs and add it to the database of terms.

Data Required: Term, Definition, and Context, all of which are varchar variables.

Data Returned: It will give a return the new word the user inputted (for now), and will return the id of the newly added term.

<img width="616" alt="Screen Shot 2022-03-31 at 1 11 18 PM" src="https://user-images.githubusercontent.com/97694891/161111938-b087d0dd-31e2-4229-b5d0-576b87bf9591.png">



## View List
File Name: viewList.js

Purpose it serves: Allows users to view the current list of terms they have compiled.

Data Required: No new information is required for this. The user clicks a button that signals a query to the Planet-Scale database.

Data Returned: All instances in the table.

<img width="743" alt="Screen Shot 2022-03-31 at 1 11 54 PM" src="https://user-images.githubusercontent.com/97694891/161112042-5c3b6b08-be4b-4e2e-a761-c2fa1414e9d5.png">



## Remove Word
File Name: removeTerm.js

Purpose it serves: Removes a term from the glossary.

Data Required: The button requests the id of the word which then signals a SQL query to the Planet-Scale database to delete the term. 

Data Returned: Responds with 200 success if the term is deleted successfully.

<img width="597" alt="Screen Shot 2022-03-31 at 1 12 19 PM" src="https://user-images.githubusercontent.com/97694891/161112115-2115c333-eec9-49a2-92f5-6e8bf37d1c79.png">

