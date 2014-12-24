Collabrify HTML5 Webapp Standards and Guidlines
==============================================

note: This document is a work in progress and you are URGED to suggest changes, if you disagree with anything contained in this document, we would love to know why and if you have a solid argument, we can fix it with your help.

Motivation
----------
There is no one way to develop HTML5 applications. While Apple, Google and Microsoft provide SDKs for their platforms to simplify development, the HTML5 scene is very fragmented. On the upside, there is wealth of high quality open source code out there that can help simplify development of HTML5 applications. The purpose of this document is to establish some standard tools and practices (similar to native SDKs) that will lead to faster development cycles and more maintainable code. 

Deviations from these guidelines are possible, but you are expected to document the reasons.

Prerequisites
-------------
Here is a list of things you will need to have basic familliarity with before this guide will make complete sense to you:

* HTML
* The DOM
* CSS
* Javascript
* Coffeescript
* SASS
* Broccoli.js
* Cordova
* React.js
* Flux
* NPM
* Bower
* Browserify
* Javascript Promises

Discussion
----------

### HTML
The application is going to a single page of HTML. The UI will not be written in HTML but this page will bring everything together.

### The DOM
This is backing data structure for almost everything visible inside a webapp.

### CSS
This lets you declare how DOM elements are styled. You may not write this directly but you will have something else that compile to it. 

### Javascript
This is the programing language drives everything. You may not write this directly but you will have something else that compile to it. 

### Coffeescript
All code should be written in this.
Reasons for choosing Coffeescript:
* Coffeescript an Object Oriented language that exposes a traditional (à la C++/Java) view of inheritance on top of Javascript Prototypical inheritance. The only language we could presume someone taking the class knows is C++  and Coffeescript brings the Object model much closer to that.

* Coffeescript gets rid of unnecessary verbosity. This is a point of contention: some people just like their curly braces because they are used to them. This is still a point in favor of Coffeescript because once they get used to Coffeescript syntax, their point disappears, but the reduced verbosity stays.
* It gets rid of some gotchas that tend to get new Javascript devs (0==”0’)

### SASS
All styles should be written in this.
Reasons for choosing SASS:
* Adds variables to CSS. Very useful sometimes.
* Syntax similar to Coffeescript, which we are also using

### Broccoli
The most advanced (non) build step that handles all the things we are using.

### Cordova
Webpage -> native app

### React.js
View framework
Reasons for choosing React:
* Forces developers to divide code into many components. This is good for maintainability and reusability.
* Eliminates the possibility of common performance mistakes.
* Used on and developed by facebook.com, instagram.com, khanacademy.org and many more

### Flux
Application Architecture
Reasons for choosing Flux:
* Built around scalable productivity (not just your productivity right now but someone else’s when they see your code for the first time). Our code is expected to change hands every semester, so it is essential we use an application architecture that is designed for this
* Pairs well with React

### NPM/Bower
Javascript Dependency management

### Browserify
Allow you to use node.js style modules in the browser. ES6 modules are not ready yet, so this is our only choice.

### Promises
The solve a common Javascript pattern called callback hell.

Directory structure
------------------
A consistence directory structure across will help newcomers predict what is where and will make sure people who work on multiple apps find a consistence environment and don’t get confused. Our apps are not expected to be not so different from one another that they justify a different directory structure

Here is the suggested directory structure
```
. (application root)
	/src
	This should contain only source files.
		/coffee 
			/models
			/views (subdirectories possible)
			dispatcher.coffee
			router.coffee
			index.coffee (entery point of the application)
		/sass
	/public
	This should contain only static file (html/static js/images/static css/etc)
		/img
		index.html
	
	/cordova (the cordova project)
	build (may contain a build)
	brocfile.js
```
Style
-----
There are exellent style guides what we should follow

https://github.com/polarmobile/coffeescript-style-guide

https://github.com/styleguide/javascript

Dependencies
-----------
All dependencies must be documented. You may use NPM and/or Bower. Bower dependencies should be considered static and must reside in /public. NPM dependencies are to be considered source.

Manually downloading and linking to dependencies is highly discouraged.

Suggesting Changes
------------------
If you identify something that needs to be changed in this document, start an issue. If you can think of a good solution, make those changes and submit a Pull Request.


