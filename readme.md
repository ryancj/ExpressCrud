#Node Express Crud

1)
```
npm init
```
This creates ```package.json``` that helps to manage dependencies

2)
Now we must create a server file- ```touch server.js```

3)
Install express- ```npm install express --save```

4)
```js
const express = require("express");
const app = express();

app.listen(3000, function(){
  console.log("listening on port 3000")
});
```
Require express and set a port that a browser can connect to

###Get/Read
5)
```js
app.get("/", (req, res) => {
  res.send("Hello World")
});
```
Define a path and callback function with request and response arguments

6)
Let's send ```index.html``` with the sendFile method

```js
app.get("/", (req, res) => {
  res.sendFile(__dirname + "/index.html")
  console.log(__dirname)
});
```

7)
Use nodemon to automatically restart the server when you make changes
(-dev is used because we only need it in the Development environment)
```
npm install nodemon --save-dev
```

###Post/Create

8)
Provide where you want to navigate and the type of method
```html
<form action="/quotes" method="POST">
  <input type="text" placeholder="name" name="name">
  <input type="text" placeholder="quote" name="quote">
  <button type="submit">Submit</button>
</form>
```
(In the ```index.html```)

```js
app.post("/quotes", (req, res) => {
  console.log("HELLLOOO");
});
```
(In the server file)

9)
To get the input values we need another package: body-parser
```
npm install body-parser --save
```

Include this in your server file
```js
const express = require("express");
const bodyParser = require("body-parser");
const app = express();

app.use(bodyParser.urlencoded({extended: true}));
```

10)
Store your data with a database: MongoDb ```npm install mongodb --save```
