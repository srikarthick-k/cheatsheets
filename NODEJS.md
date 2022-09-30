# NODE.JS

## Web sockets

- Import express and set variable ```app``` to the function ```express()```

```js
    const express = require("express");
    const app = express();
```

- Import http package and cors to create http server and cross origin resource sharing to enable middleware respectively.

```js
    const http = require("http");
    const cors = require("cors")
```

- Enable cors

```js
    app.use(cors())
```

- import server from socket.io package

```js
    const { Server } = require("socket.io")
```

- Create a New instance of server by passing app as argument and save it in server variable

```js 
    const server = http.createServer(app)
```

- Create a object ```io``` for the class Server imported and pass two parameters.
    
    1. @params: server (srv) 
    1. @params: an object of cors set to front-end port and methods supported

```js
    const io = new Server(server, {
        cors:{
            origin: "http://{font-end url}",
            methods:["GET","POST"] 
        }
    })
```

- Call the function ```on``` in Server class using the newly created object ```io``` which has two parameters

    1. @params: ev (name of the event which when triggered executes this)
    2. @params: listener (a call back function in which further actions are specified for triggered action in the front-end)

```js
    io.on("connection", (socket)=>{
        //some further actions here
    })
```

- Example of further actions that can be specified

    Here we are trying to receive a message from a user and broadcast it to all the users available except for the one that sent it

```js
    io.on("send_message", (data)=>{
        socket.emit.broadcast(message.data)
    })
```

- Finally we can start the server by following code

```js
    server.listen(PORT || 4000, ()=>{
        console.log("Server started at: ", PORT || 4000);
    })
```

