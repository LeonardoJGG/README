# WEEK2

<details>
  
<summary> Monday </summary>  
  
***Read about if...else***
  
The if...else is an instruction to establish a condition and show a result when it is met, and if it is not met, show the opposite side of that condition
 
It is declared as follows:  
  
```javascript
  if(condition){
    statement
  } else {
    statement
  }
``` 
  
Example:

```javascript
let num = 0;
let result;
  if (num < 5) {
    result = 'true';
  } else {
    result = 'false';
  }
``` 
  
***Read about for***
            
It is an instruction that creates a loop based on 3 expressions followed by a statement which is then executed in a loop until its condition is met.

It is structured as follows:

```javascript
for (expression1; condition; expression2){
  statement             
}
``` 

Example:
              
```javascript
for (let i = 0; i <= 7; i++) {
   i = i++;
   console.log(i);
}
``` 
  
***Read about while***
 
While is a loop that runs indefinitely as long as its condition is true.
  
Its structure is as follows:

```javascript
while (condition){
  statement
}
``` 
  
Example:

```javascript
let i = 0;

while (i < 77){  
  i++;   
}
console.log(i);
```
  
***Read about functions***
  
A function in an instruction set that performs some specific action based on its parameters, taking an input value and returning a final value when called to perform its action.

Its structure is the following:

```javascript
function name(parameter0, parameter1) {
  statements
}
```

Example:

```javascript
let name = "Leonardo";

function nameFunction(){
    result = console.log("Your name is " + name);
    return result;
}

nameFunction();
```

</details>



<details>
  
<summary> Tuesday </summary>  
 
**1. Multiply exercise**

In this exercise, we came across a function to multiply the value of two variables that has an error in the code. The code is the following:

```javascript
  function multiply(a, b){
  a * b
}
```
  
The previous code was missing to return the operation, so the fastest solution I found for this was the following:
  
```javascript
  function multiply(a, b){
  return a * b
}
```
  
**2. ASCII Total exercise**

</details>



<details>
 
<summary> Wednesday </summary>  
  
</details>

<details>
  
<summary> Thursday </summary>
  
</details>

<details>
  
<summary> Friday </summary>
  
</details>
