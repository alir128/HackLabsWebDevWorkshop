# HackLabsWebDevWorkshop
Web development workshop files for UTM Hacklabs

### Running the application for the first time:
Download or clone this repo on to a new directory.
Remember to install NodeJS and npm before trying to run.

refer to: https://nodejs.org/en/

Once completed head over to a new directory and run the following lines of code:

```bash
npm install
node app.js
```

These lines of code install all the packages required to run the application and then start the node server on your local machine.

### Making the application from scratch:
Again make sure to have NodeJS and npm installed on your machine. Once completed:
```bash
npm install express --save
node app.js
```
1. Install the Express framework NPM so that it can be used to create a web application.
The above command saves the installation locally in the node_modules directory and creates a directory express inside node_modules.
2. Install the following frameworks along with express to make life easier:
```bash
npm install multer --save
npm install body-parser --save
npm install cookie-parser --save
```
3. Next, Create an app.js file that will contain boilerplate code to make a server run. For those of you in CSC207, think of this as your Controller file.
4. Now in the app directory create a folder and call it "Views". This will contain all the html templates. Along with views create another folder called "public". This will contain files that will be sent over to the client each time the pages are loaded.
5.

Hope you enjoyed the workshop! Make sure to experiment further with Web applications....
