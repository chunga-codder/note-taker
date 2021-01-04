# note-taker



this is how the app will look like after deployment

![Capture 2](https://user-images.githubusercontent.com/71171928/103551427-9d931100-4eaa-11eb-883f-8044b3a3fe43.PNG)


![note-taker](https://user-images.githubusercontent.com/71171928/103551443-a1bf2e80-4eaa-11eb-963a-dbd28e18606b.PNG)

## LINKS TO DEPLOYED AND GITHUB APP

### GIT HUB : 
https://github.com/chunga-codder/note-taker

### HEROKU :

https://note-tk.herokuapp.com/


## VIDEO LINK :

https://drive.google.com/file/d/1UR9BbCcA5ZzwIJudZAAdxJFVY6VNIX-p/view



# ABOUT

Express Note Taker

The purpose of this project was to build an application that can write, save, and delete notes using an express backend to save and retrieve note data from a JSON file. The project user story is below.

AS A user, I want to be able to write and save notes

I WANT to be able to delete notes I've written before

SO THAT I can organize my thoughts and keep track of tasks I need to complete
The criteria for a successful project are below:

Application should allow users to create and save notes.

Application should allow users to view previously saved notes.

Application should allow users to delete previously saved notes.





  ## APPROACH
  As the front end was already created, I needed to look at connecting this to the backend. I broke down the problem into smaller objectives:

Start a server using Express
Link the HTML to get and post requests in the backend JavaScript
Write the user's notes to the server's JSON file with unique IDs
The post method needs to write the note to the JSON file for retrieval
The get method needs to retrieve notes from the server for viewing
The delete method needs to locate and delete specific notes from the server

## CHALENGES

 My first challenge arose at the very beginning of the project: understanding pathing with Express. I needed to complete my understanding of the usage of path.join and the meaning of __dirname, which required deep reading into documentation of the package. On completion I was able to successfully link the frontend content to the server.

My second challenge was then to write the user's notes to the server. As the JSON file already exists, I used the file system package to retrieve it, parsing the file in order to write the new note to it. This challenge follows into the need to store each note with a unique ID for the delete function. I needed a means to call the selected note in order to remove it from the array. To do this, every new note saved is given an ID equal to its position in the array to start. The idea is to rewrite these IDs to match each note's new position in the array when one entry is removed.

I struggled with finding a working method for the delete function. Eventually after some debugging I found the best method to remove a note using my unique IDs was to use a filter that would return an array with every entry except the entry I was looking for. By rewriting the unique IDs of each entry after the removal, I was able to ensure that every note's ID was equal to their position in the array, thus the delete function would remove only the selected note every time.

Another challenge I had was applying the * path in my get requests. When I tried to apply the * path for the index page, I found that it would override the other unique paths I had defined. Eventually I found out that the order of get requests reflects the order of precedence, so defining the * path first would prevent the other paths from working properly! In the end, moving this path to the end of my get requests solved the issue.


## DEVELOPMENT

Below are the steps I took to create the application as it is so far. The most difficult aspect of this application for me was using a constructor to cover all aspects of the notes (writing, reading, saving, deleting).

Created and linked the initial files (JS files, HTML files, JSON files).

Downloaded all dependecies using npm.

Created all routes and verified them with small tests using Postman.

Created a constructor which contained functions for each element of the notes (writing, reading, saving, deleting).

Verify the functionality of the application, then deploy to Heroku.

Testing
