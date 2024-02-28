---
toc: true
comments: true
layout: post
title: Individual Blog
description: blog
type: plans
courses: { csse: {week: 0}, csp: {week: 0, categories: [4.A]}, csa: {week: 0} }
categories: [C1.4]
---

### Project Summary
A website with a travel theme where the user can play different games, learning more about different parts of the world. This challenged me and my group to figure out how to connect the database stored in the backend to create functions on our website.

### Feature
User login and signup page which leads to the hompage that gateways to different games

### College Board Requirements
Instructions for input from one of the following: the user, a device, an online datas stream, a file.
- The Signup and Login page require the user to input their name, username, password, and date of birth

Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the users purpose.
- The data from the user is stored into the sqlite data table, where you can see all the users created and the information

![makedebug]({{site.baseurl}}/images/sqlite-screenshot.png)

At least one procedure that contributed to the program's intended purpose where you have defined: the name, return type, one or more parameters.
- Once the user creates an account and logs in, they are able to access the homepage and all the games on the website. 

![makedebug]({{site.baseurl}}/images/homepage-screenshot.png)

An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure.
- This selection and condition function will either redirect the user to the main homepage, or will display a failed login

![makedebug]({{site.baseurl}}/images/sequence-screenshot.png)

Calls to your student-developed procedure.
- The scores from the different games (work in progress) will be added on to the leaderboard, and will display the user's scores

Instructions for output (tactile, audible, visual or ) based on input and program functionality.
- This part of the code tells you whether you got one correct and will add one to your score, to eventually contribute to the leaderboard

![makedebug]({{site.baseurl}}/images/code-screenshot.png)

### Summary
Me and our team could have definently incorporated more database interaction with the user. Everything on the frontend was good, such as our game and our website function. A little more styling could have been added. We struggled a little with the sign up and the login page, and we didn't have enough time to fully incorporate our leaderboard.