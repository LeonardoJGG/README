# WEEK8

<details>
  <summary>Monday</summary>
  
</details>




<details>
  <summary>Tuesday</summary>
  
</details>




<details>
  <summary>Wednesday</summary>
  
**1. Make the Deadfish Swim exercise, using** *Typescript*

Write a simple parser that will parse and run Deadfish.

Deadfish has 4 commands, each 1 character long:

* "i" increments the value (initially 0)
* "d" decrements the value
* "s" squares the value
* "o" outputs the value into the return array

Invalid characters should be ignored.

```typescript
  parse("iiisdoso") => [8, 64]
```

***Solution***
  
```typescript
  export function parse(data: string): number[] {
  let result: number[] = [];
  let initially: number = 0;
  let toArr = data.split('')
  
  toArr.map(num => {
    switch(num){
        case 'i': initially++; 
        break;
        case 'd': initially--; 
        break;
        case 's': initially*= initially; 
        break;
        case 'o': result.push(initially); 
        break;
    }
  })
  
  return result;
}
```
  
**2. Duplicate Encoder exercise, using** *Typescript*
  
The goal of this exercise is to convert a string to a new string where each character in the new string is "(" 
if that character appears only once in the original string, or ")" if that character appears more than once in the original string. 
Ignore capitalization when determining if a character is a duplicate.
  
***Examples***

    "din"      =>  "((("
    "recede"   =>  "()()()"
    "Success"  =>  ")())())"
    "(( @"     =>  "))((" 

***Notes***

Assertion messages may be unclear about what they display in some languages. If you read **"...It Should encode XXX"**, the **"XXX"** is the expected result, not the input!

***Solution***

```typescript
export function duplicateEncode(word: string){
  let result: string = '';
  let lower: string = word.toLowerCase();
  
  for(let i = 0; i < lower.length; i++){
    if(lower.indexOf(lower[i]) != lower.lastIndexOf(lower[i]) ){
      result += ')';
     }else{
      result += '(';
     }
    
  }
  return result;
}
```


**3. Find The Odd Int exercise, using** *Typescript*

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

***Examples***

* [7] should return 7, because it occurs 1 time (which is odd).
* [0] should return 0, because it occurs 1 time (which is odd).
* [1,1,2] should return 2, because it occurs 1 time (which is odd).
* [0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).
* [1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).

***Solution***

```typescript
export const findOdd = (xs: number[]): number => {
  let result: number = xs.reduce((a, b) => a^b);
  return result;
};

```

**4. Which Are In? exercise, using** *Typescript*

Given two arrays of strings a1 and a2 return a sorted array r in lexicographical order of the strings of a1 which are substrings of strings of a2.

***Example 1***
    a1 = ["arp", "live", "strong"]

    a2 = ["lively", "alive", "harp", "sharp", "armstrong"]

    returns ["arp", "live", "strong"]

***Example 2:***
    a1 = ["tarp", "mice", "bull"]

    a2 = ["lively", "alive", "harp", "sharp", "armstrong"]

    returns []

***Notes:***
  
* Arrays are written in "general" notation. See "Your Test Cases" for examples in your language.
* In Shell bash a1 and a2 are strings. The return is a string where words are separated by commas.
* Beware: r must be without duplicates.

***Solution***

```typescript
export function inArray(a1: string[], a2: string[]): string[] {

  return a1.filter((item)=> a2.join(' ')
                              .includes(item))
                              .sort()
}
```

</details>




<details>
  <summary>Thursday</summary>

We have just learn about generics, an we where creating our own implementation for the Linkedlist structure, but it is incomplete, you task is to finish the missing methods.

* **addFirst:** Adds a new node at the start of the structure.
* **removeLast:** Removes the last node of the structure.

***Example***

```typescript
  let list = new LinkedList<number>();
  list.add(1); // [1]
  list.add(2); // [1,2]
  list.add(3); // [1,2,3]
  list.add(4); // [1,2,3,4]
  list.addFirst(5); // [5,1,2,3,4]
  console.log(list.toString()); // [5,1,2,3,4]
  console.log(list.size); // 5
  list.remove(); // [1,2,3,4]
  console.log(list.toString()); // [1,2,3,4]
  console.log(list.size); // 4
  list.removeLast(); // [1,2,3]
  console.log(list.toString()); // [1,2,3]
  console.log(list.size); // 3
```

***Solution***

```typescript
  public addFirst(value: T) {
    if (this.head === null) {
      this.add(value);
    } else {
      let node = new Node(value);
      node.next = this.head;
      this.head = node;
      this.length++;
    }
  }

  public removeLast(): void {
    if (this.head !== null) {
      let node = this.head;
      let previous: Node<T> = node;
      while (node.next !== null) {
        previous = node;
        node = node.next;
      }
      previous.next = null;
      this.length--;
    }
  }
```
  
</details>
