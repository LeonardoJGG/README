# WEEK3

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

In this kata you have to write a method that folds a given array of integers by the middle x-times.

The solution could be the following:

```javascript
function foldArray(array, runs) {
  if (array.length === 1) return array;
  let output = [...array];
  let aheadPosition = 0;
  while (runs) {
    if (output.length === 1) return output;
    output = Array.from(
      { length: Math.round(output.length / 2) },
      (v) => 0
    ).map((v, i) => {
      aheadPosition = output.length - (i + 1);
      if (aheadPosition === i) return output[i];
      return output[i] + output[aheadPosition];
    });
    runs--;
  }
  return output;
}
```

**2. Encrypt This! exercise**

In this case we must create a function to encrypt messages by converting the first letter of the string into ascii code and exchanging the second for the last

The solution could be the following:

```javascript
function encryptedWord(word) {
  if (word.length == 1) return word.charCodeAt();
  if (word.length == 2) return `${word.charCodeAt(0)}${word[1]}`;
  return `${word.charCodeAt(0)}${word[word.length - 1]}${word.slice(
    2,
    word.length - 1
  )}${word[1]}`;
}

var encryptThis = function (text) {
  return text.split(' ').map(encryptedWord).join(' ');
};
```

**3. Core Challenge**

***Let’s write our Mission Statement!*** In ***one paragraph***, please answer to the next 5 questions:

**1. Who are you?**

**2. What background do you have?**

**3. Who do you want to be?**

**4. What do you want to do?**

**5. What are the core values and principles that govern your character and contributions?**

I'm Leonardo, future software developer. I have followed the world of development for 9 years and I was in a company as a python developer. I want to build a solid career as a ***developer*** and ***entrepreneur.*** I am a very ***constant*** person who does not stop until I meet my goals, ***curious*** and ***eager to grow***.

</details>
