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

In this exercise we are given a text string that we would have to return as an int and be able to handle ASCII characters.

The proposed solution is the following:

```javascript
function uniTotal(texto) {
  let longitud = texto.length
  let resultado = 0;
  
  for (let i = 0; i < longitud; i++) {
    resultado = resultado + texto.charCodeAt(i);
  }
  return resultado;
}
```

</details>



<details>
 
<summary> Wednesday </summary>  

**1. Char From ASCII Value exercise**
For this exercise we must create a class that converts the value into a string corresponding to its ASCII value.

The proposed solution is the following:

```javascript
function getChar(num){
  return String.fromCharCode(num);
}
```

**2. Binary Addition exercise**

For this exercise we must create a function that takes two values and returns the sum of the two in binary

The proposed solution is the following:

```javascript
function addBinary(a, b) {
  let result = a + b;
  return (result).toString(2);
}
```

**3. Student's Final Grade exercise**

In this exercise we must create a function to calculate the final grade of the students

This function should return a number (final grade). There are four types of final grades:

- 100, if the exam score is greater than 90 or if the number of completed projects is greater than 10.

- 90, if the exam score is greater than 75 and if the number of completed projects is at least 5.

- 75, if the exam score is greater than 50 and if the number of projects completed is at least 2.

- 0, in other cases

The proposed solution is the following:

```javascript
function finalGrade (exam, projects) {
  
  let final_result;

  if (exam > 100 || projects > 10 ){
    final_result = 100;
  } else if (exam > 75 && projects >= 5){
    final_result = 90;
  } else if (exam > 50 && projects >= 2){
    final_result = 75;
  } else {
    final_result = 0;
  }
  
  return final_result;
}
```

</details>

<details>
  
<summary> Thursday </summary>
  
**1. Remove All Exclamation Marks From The End Of Sentence exercise**

For this exercise we must create a function to remove the exclamation marks at the end of each statement

The proposed solution is the following:
  
```javascript
function remove(string) {
  let result = '';
  let lastChar = string.length - 1;
  for (let n = lastChar; n > 0; n--) {
   
    if (string[n] !== '!') {
      result = string.substring(0, n + 1); 
      break; 
    }
  }
  return result;
}
```
  
**2. Vowel Remover exercise**

For this exercise we must create a function to remove the vowels that are lowercase

The proposed solution is the following:

```javascript 
function shortcut(string) {
  let result = '';
  for (let i = 0; i < string.length; i++) {
    if (
      string[i] == 'a' ||
      string[i] == 'e' ||
      string[i] == 'i' ||
      string[i] == 'o' ||
      string[i] == 'u'
    ) {
      continue;
    }
    result = result + string[i];
  }
  return result;
}
```

**3. Rock Paper Scissors! exercise **

For this exercise we must create a function that returns us which player was the winner or if there was a tie

The proposed solution is the following:                                    

```javascript 
const rps = (p1, p2) => {
  if (p1 === p2) return 'Draw!';
  if (p1 === 'rock' && p2 === 'scissors') return 'Player 1 won!';
  if (p1 === 'scissors' && p2 === 'paper') return 'Player 1 won!';
  if (p1 === 'paper' && p2 === 'rock') return 'Player 1 won!';
  return 'Player 2 won!';
};
```

**4. Persistent Bugger exercise**

In this exercise we must create a function that takes a number value and returns its multiplicative persistence

The proposed solution is the following:  

```javascript 
function persistence(num) {
  let times = 0;
  let digits = [];
  while (num >= 10) {
    digits = num.toString().split('');
    num = 1;
    for (let i = 0; i < digits.length; i++) {
      num *= digits[i];
    }
    times++;
  }
  return times;
}
```

</details>

<details>
  
<summary> Friday </summary>
  
</details>
