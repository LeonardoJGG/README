# WEEK6

<details>
<summary>Monday</summary>
  
Intro:

We are starting a small community of users. For performance
reasons we have decided to store all users right in the code.
This way we can provide our developers with more
user-interaction opportunities. With user-related data, at least.
All the GDPR-related issues will be solved some other day.
This would be the base for our future experiments during
these exercises.

***Exercise:***

Given the data, define the interface "User" and use it accordingly.
  
```typescript
  export type User = unknown;

export const users: unknown[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    }
];

export function logPerson(user: unknown) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```

***Possible solution***

```typescript
export interface User {
    name: string;
    age: number;
    occupation: string;
};

export const users: User[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    }
];

export function logPerson(user: User) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```
  
**2. TypeScript Unions exercise**

Intro:

All 2 users liked the idea of the community. We should go
forward and introduce some order. We are in Germany after all.
Let's add a couple of admins.

Initially we only had users in the in-memory database. After
introducing Admins, we need to fix the types so that
everything works well together.

***Exercise:***

Type "Person" is missing, please define it and use
it in persons array and logPerson function in order to fix
all the TS errors.

```typescript
interface User {
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    name: string;
    age: number;
    role: string;
}

export type Person = unknown;

export const persons: User[] /* <- Person[] */ = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(user: User) {
    console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);
```

***Possible solution***

```typescript
interface User {
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    name: string;
    age: number;
    role: string;
}

export type Person = User | Admin;

export const persons: Person[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(user: Person) {
    console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);
```

</details>

<details>
  
<summary>Tuesday</summary>
  
**1. Square(n) Sum**

