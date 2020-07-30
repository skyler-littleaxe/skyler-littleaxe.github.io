---
layout: post
title:      "CLI Portfolio Project - SWAPI CLI"
date:       2020-07-30 04:34:21 +0000
permalink:  cli_portfolio_project_-_swapi_cli
---


This project was a struggle to say the least. I ran into every single issue possible - from local environment set-up issues, computer issues (had to buy a new desktop in the middle of week one), api failures and so much frustration. I could have easily let that defeat me but each new roadblock renewed my resolve. At this project's end, what insecurities I had regarding coding being the best fit for me are gone. In truth, I have never wanted something more. 


The Star_Wars_Info CLI is a Command-line Interface for a Star Wars API, cleverly named SWAPI. Its main function is to search the collection of characters within the API and retrieve data on a given character or characters, depending on how specific the user is in their query. I wanted to create something that was user-friendly, clean and simple and I feel this CLI achieved that goal. 

The program on startup greets the user and displays commands the user can enter to continue. Looking under the hood, so to speak, the menu_interface method, which is a method contained in the CLI class (essentially the only class within this file that the user has any direct interaction with)  allows the user to enter a command via storing a gets.chomp into the instance variable, @input. It then uses this instance variable as the root for a logic loop that determines what actions to take based on the string stored inside the variable. If the user entered ‘search’ the input_character_search method is called, if they entered ‘exit’ the exit_program method is called and if the user enters anything else the loop recognizes this as an invalid entry and repeats the request.

Assuming ‘search’ was entered and the input_character_search method was called, this method first clears any possible search results that may still be stored in the program from previous runs. It then explains the search function and how specificity can directly affect the return value of the query. Again, storing the entered query in the instance variable @input, it calls on the get_stats method within the Character class, passing through the value stored inside @input as an argument. The self.get_status method is a class method that essentially stores the return values of the API class method API.get_characters - a series of hashed arrays, after iterating over each of them and creating an instance within the Character class. In short, the @@all  class variable becomes an array of instances, each instance possessing properties that were once the values of the hashes they possessed in their native API data structures. Further, the @@all class method becomes accessible within this class via the getter class method self.all.


Going back to the CLI class, after the instances have been created and stored inside the @@all class variable, the CLI iterates over this collection creating a list for the user to choose from and returns a bio of the given character - his or her stats assigned as a property of that instance.  Another loop is created allowing the user to either exit the program or to return to the search via the input_character_search method inside the CLI class - starting the process over again. 

Once exit is entered by the user, all instances stored inside the @@all variable are cleared from the array and a goodbye message is displayed in the terminal essentially closing the program. 


This project was a great exercise and helped solidify any insecurities I had in both my ability to code in ruby and understand the bigger picture as an engineer. I look forward to the challenges ahead of me and hope I can keep this drive as I continue my journey. 

