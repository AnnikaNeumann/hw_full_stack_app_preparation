# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using React, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

*EDIT: Frontend is now written in React with the command to run `npm start`*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource? GET METHOD

ANSWER: The express.Router and const createRouter function 

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?

ANSWER - Client: The client is responsible for the game structure itself including the components and containers, adding games as in receiving data and post this to the database, handling them, deleting games, css via GameService.js

ANSWER - Server: Responsible for connecting with Mongo DB, it listens to requests such as the CRUD methods including their functionality.


3. What are the the responsibilities of server.js?
ANSWER: server.js connects and listens to the Mongo Database with Mongo's collections in games_hub.games.


4. What are the responsibilities of the `gamesRouter`?

ANSWER - Managing the CRUD methods for show one/all, create, delete, update.  (gamesCollection) 


5. What process does the the client (front-end) use to communicate with the server?

ANSWER - The client creates or deletes the game, which is then being updated in the database via the server - get/post method.


6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs

ANSWER - Second argument is an init object with custom settings like method of POST/DELETE and the body of request like JSON for example. 
    

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

ANSWER - 
router.get('/:id', (req, res) => Show
router.post('/', (req, res) => Create
router.delete('/:id', (req, res) => Delete


8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?


ANSWER -It connects Node.js applications with Mongo DB and works with Data. The driver allows communication to happen for all interactions between the database and the app (client side).



## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

Add to your diagram the dataflow for removing a game.
