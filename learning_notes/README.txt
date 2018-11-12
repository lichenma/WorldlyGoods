//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Introduction

This project involves creating a NetWorth management application using the MERN stack. The application will allow the user to add, update, delete and display their total assets and expenses and will serve as an exercise to learn web application development. 

The methodology and steps used in this project were adapted from a cloudboost tutorial
https://blog.cloudboost.io/creating-your-first-mern-stack-application-b6604d12e4d3
//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//The Stack 
A quick introduction and description of the technologies involved in this stack 

//MongoDB
MongoDB is a cross-platform document oriented database and leading NoSQL database and works on the concept of collection and document. A "DATABASE" is a physical container for collections, each database gets its own set of files on the file system and a single MongoDB server typically has multiple databases. A "COLLECTION" is a group of MongoDB documents and is the equivalent of a RDBMS table. It exists within a single data and do not enforce a schema. A "DOCUMENT" is a set of key-value pairs and documents in the same collection do not need to have the same set of fields or structure and common fields in a collection's documents may hold different types of data. 

MongoDB is schema-less which means that one collection can hold different documents and the number of fields, content and size of the document can differ from one document to another. It is also a Document Oriented Storage which means that data is stored in the form of JSON style documents and is very easy to scale. 

//Express
Express.js is a minimal and flexible web application framework for Node.js, and is designed for building web/mobile applications and APIs. It is the backend part of the MEAN stack together with MongoDB database and AngularJS frontend framework. It facilitates the rapid development of Node based Web applications and has the following core features: 
	-allows to set up middlewares to respond to HTTP Requests
	-Defines a routing table used to perform different actions based on HTTP Method and URL
	-Allows to dynamically render HTML Pages based on passing arguments to templates

//React
ReactJS is a JavaScript library for building user interfaces and is maintained by Facebook 

//Angular
AngularJs is a JavaScript based front end web application framework mainly maintained by Google 

//Node
Node.js is an open source server environment that uses JavaScript on the server and uses asynchronous programming. A common task for a web server can be to open a file on the server and return the content to the client. In PHP or ASP the file request is handled as follows: 

	1. Sends the task to the computer's file system
	2. Waits while the file system open and reads the file
	3. Returns the content to the client
	4. Ready to handle the next request

In Node.js the file request is handled as follows: 
	
	1. Sends the task to the computer's file system
	2. Ready to handle the next request
	3. When the file system has opened and read the file, the server returns the content to the client

Node.js eliminates the waiting and simply continues with the next request- it runs a single threaded, non blocking, asynchronously programming which is very memory efficient. 

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 1: Creating basic React Application

To get us started we begin by creating a basic react application. We will be using the create-react-app package and this package could be installed as follows:

"npm i -g create-react-app"

Now use create-react-app package to create a new react application:

"create-react-app net-worth"

This creates a new folder called net-worth and install the react dependencies. Execute "npm start" command to run this application and it should display the basic react app on localhost

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 2: Install the dependencies

Run the following command to install the dependencies and update the package.json file:

"npm i axios babel-cli body-parser express mongoose nodemon react-bootstrap react-modal react-router-dom --SAVE" 

	-axios is used to send requests to the server or to fetch/insert data
	-body-parser parses the request bodies and we can access information in the request via req.body
	-babel-cli will be used to compile files from the command line
	-express is a web application framework for NodeJS
	-mongoose is an ODM framework for MongoDB
	-nodemone automatically restarts the server whenever the code changes
	-react-bootstrap lets us use bootstrap components with React
	-react-modal lets us create a modal dialog in React
	-react-router-dom lets us use React router

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 3: Re-arrange the React application

'ejs' is a template engine that lets you generate html markup with plain JavaScript

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 4: Server-side configurations

We will now create the server and configure it. In our server.js file, we create a create a server and set the "view engine" to "ejs" as introduced earlier. We also tell the server where our template files are placed and all of our front-end code will reside inside the client folder as already discussed. We are referring to a file called routes.js inside the routes directory to get the routes

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 5: Bundle the front and back-end

To run the MERN application we need to bundle together the React front end and Node back-end. We will be using webpack for this purpose. The file "root/bin/www.js" will server as the configuration file for the server. We will also configure Webpack using the javascript configuration file "root/webpack.config.js". Webpack will bundle the JavaScript files together and generate a bundle .js file inside the client folder. 

//Webpack 
Webpack is a module bundler whose main purpose is to bundle JavaScript files for usage in a browser and takes modules with dependencies and generates static assets representing those modules. 

This will have successfully created an ERN stack application, and the database MongoDB will be incorporated in the following steps. 

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 6: Integrating the database with back-end

Mongo database is set up with MLAB or MongoDB Atlas (cloud providers: Amazon Web Service, Google Cloud Platform, Microsoft Azure) which are Database-as-a-Service for MongoDB which offer a free cloud hosting but only up to a certain point. Create a collection called networth and determine the MongoDB URI which for this project is: 

mongodb://<dbuser>:<dbpassword>@ds155203.mlab.com:55203/networth

For the web app, we will use Mongoose to model the MongoDB data. 

//--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------//
//Step 7: Wire the database back-end with React

At this point, we have a NodeJS server, a React front-end that is rendered by the server, a Mongoose model of the MongoDB data and a couple of server routes that interact with the MongoDB and perform the CRUD operation. All we need now is something to fetch or send/fetch the data to/from the server to/from the React front-end. In order to perform this function we will be using Axios, which allows us to make requests from node.js and intercept the reponse data. 

