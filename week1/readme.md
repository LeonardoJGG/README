# WEEK1

<details>
<summary> Tuesday </summary>  
  
***1.Interpreted And Compiled Programming Languages***

**•Compiled language**  

A compiled language is a programming language whose implementations are usually "translators" that create machine code from source code written by the developer.

**•Interpreted language**

An interpreted language is a programming language in which instructions are mostly executed directly without first being compiled into machine language.

**Personal comparison**

In short, a compiled language when translated into machine language is more efficient for the user when executed, while an interpreted language is more optimized on the developer's side and is a little less efficient when executed since it means a slightly higher load for the machine.


***2.Is Java compiled or interpreted, or both?***

Java is a language that is compiled and interpreted at the same time, since the compiler converts the code into bytecode, and then the Ja Virtual Machine ends up interpreting that code.


***3.Pseudocode Currency Converter exercise***

Pseudocode FROM_USD_TO_SOLANA

Start  
USD <--- GET  
SOLANA_PER_USD <--- 0.023  
EXCHANGE <--- USD * SOLANA_PER_USD  
PRINT <--- EXCHANGE  
End
  
</details>



<details>
<summary> Wednesday </summary>  

***1.Your date of birth in the matrix? exercise***  

I was born on May 7, **2003**  

So convert the year of birth (2003) to binary numbers:

|  2¹⁰ |  2⁹ |  2⁸ |  2⁷ | 2⁶ | 2⁵ | 2⁴ | 2³ | 2² | 2¹ | 2⁰ |
|:----:|:---:|:---:|:---:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 1024 | 512 | 256 | 128 | 64 | 32 | 16 |  8 |  4 |  2 |  1 |

2003 - 1024 = 979, this is equal to 1

979 - 512 = 467, this is worth 1

467 - 256 = 211, this is equal to 1

211 - 128 = 83, this is equal to 1

83 - 64 = 19, this is equal to 1

19 - 32 is not a possible operation, so it is 0

19 - 16 = 3, this is worth 1

3 - 8 is not a possible operation, so it is equal to 0

3 - 4 is not a possible operation, so it is 0

3 - 2 = 1, this is equal to 1

1 - 1 = 0, this is equal to 1

This process gives us as a result that my year of birth in binary numbers is: **11111010011**




***2.MIPS exercise***  

1. Create a program that adds any two given numbers provided by the user  

```assembly
   .data
	      num1: .asciiz "\nEnter your first number: "
	      num2: .asciiz "\nEnter your second number: "
	      sum: .asciiz "\nThe sum of the numbers entered is: " 
	      subs: .asciiz "\nThe remainder of the numbers entered is: "
	      multi: .asciiz "\nThe multiplication of the entered numbers is: "
	      divs: .asciiz "\nThe division of the entered numbers is: "
	      thanks: .asciiz "\nThanks for testing my code :) "
  .text
	      main:
              li $v0, 4
              la $a0, num1
              syscall

              li $v0, 5
              syscall

              move $t0, $v0

              li $v0, 4
              la $a0, num2
              syscall

              li $v0, 5
              syscall

              move $t1, $v0
              
              add $t2, $t0, $t1
              
              li $v0, 4
              la $a0, sum
              syscall
              
              li $v0, 1
              move $a0, $t2
              syscall                         
              
              sub $t3, $t0, $t1
              
              li $v0, 4
              la $a0, subs
              syscall
              
              li $v0, 1
              move $a0, $t3
              syscall
              
              mul $t4, $t0, $t1
              
              li $v0, 4
              la $a0, multi
              syscall
              
              li $v0, 1
              move $a0, $t4
              syscall
              
              div $t5, $t0, $t1
              
              li $v0, 4
              la $a0, divs
              syscall
              
              li $v0, 1
              move $a0, $t5
              syscall
              
              li $v0, 4
              la $a0, thanks
              syscall


```

2. Create a program that adds any two given numbers provided by the user  

```assembly
   .data
        message: .asciiz "\nHello, my name is Leonardo\n"
  .text
        main:
              li $v0, 4
              la $a0, message
              syscall

```

</details>



<details>
<summary> Thursday </summary>  

***1.Print special numbers exercise***  

In this exercise to print all the even numbers from 0 to 100 I have done it using the ***for***, ***while*** and ***do while*** cycle as follows:

### *for*

```javascript
let numbers = '';

for (i = 0; i <= 100; i++) {
  if (i % 2 == 0) 
  numbers = numbers + i + ' ';
}
console.log(numbers);
```  

### *while*

```javascript
let num = 0;

while (num <= 100){
  if(num % 2 == 0)
  console.log(num);
  num++; 
  
}
```  

### *do while*

```javascript
let num = 0;
do {
  if(num % 2 == 0)   
    console.log(num);
    num++
}while(num <= 100);
```

***2.Bad Code exercise***

In the following code there is an error with the conditional:  

```javascript
var cond = false;

if ((cond = true)) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```
The error in this code was inside the condition (*if ((cond = true))*) so one solution was to simply fix it by adding the remaining equals symbol (*if ((cond == true)*):

```javascript
var cond = false;

if ((cond == true)) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```

***3.Bad Code 2 exercise***  

This code had a problem, and it was that it could not fulfill the intention of the program, and it could not mount if the given number was less than 1000, a multiple of 10 or if it was different from the given number (*100*)

```javascript
var n = 100;

if (n == 100) {
  console.log('This is a special number!');
}
if (n < 1000) {
  console.log('');
} else {
  console.log('Just a regular number');
}
if (n % 10 == 0) {
  console.log('This number is multiple of 10');
}
```

So I solved it as follows:

```javascript
var n = 100;

if (n == 100) {
  console.log('This is a special number!');
} else if (n < 1000 && n % 10 == 0){
  console.log('This is almost special number!');
} else {
  console.log('Just a regular number');
}
```
</details>