For example, for [1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9.

```typescript
export function squareSum(numbers: number[]): number {
    let x:number = numbers.reduce(
    (previousValue: number, currentValue: number) => previousValue + Math.pow(currentValue, 2),0
    );
    return x;
}
```
  
**2. A Wolf In Sheep's Clothing**
  
Wolves have been reintroduced to Great Britain. You are a sheep farmer, and are now plagued by wolves which pretend to be sheep. Fortunately, you are good at spotting them.

Warn the sheep in front of the wolf that it is about to be eaten. Remember that you are standing at the front of the queue which is at the end of the array:

| sheep | sheep | sheep | sheep | sheep | wolf | sheep | sheep |
|:-----:|:-----:|:-----:|:-----:|:-----:|:----:|:-----:|:-----:|    
|   7   |   6   |   5   |   4   |   3   |      |   2   |   1   |  
  
  
If the wolf is the closest animal to you, return "Pls go away and stop eating my sheep". Otherwise, return "Oi! Sheep number N! You are about to be eaten by a wolf!" where N is the sheep's position in the queue.
  
```typescript
export function warnTheSheep(queue: string[]): string {
  let wolf: number = queue.indexOf('wolf');
  
  if(wolf == queue.length -1) 
    return "Pls go away and stop eating my sheep";
  return `Oi! Sheep number ${Math.abs(
    wolf + 1 - queue.length
  )}! You are about to be eaten by a wolf!`
}
```
</details>

<details>

<summary>Wednesday</summary>
  
**1. A Rule Of Divisibility By 13**

Call thirt the function which processes this sequence of operations on an integer n (>=0). thirt will return the stationary number.

thirt(1234567) calculates 178, then 87, then 87 and returns 87.

thirt(321) calculates 48, 48 and returns 48

```typescript
const rem = [1, 10, 9, 12, 3, 4];

export function thirt(n: number): number {
  let reverse: string[] = n.toString().split('').reverse();
  let index = 0;
  let result = reverse.reduce((total: number, digit: string) => {
    if (index > 5) index = 0;
    return total + Number(digit) * rem[index++];
  }, 0);
  if (result === n) return result;
  return thirt(result);
}
``` 


**2. Playing With Digits**

Some numbers have funny properties. For example:

89 --> 8¹ + 9² = 89 * 1

695 --> 6² + 9³ + 5⁴= 1390 = 695 * 2

46288 --> 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 * 51

Given a positive integer n written as abcd... (a, b, c, d... being digits) and a positive integer p

we want to find a positive integer k, if it exists, such that the sum of the digits of n taken to the successive powers of p is equal to k * n.
In other words:

Is there an integer k such as : (a ^ p + b ^ (p+1) + c ^(p+2) + d ^ (p+3) + ...) = n * k

If it is the case we will return k, if not return -1.

```typescript
export class G964 {
  public static digPow = (n: number, p: number) => {
    const sum = n
      .toString()
      .split('')
      .map(Number)
      .reduce((prev: number, curr: number) => prev + Math.pow(curr, p++), 0);
    if (sum % n === 0) return sum / n;
    return -1;
  };
}
```
</details>

  
  
  
  
  
  
<details>
  
<summary>Thursday</summary>
  
**1. Tile exercise using** *Typescript*

In the board game Scrabble2, each tile contains a letter, which is used to spell words, and a score, which is used to determine the value of words.

1. Write a definition for a class named Tile that represents Scrabble tiles. The instance variables should be a string named letter and an number named value.
2. Write a constructor that takes parameters named letter and value and initializes the instance variables.
3. Write a method named printTile that prints the instance variables in a reader-friendly format (not the { ... } format way).
4. Don't worry you don't have to check if the letter is no more than one String length.
5. You can use this Main class to test your code.


```typescript
import Tile from './Tile';
export default class Main {
  start() {
    const A = new Tile('A', 10);
    A.printTile(); // Example of a reader-friendly format above
    /*
      ==================
        Letter: A
        Value: 10
      ==================
    */
    const W = new Tile('W', '50'); // This should show and error
  }
}
```
6. On your index.ts you can now use this to test your solution
  
```typescript
import Main from './Main';
const main = new Main();
main.start();
```

***Solution***

```typescript
export default class Tile{
    letter: string;
    value: number;

    constructor(letter: string, value:number){
        this.letter = letter;
        this.value = value;
    }


    printTile() {
        console.log(`
            ==========================  ========================= 
              Letter: ${this.letter}  ||  Value: ${this.value}   
            ==========================  =========================
        `)
}

}
```

**2. Time exercise using** *Typescript*

You have been hired by a brand of digital watches to be able to create the functionality of keeping track of time, for this you have been asked to do the following:

1. Write a definition for the class name Time this class would be use to build a digital clock. This class should have 3 attributes of type number. hour, minute and second.
2. Write a constructor that takes parameters named hour, minute and second and initializes the instance variables.
3. Write a method called getInSeconds that returns a number representing the actual time in the instance represented in seconds.
4. Write a method named printTime that prints the instance variables in a reader-friendly format (not the { ... } format way).

```typescript
import Time from './Time';
export default class Main {
  start() {
    const t = new Time(10, 45, 1);
    t.printTime(); // Example of a reader-friendly format above
    /*
      ==================
        Hours: 10
        Minutes: 45
        Seconds: 1
      ==================
    */
    console.log(t.getInSeconds()); // 38701
  }
}
``` 

5. On your index.ts you can now use this to test your solution

```typescript
import Main from './Main';
const main = new Main();
main.start();
```
  
***Solution***
 
```typescript
export default class Time {
  hour: number;
  minute: number;
  second: number;

  constructor(hour: number, minute: number, second:number){
    this.hour = hour;
    this.minute = minute;
    this.second = second;
  }

  getInSeconds(){
    const hourToSecond: number =  (this.hour * 60) * 60;
    const minuteToSecond: number = this.minute * 60;
    const totalSeconds: number = hourToSecond + minuteToSecond + this.second;

    return totalSeconds;
  }

  printTime(){
    console.log(`
    ===============
      Hours:   ${this.hour}
      Minutes: ${this.minute}
      Seconds: ${this.second}
    ================
    `)
  }
}
```
  
**3. Rational exercise, using** *Typescript*
  
A rational number is a number that can be represented as the ratio of two integers. For example, 2/3 is a rational number, and you can think of 7 as a rational number with an implicit 1 in the denominator (7/1). For this assignment, you are going to write a class definition for rational numbers.

1. Create a new class named Rational. A Rational object should have two number instance variables to store the numerator and denominator.
2. Write a constructor for your class that takes two arguments and that uses them to initalize the instance variables.
3. Write a method called printRational that prints the object in some reasonable format.
4. Write a method called invert that inverts the number by swapping the numerator and denominator. This method should modify the instance variables.
5. Write a method called toFloat that converts the rational number to a floating-point number and returns the result. This method is a pure function it does not modify the object.
6. Write method named reduce that reduces a rational number to its lowest terms by finding the greatest common divisor (GCD) of the numerator and denominator and dividing through. This method should modify the instance variables. To calculate the GCD you can search for Euclidian Algorithm: GCD.

```typescript
import Rational from './Rational';
export default class Main {
  start() {
    const r1 = new Rational(36, 120);
    r1.printRational(); // 36 / 120
    console.log(r1.toFloat()); // 0.3
    r1.reduce();
    r1.printRational(); // 3 / 10
    r1.invert();
    r1.printRational(); // 10 / 3
    r1.reduce();
    r1.printRational(); // 10 / 3
  }
}
```

7. On your index.ts you can now use this to test your solution

```typescript
import Main from './Main';
const main = new Main();
main.start();
```

***Solution***

```typescript
export default class Rational {
  numerator: number;
  denominator: number;

  constructor(numerator: number, denominator: number) {
    this.numerator = numerator;
    this.denominator = denominator;
  }

  printRational() {
    console.log(`${this.numerator} / ${this.denominator}`);
  }

  invert() {
    [this.numerator, this.denominator] = [this.denominator, this.numerator];
  }

  toFloat(): number {
    return this.numerator / this.denominator;
  }

  gcd(n: number, d: number): number {
    if (d == 0) return n;
    return this.gcd(d, n % d);
  }

  reduce() {
    const gcd = this.gcd(this.numerator, this.denominator);
    this.numerator = this.numerator / gcd;
    this.denominator = this.denominator / gcd;
  }
}
```

</details>
