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

**3. Your Order, Please exercise**

In this exercise our task is to order the words in the order of the numbers they contain

The solution could be the following:

```javascript
function order(words) {
  let sortedArray = [];
  let wordsArray = words.split(' ');
  for (let i = 0; i < wordsArray.length; i++) {
    let wordNumber = getWordNumber(wordsArray[i]);
    sortedArray[wordNumber] = wordsArray[i];
  }
  return cleanUndefined(sortedArray).join(' ');
}                            

function getWordNumber(word) {
  for (let i = 0; i < word.length; i++) {
    if (!Number.isNaN(Number(word[i]))) return word[i];
  }
}

function cleanUndefined(array) {
  let result = [];
  for (let i = 0; i < array.length; i++) {
    if (array[i] != undefined) result.push(array[i]);
  }
  return result;
}
```

  
</details>




<details>
  
<summary> Tuesday </summary>

**1. Simple Pig Latin exercise**

For this exercise our task is to move the first letter of each word to the end, and add "ay" at the end of everything respecting the punctuation marks

The solution could be the following:

```javascript
function pigIt(str) {
  let pMarks = ['!', '¡', '?', '¿', '.', ',', ':', ';'];
  str = str.split(' ');
  for (let i = 0; i < str.length; i++) {
    if (pMarks.indexOf(str[i]) >= 0) continue;
    str[i] = str[i].slice(1) + str[i].slice(0, 1) + 'ay';
  }
  return str.join(' ');
}
```

**2. Counting Duplicates exercise**

Here we need to write a function that returns the count of alphabetic characters and distinct case-insensitive numeric digits that appear more than once in the input string.

The solution could be the following:

```javascript
function duplicateCount(text) {
  let textArray = text.toLowerCase().split('').sort();
  let i = 0,
    result = 0,
    lastIndexOfChar = 0;
  while (textArray.length) {
    lastIndexOfChar = textArray.lastIndexOf(textArray[i]);
    if (lastIndexOfChar !== i) {
      i = lastIndexOfChar;
      result++;
    }
    textArray = textArray.slice(++i);
    i = 0;
  }
  return result;
}
```

**3. Decode The Morse Code exercise**

Our task in this exercise is to decipher the morse code and return it in human-readable text strings.

The solution could be the following:

```javascript
decodeMorse = function (morseCode) {
  morseCode = morseCode.replace(/   /g, '#');
  let decodedCode = '';
  let tempWordToDecode = '';
  for (let i = 0, lenght = morseCode.length; i < lenght; i++) {
    if (morseCode[i] === ' ') {
      decodedCode += MORSE_CODE[tempWordToDecode] || '';
      tempWordToDecode = '';
    } else if (morseCode[i] === '#') {
      decodedCode += `${MORSE_CODE[tempWordToDecode] || ''} `;
      tempWordToDecode = '';
    } else {
      tempWordToDecode += morseCode[i];
    }
  }
  decodedCode += MORSE_CODE[tempWordToDecode] || '';
  return decodedCode.trim();
};
```
  
</details>




<details>
  
<summary> Wednesday </summary>

**1. Valid Parentheses exercise**

For this exercise we must create a function that checks if the order of the parentheses is correct and returns true or false if it is not.

The solution could be the following:

```javascript
function validParentheses(parens) {
  let valid = 0;
  for (let i = 0; i < parens.length; i++) {
    if (parens[i] === ')') valid--;
    if (parens[i] === '(') valid++;
    if (valid < 0) return false;
  }
  return valid == 0;
}
```
  
**2. Convert String To Camel Case exercise**

Here we must complete the function so that the words delimited with hyphens or underscores change the first letter of each word to uppercase

The solution could be the following:

```javascript
function toCamelCase(str) {
  let result = '';
  for (let i = 0; i < str.length; i++) {
    if (i != 0 && (str[i - 1] === '_' || str[i - 1] === '-')) {
      result += str[i].toUpperCase();
    } else if (str[i] != '-' && str[i] != '_') {
      result += str[i];
    }
  }
  return result;
}
```

**3. Unique In Order exercise**

For this exercise we must create a function that takes a given sequence and returns it as a list of elements that do not contain another element of the same value next to them.

The solution could be the following:

```javascript
function uniqueInOrder(iterable) {
  let result = [];
  let last;
  for (let i = 0; i < iterable.length; i++) {
    if (iterable[i] !== last) {
      last = iterable[i];
      result.push(last);
    }
  }
  return result;
}
```
  
</details>




<details>
  
<summary> Thursday </summary>

**1. Fold An Array exercise**


  
</details>
