# WEEK2

<details>
  
<summary> Monday </summary>
  
**1. Who Likes It? exercise**
  
For this exercise we must implement a function that takes an array where the names of our users are stored and returns on the screen the names that interact in each line.

```javascript
function likes(names) {
  if(names.length == 0) 
  return 'no one likes this';
  
  if(names.length == 1)
  return names[0] + ' likes this';
  
  if(names.length == 2)
  return names[0] + ' and ' + names[1] + ' like this';
  
  if(names.length == 3)
  return names[0] + ', ' + names[1] + ' and ' + names[2] + ' like this'; 
  
  if(names.length > 3)
  return names[0] + ', ' + names[1] + ' and ' + (names.length - 2) + ' others like this';
}
```
  
</details>




<details>
  
<summary> Tuesday </summary>
  
**2. Bit Counting exercise**
  
Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.


```javascript
  var countBits = function(n) {
  let bit = 0;
  let binary = n.toString(2);
  
  for(let i = 0; i < binary; i++){
    if (binary[i] === '1') bit++
  }
  return bit
};
```
</details>




<details>
  
<summary> Wednesday </summary>
  
</details>




<details>
  
<summary> Thursday </summary>
  
</details>
