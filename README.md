# Note-taker
## Description
This application is made for all the users who need to keep track of a lot of information, tasks or goals, it's easy to forget or loose track of important next steps. Being able to take persistent notes allows users to have written information available when needed to reference these important pieces of information. NoteTaker does just this, allows users to take notes via a CLI application that launches in the browser. After launching the application you can keep a tab open in the browser, take and edit notes, and trash the ones that you have marked off your list. Just follow the instructions below to get started.

## Table of Contents 

* [Getting_started](#Getting_started)
* [User Story](#UserStory)
* [Technologies_Used](#Technologies_Used)
* [Code_Snippet](#Code_Snippet)
* [Demo](#Demo)
* [Github_Link](#Github_Link)



## Getting_started
There are a couple dependencies that are have already been provided for you in the package json. All you need to do is open your terminal and run "npm install". This gives you access to the packages that will run the applicaiton, mainly the express.js package. Next, in terminal run "node server.js". This will launched your local host 3000. You can then navigate to your browser and go to https://localhost:3000 where you will be able to start taking and editing notes

## UserStory
AS A user, I want to be able to write and save notes
I WANT to be able to delete notes I've written before
SO THAT I can organize my thoughts and keep track of tasks I need to complete



## Technologies_Used
Express.js - Used for applicatoin end points handling client requests as well as utilizing middle ware for referencing public files in backend funcitions.<br>
Node.js - Used for package managment and to execute JavaScript code outside of a browser to build command line tool for server-side scripting.<br>
Postman - To create, share, test and document APIs<br>
Javascript - Used to base functionality of functions and prompts within the application.<br>
ES6 - Used to build prompts, functions, methods, and classes.<br>
HTML - Used to generate HTML to be displayed in the browser.<br>
CSS - Used to style html elements.<br>
Git - Version control system to track changes to source code<br>
Heroku - Hosts repository that can be deployed to Heroku <br>

## Code_Snippet
The code snippet below handles the request to delete a note. Calling on the  method in express "delete("/api/notes/") we direct to the api path where we can get the id's that have been set to individual notes in our database. We then read the files from that directory, parse out the data that we need in this case the id, then delete that object (note) using id out of the database array . Once that work has been done we still need to display these changes, so we write the updated file from our database back to the browser.
```
app.delete("/api/notes/:id",function(req,res){
  let newId=req.params.id;
  dbJSON=dbJSON.filter(function(note){
    if(newId !==note.id){
      return true;
    }
    else  {
      return false;
  }
});
console.log(dbJSON);
fs.writeFile("db/db.json",JSON.stringify(dbJSON),function(error){
  if(error)
    throw error;
    return res.json(true);
  
});
});
```

## Demo
![](https://drive.google.com/file/d/14Q8pHlC8-h4D6Bux6fXQvUejTbpiKrjg/view)

## Github_Link
[**URL of My Github Repository**](https://github.com/guptaria/Note-taker)<br>


