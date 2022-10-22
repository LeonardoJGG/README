# WEEK11

<details>
  <summary>Monday</summary>
  
</details>



<details>
  <summary>Tuesday</summary>
 
## Node.JS Core Understanding Learning Exercise 🧠
  
***1. What is Node.js?***

**Node JS** is an open source javascript environment that we run outside the browser targeting asynchronous events.

***2. What problem does Node.JS solve?***

Node solves the problem of having the need to use a large number of servers, because thanks to its engine, instead of creating a new thread for each client, each connection triggers an execution within the node engine, so a server can support thousands of connections

***3. What is the V8 Javascript Engine?***

The v8 engine is an engine developed in C++ that is currently most popular due to its performance and performance, which combines an interpreter that transforms the code into a list of tokens and a compiler that optimizes it, thus making javascript run much faster.

***4. Is Node.JS really necessary in the Development ecosystem?***

Node js is necessary and very useful in the development ecosystem because it allows us to develop faster and more scalable applications in a very efficient way, in addition to having a huge community and support.
  
***5. What is the difference between Node.JS and any other browser?***
  
The difference between nodejs and any other browser is that NodeJS has full access to the system, thus being able to read and write directly from the file system, with unlimited access, run software etc.

  ***6. What is NVM and Why is it useful for Node.JS developers?***
  
  NVM (node vision manager) is a bash script used to manage the released versions of NodeJS, allowing you to install, update or change the version. This makes it easier to work with projects that require different versions on the same computer.
  
  
## Node.JS Module System Core Understanding Learning Exercise 🧠
  
***1. What is a Javascript Module?***
  
  Modules are a feature that can contain classes or libraries with functions for specific tasks, which we can import into our projects.
  
  
***2. Why are Javascript Modules necessary?***
  
  Modules are important because they allow us to split our code into different files by importing and exporting them, thus allowing us to reuse them.
  
  
***3. What module standards are available in Node.JS?***
  
As standard modules NodeJs has the following modules:

- http
- url
- querystring
- path
- fs
- util
  
  
***4. What are the differences between ESModules and CommonJS modules?***
  
  The difference between ESModules and CommonJS is that CommonJS specifically allows you to load modules in a synchronous way, while ESModules allows you to load modules synchronously and asynchronously.
  
  
***5. Which types of modules exist in Node.JS?***
  
  In NodeJS there are three types of modules:
  
- Core Modules
- Local Modules
- Third Party Modules
  
  
## Node.JS Module System Practice 💻
  
### Description

Time to put into practice what you learned about Node.JS modules 😁.

1. Create a new Node.JS project, name it: <your-nickname>/modules
2. Create a new module, name it: operations.js
3. Inside operations.js implement two functions, one for the sum operation and one for the subtract operation.
4. Create a new module, name it: main.js
5. Import the functions implemented in operations.js and use them in any way in main.js.

***Solution***

**main.js**

```javascript

const {sum, subs} = require('./operations.js');

let One = 3.5;
let Two = 3.5;

let Operation1 = sum(One, Two);
let Operation2 = subs(One, Two);
let Complete_operation = sum(Operation1, Operation2);
let Complete_operation1 = subs(Operation1, Operation2);

console.log('The result is:' + Operation1);
console.log('The result is:' + Operation2);
console.log('The result is:' + Complete_operation);
console.log('The result is:' + Complete_operation1);

```

**operations.js**

```javascript

function sum(num1, num2){
    let result = num1 + num2;
    return result;
}

function subs(num1, num2){
    let result = num1 - num2;
    return result;
}

module.exports = {sum, subs}

```
  
  
## Client-Server Model Learning Exercise 🧠
  
***1. What is a Server?***
  
A server is a set of computers that can receive requests from users and return a response.

 
***2. Why is a Client?***
  
The client is the one who interacts with the server and sends requests and receives responses from it.

  
***3. Is a server just another physical computer?***
  
  A server is a physical computer integrated into a network in which it communicates with other computers also connected to the network.

 
***4. Is there any similarity between human communication and the client-server model?***
  
  In general, the intention of both options is to make a request and receive a response, but in my opinion the difference between the two is that in human communication, people communicate directly with a single person to receive some type of information, while in client-server model, many clients are communicating at the same time with a single server which returns a specific response to each request from each client

  
***5. Is the client-server model applicable only to the Web?***

