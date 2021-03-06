## Node.js - Express - EJS - Bootstrap Template

This is a template application using Node.js, Express, EJS, Bootstrap and Nodemon.  Almost all of this comes from John Schimmel and the ITP Dynamic Web Development class.  I have simply added a few thing and made it my own so I can develop quickly.  

To use, follow the getting started below.  Very simple!


### Getting started w/ local development server

1) Download this template repo and navigate into the code directory with Terminal.

2) Run **npm install** to get all required libraries.

	npm install

3) A Git repository and Heroku app are required for this Example to work. 

	git init
	git add .
	git commit -am "init commit"


4) Create Heroku app and add database

	heroku create

5) Rename the app to what you want
	
	heroku apps:rename newname

6) Add MongoLabs Starter MongoDB add on to your heroku app

	heroku addons:add mongolab:starter

7) Get Heroku MongoLab connection string into .env file

	heroku config --shell | grep MONGOLAB_URI >> .env

Your connection string to MongoDB will be in your **.env** file now.

8) Start server with **foreman start**.

	foreman start

Foreman reads your .env file, populates the process.env object for use in your app.

9) Open web browser to <http://localhost:5000> to view the web app.

10) Stop the web server press Command+C in the Terminal window.

### Auto restart development server

To auto restart your development server after you make some changes to your code. Install **Nodemon**. [Nodemon](https://github.com/remy/nodemon) will watch your files and restart the server for you.

Install Nodemon. In Terminal type,

	npm install -g nodemon

There are two possible ways to use Nodemon,

	foreman run nodemon app.js

Or with the helper script

	. devserver

The **.nodemonignore** file will ignore certain files and directories from being watched. By default and for example we're ignoring /public folder.


### Frameworks and NodeJS

Libraries and frameworks are created for all programming languages to make complicated programming tasks more easier to program. A database library will create the connection to the database server, insert and query data and return a result that is easily used. A framework involves the same ideas of a library but it usually is larger in size and complexity - picking a framework is usually done at the beginning of development because it is often difficult to switch to another. Android, Arduino, OpenFrameworks, Sinatra, Ruby on Rails, Django and Processing are frameworks, each is a collection of libraries to interact with lower level code.

Libraries and frameworks are available to make your programming life easier - someone else has had similar tasks and requirements so they organized their code into a library and made it available to the community.

#### ExpressJS

ExpressJS (http://expressjs.com/guide.html) is a popular framework for building web applications in NodeJS. ExpressJS's core is taken from the Connect framework.

#### Routing

Routing is how you direct the user's requested URL to retrieve the appropriate 'page' or save the submitted form. All routes execute functions, the callbacks should receive a request and response object from Express

app.get('/page1',function(request, response){
    //your code goes here
})

#### HTTP Methods

GET- a user requests a web page or resource

	app.get('/about',function(request, response){
	    console.log("GET request for /about");
	    response.send("This is the about page.");
	});

POST- a user submits a form

	app.post("/the-form", function(request, response){
	    
	    console.log("a user has request /the-form via POST");
	    
	    //form processing code goes here....
	    
	    //send message to user
	    response.send("okay, we'll process that right away.")
	});


-----


