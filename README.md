# HackLabsWebDevWorkshop
Web development workshop files for UTM Hacklabs

### Running the application for the first time:
Download or clone this repo on to a new directory.
Remember to install NodeJS and npm before trying to run.

refer to: https://nodejs.org/en/

Once completed head over to a new directory and run the following lines of code on console or terminal:

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
npm install express --save
npm install body-parser --save
npm install ejs --save
```
3. Next, Create an app.js file that will contain boilerplate code to make a server run. For those of you in CSC207, think of this as your Controller file.
4. Now in the app directory create a folder and call it "Views". This will contain all the html templates. Along with views create another folder called "public". This will contain files that will be sent over to the client each time the pages are loaded.
5. Now lets head back to the app.js file, inside paste the following lines of code:
```javascript
var express = require('express');
var app = express();

app.get('/', function (req, res) {
   res.send('Hello World');
})

var server = app.listen(8080, function () {
   var host = server.address().address
   var port = server.address().port

   console.log("Example app listening at http://%s:%s", host, port)
})
```
So here we made our basic web server, and a get request call that sends back the message "Hello World" to the clients web browser. Run this on terminal or console to start your server locally.
```bash
node app.js
```
6. Now to dive a bit deeper.
```javascript
var express = require('express');
var app = express();
app.use(express.static(__dirname + '/views'));
app.set('view engine', 'ejs');
app.use(express.static('public'));
var bodyParser = require("body-parser");
app.use(bodyParser.urlencoded({ extended: true }));

var task =["workshop"];
app.get('/', function (req, res) {
   res.send('Hello World');
})


app.get('/todo', function (req, res) {
    res.render("todo", { task: task})
})

app.post('/add-new-todo', function(req, res){
    var newTask = req.body.newtask;
    //add the new task from the post route into the array
    task.push(newTask);
    //after adding to the array go back to the root route
    res.redirect("/todo");
})

var server = app.listen(8080, function () {
   var host = server.address().address
   var port = server.address().port

   console.log("Example app listening at http://%s:%s", host, port)
})
```


7. Also now in the views folder create a file called todo.ejs and paste the following code:

```javascript
<!DOCTYPE html>
<html lang="en" >

<head>
  <meta charset="UTF-8">
  <title>Todo App</title>
</head>

<body>
    <form action="/add-new-todo" method="post">
        <input type="text" name="newtask">
        <button type="submit">New Task</button>
    </form>
    <br>
    <ul>
    <% for( var i = 0; i < task.length; i++){ %>
        <li> <%= task[i] %> </li>
    <% } %>
    </ul>

</body>

</html>

```
Now again restart the server:
```bash
node app.js
```

Hope you enjoyed the workshop! Make sure to experiment further with Web applications....
