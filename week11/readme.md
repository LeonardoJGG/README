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

</details>




<details>
  <summary>Thursday</summary>

</details