According to me, currently I think it is only applicable for the web, since it is necessary to establish a connection between clients and the server, and for that the network is necessary, which is within the web

  
</details>




<details>
  <summary>Wednesday</summary>
  
## APIs Core Understanding Learning Exercise 🧠

***1. What is an API?***

An API (Application Programming Interfaces) is a set of protocols and definitions used to develop and integrate software, allowing communication between two applications through certain rules.

***2. What is a Protocol?***

Protocols are a set of rules, standards and policies made up of restrictions that define the exchange of information between devices or servers through the network.

***3. Is the term API only applicable to the communication of programs over the Internet?***

Yes, it is only applicable on the internet, since for an api to work it must have a connection with another application through some network

***4. Why is structured communication between two programs important?***
  
Structured communication is important so that each program can work objectively, respecting the operation of the application with which it is making a connection, which only happens in applications since in communication between humans there are no protocols that create restrictions between the communication of two people.


***5. Is an API just another program or a standard? ***
  
It is a program that creates a connection between applications

***6. Do you know any API? Can you list at least 5 examples of APIs?***

1. Axios
  
2. Google Cloud API
  
3. Twitter API
  
4. API OpenWeatherMap
  
5. All Sports API
  


## From JSON to REST Learning Exercise 🧠
  
***1. What is HTTP?***

The http protocol (hipetext transfer protocol) is the protocol that allows the transfer of information through files on the world wide web

***2. What is JSON?***

The JSON format is a data exchange format based on literal notation subsets of JavaScript objects.

***3. What is REST?***

REST is a **software architecture** style for distributed hypermedia systems such as the world wide web.

***4. What is a Resource in REST?***

A resource is anything important enough to be referenced by itself, a resource can be stored in a computer represented as a sequence of bits.

Following this is the resource identifier, or uniform resource identifier (URL) is a string of characters that uniquely identifies the resources or address of a network.


***5. What is an HTTP method?***

HTTP methods provide the operations available on Rule Execution Server artifacts, such as create, read, update, and delete.

  **What HTTP methods does REST use within its architecture rules?**
  
Uniform interface: descriptive messages

Use the features of the http protocol to improve semantics:

* HTTP Verbs

* HTTP Status Codes

* HTTP Authentication

Seek a simple and hierarchical API with certain rules: Use of plural names


***6. Is REST the same as HTTP?***

REST and HTTP are not the same as http is the hypertext transfer protocol for transferring files on the web and REST connects systems based on this http protocol


## REST API Clients Learning Exercise 🧠

***1. Postman only works with REST APIs?***

Postman is dedicated to working with web APIs, which conform to the REST architecture that allows interaction with RESTful web services.

***2. Is there an alternative to Postman?***

Yes, there are alternatives to postman, among them Zapier, SoapUI among others


## Express.JS Core Understanding Learning Exercise 🧠
  
***Create "Hello world!" with express***
  
* Step #1
  
  ```javascript
    npm init
  ```

* Step #2
  
  ```javascript
    npm install express --save 
  ```

* Step #3 (Coding)
  
  ```javascript
    const express = require ('express');
    const app = express();
    const port = 3000;

    app.get('/', (req, res) => {
        res.send('Hello World!');
    })

    app.listen(port, () => {
        console.log(`Hello world app is running on port ${port}`)
    })
  ```

**check the output of our program at** *http://localhost:3000/*


</details>




<details>
  <summary>Thursday</summary>

## Forrest Gump Ping-Pong API 🏓:

### Step #1

```javascript
  npm init
```

### Step #2

```javascript
  npm install express --save
```
### Step #3

```javascript
  npm install cors
```

### Step #4 (coding)

```javascript
  const express = require('express');
  const cors = require('cors');
  const game = express();
  const port = 3000;

  game.use(cors())

  game.get('/api/buba-gump', (req, res) => {
      res.send({message: 'This is my API REST for ping-pong with Express'})
  })

  game.post('/api/buba-gump/ping', (req, res) => {
      res.send({data: 'pong'})
  })

  game.post('/api/buba-gump/pong', (req, res) => {
      res.send({data: 'ping'})
  })

  game.listen(port, () => {
      console.log(`Running on port ${port}`)
  })
```

### RUN
  
```javascript
  node index.js
```

## Delayed Response API ⏳:

</details
