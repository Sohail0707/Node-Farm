# 1-Node-Farm

Right now I'm learning back-end web development from udemy. Through this course, I'll be learning Nodejs, Express and mongoDB database. In here I'll be writing my learning experience

## Using Module

const #MODULE_NAME = require('#ACTUAL_MODULE_NAME / LOCATION_IF_MODULE_IS_USER_DEFINED');

## Blocking Synchronous code

This code blocks the single thread untill it finish execution. this code can return a value or data, which we can store in a variable.

### Syntax-read-file

const #VARIABLE-NAME = fs.readFileSync('#FILE_LOCATION', 'utf-8');

### Syntax-write-file

fs.writeFileSync('#FILE_LOCATION', #DATA_WANT_TO_WRITE);

## Non-blocking Asynchronous code

we never store it in a variable. We use callback function to read the data in the background. (err, data)=> this is the callback function for read file. the argument 'data' can has any name. (err) => this is the callback function for write file. because it doesn't return any data. We can use the 'data' to execute a code and also check for 'err' to print an error message.

### Syntax-read-file

fs.readFile('#FILE_LOCATION', 'utf-8', (err, #DATA_NAME) =>{CODE wanna execute after file-read});

### Syntax-write-file

fs.writeFile('#FILE_LOCATION', `#DATA_WANT_TO_WRITE`, 'utf-8', (err) => { CODE wanna execute after file-write});

## Creating a Server

First we need to initialise a module called http. We will use it to creat a web server. It has two parameter 'req' and 'res'. 'res' used for send response to the browser. It can be a message or a html page. 'req' is an object with lots of data. Some of theM we will be using during this course.
Here we also need to define a port and IP address, where we want to send response. Adding a callback function is optional with it

### Syntax-web-server

const #SERVER_NAME = http.createServer((req, res) => {
res.end('#SERVER_MESSAGE');
});

#SERVER_NAME.listen(#PORT, '#IP', () => {
console.log('#A_SUITABLE_MESSAGE');
});

## Concept Of Routing

Till now what I have learnt about routing is, we do routing to create a variation of the url and send different response to different url. To implement it we need to initialise a module called 'url'. Then we use it with 'req' parameter;
We use it inside the server code.

### Syntax-Routing

const NAME_OF_THE_VARIATION = req.THE_NAME_INITIALISED_FOR_url;
The url is look like — IP:PORT/NAME_OF_THE_VARIATION (127.0.0.1:8000/Overview);

We can also secify a status code for a specific routing. For example we can specify a status code 404, if the url is invalid.
res.writeHead(404);

## HTTP HEADER

httpheader is set of information that derfines the type of content we are sending to the browser as a respnse. There are many headers. But we can also specify our own header.

### Syntax-Header

res.writeHead(#STATUS_CODE, {
'content-type': '#TYPE_OF_CONTENT',
});
