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
```
const express = require("express");
const app = express();

app.listen(3000, function(){
  console.log("listening on port 3000")
});
```
Require express and set a port that a browser can connect to

###Get/Read
5)
```
app.get("/", (req, res) => {
  res.send("Hello World")
});
```
Define a path and callback function with request and response arguments

6)
Let's send ```index.html``` with the sendFile method

```javascript
app.get("/", (req, res) => {
  res.sendFile(__dirname + "/index.html")
  console.log(__dirname)
});
```

7)
Use nodemon to automatically restart the server when you make changes
```
npm install express --save
```
