# WEEK7

<details>
  <summary>Monday</summary>

**OOP glossary**

**1. Abstraction**

Abstraction is the concept of programming in which it should not be necessary to know the internal workings of an object in order to make an application of it, and that we can modify the implementation.

As an example we can create an object for automobiles, to which we assign properties that are shown as: 

    Make, model, year and color

Without the need to have knowledge about other properties such as its
  
    weight, max_speed or horsepower

***Example***

```typescript
class Car {
  make: string;
  model: string;
  year: number;
  color: string;
  weight: number;
  max_speed: number;
  horsepower: number;

  constructor(make: string, model: string, year: number, color: string, weight: number, max_speed: number, horsepower: number){
    this.make = make;
    this.model = model;
    this.year = year;
    this.color = color;
    this.weight = weight;
    this.max_speed = max_speed;
    this.horsepower = horsepower;
  }

  features(){
    return `${this.make}, ${this.model}, ${this.year}`
  }

}

const myCar = new Car('Ford', 'GT', 2022, 'Grey', 1460, 350, 669);
console.log(myCar.features());
```


**2. Access Modifiers**

The access modifiers at the time of developing an object, allow us to determine who can or cannot access certain characteristics of our object.

These are:

* **default (when we don't assign any access modifier)**  
When we do not determine any modifier, the default access level remains, which allows access from all classes within the same package.
  
* **public**  
The public modifier indicates that it can be accessed from any class regardless of whether it is inside its package or not.
  
* **private**  
The protected modifier specifies that it can only be accessed by methods of classes that are within their own package or independent subclasses of the package to which they belong.
  
* **protected***  
The private modifier, indicates that it can only be accessed from elements that are in its own class

***Example***

```typescript
class Employee {
    public name: string;
    public lastName: string;
    protected age: number;
    protected class: string;
    private salary: number;
}
```


**3. Class**

In programming, a class is a template with certain properties or specific characteristics, which can be used infinitely to create different objects by inheriting the properties of said template.

***Example***

```typescript
class TemplateCar{
    make: string;
    model: string;
    year: number;
    color: string;
    weight: number;
    max_speed: number;
    horsepower: number;
}
```


**4. Constructors**
  
A constructor is a subroutine or a series of instructions that is responsible for initializing an object by assigning initial values.

***Example***

```typescript
class ConstructorCar {
    make: string;
    model: string;
    year: number;
    color: string;
    weight: number;
    max_speed: number;
    horsepower: number;
  
    constructor(make: string, model: string, year: number, color: string, weight: number, max_speed: number, horsepower: number){
      this.make = make;
      this.model = model;
      this.year = year;
      this.color = color;
      this.weight = weight;
      this.max_speed = max_speed;
      this.horsepower = horsepower;
    }
}
```


**5. Encapsulation**
  
Encapsulation is to hide information of an object that does not contribute to its main characteristics, accompanying the abstraction, since for the abstraction to work correctly, its implementation must be encapsulated
  
***Example No. 1***

    We need anyone to be able to access the color of a car, how should I declare the color of the car?
  
```typescript
class color{
    public color: string;
}
```

***Example No. 2***
  
    We need that the color can also be accessed from other types of vehicles, how should I declare the color of the car?

```typescript
class color{
    protected color: string;
}
```

***Example No. 3***

    We need the color to be accessible only for the car, how should I declare the color of the car?

```typescript
class color{
    private color: string;
}
```

With these examples we were able to understand a little better how the encapsulation of an object works


**6. Inheritance**

Inheritance in programming is to transmit the code of the parent class to the child class, and in this way reuse the code without the need to override the properties for each class.

That means that all the properties of the parent class will be included within its children automatically, in addition to being able to assign exclusive properties for each child class if you wish.

***Example***

```typescript
class Dad{
  name: string;
  lastname: string;
  age: number;
  gender: string;

  constructor(name: string, lastname: string, age: number, gender: string){
    this.name = name;
    this.lastname = lastname;
    this.age = age;
    this.gender = gender;
  }
}

class Son extends Dad{
  height: number;
  weight: number;

  constructor(name: string, lastname: string, age: number, gender: string, height: number, weight: number){
  super(name, lastname, age, gender);
  this.height = height;
  this.weight = weight;

  }
}
```


**7. Instance**
  
An instance is any object that is derived from another, so all objects are instances, except the Object class, since it is the parent class of all

***Example***

```typescript
class Person{
  name: string;
  lastname: string;
  age: number;
  gender: string;

  constructor(name: string, lastname: string, age: number, gender: string){
    this.name = name;
    this.lastname = lastname;
    this.age = age;
    this.gender = gender;
  }

  print(){
  return `Hello ${this.name} ${this.lastname}!`
}
}

const person1: Person = new Person('Leonardo', 'Guevara', 19, 'male'); //Instance
const person2: Person = new Person('Elon', 'Musk', 51, 'male'); //Instance
const person3: Person = new Person('Bill', 'Gates', 66, 'male'); //Instance
```

**8. Interface**

Interfaces in object-oriented programming work as a kind of contract, where you specify which methods a class must necessarily implement so that it can be executed.

All methods within an interface must be public.

***Example***

It gives us an error because we are not fulfilling the contract of the properties that our interface is demanding

```typescript
interface Person {
  name: string;
  age: number;
  gender: string;
}

const person: Person[] = [
  {
    name: 'Leonardo Guevara',
    age: 19,
    gender: 'male'
  },
  {
    name: 'Elon Musk',
    age: 51,
    gender: 'male'
  },
  {
    name: 'Bill Gates',
    age: 66   
                          //ERROR ERROR ERROR ERROR ERROR ERROR ERROR ERROR

  }
  ]
```
  
Here it is fine because we are respecting the contract

  
```typescript
interface Person {
  name: string;
  age: number;
  gender: string;
}

const person: Person[] = [
  {
    name: 'Leonardo Guevara',
    age: 19,
    gender: 'male'
  },
  {
    name: 'Elon Musk',
    age: 51,
    gender: 'male'
  },
  {
    name: 'Bill Gates',
    age: 66,  
    gender: 'male',        //That's ok
  }
  ]
```



**9. Object**

An object in programming is a block that contains data stored within itself, which are known as *attributes* and *methods*, intended to fulfill a specific task or behavior.

***Example***

```typescript
class ObjectCar{
  make: string;
  model: string;
  year: number;                // ------------ ATRIBUTES ------------
  color: string;
  max_speed: number;

  
  start(){

  }

  speedUp(){                    
                              // ------------ METHODS ------------
  }

  curb(){

  }

}
```


**10. Polymorphism**
  
Polymorphism in programming means that any object could have different shapes or different behavior using the same methods just with different parameters.

***Example***

```typescript
function person(height: number, weight: number){
  return {
    description(){
      console.log(`Person height is ${height} and weight is ${weight}`)
    }
  }
} 

function wall(height: number, width: number, thickness: number){
  return {
    description(){
      console.log(`Wall height is ${height}, width is ${width} and thickness is ${thickness}`)
    }
  }
} 

function mirror(height: number, width: number, price: number){
  return {
    description(){
      console.log(`Mirror height is ${height}, width is ${width} and price id ${price}`)
    }
  }
} 

function printDescription(obj: any){
  if (typeof obj.description === 'function'){     // --------- COMMON METHOD ---------
    obj.description();
  }
}

const person1 = person(175, 60);
const wall1 = wall(200, 150, 50);
const mirror1 = mirror(145, 50, 70);

printDescription(person1)
printDescription(wall1)                   // --------- POLIMORPHISM ---------
printDescription(mirror1)
```

</details>







<details>
  <summary>Tuesday</summary>

</details>







<details>
  <summary>Wednesday</summary>

**1. Build Tower exercise, using** *Typescript*

Build a pyramid-shaped tower given a positive integer number of floors. A tower block is represented with "*" character.

For example, a tower with 3 floors looks like this:

    [
      "  *  ",
      " *** ", 
      "*****"
    ]

And a tower with 6 floors looks like this:

    [
      "     *     ", 
      "    ***    ", 
      "   *****   ", 
      "  *******  ", 
      " ********* ", 
      "***********"
    ]

***Solution***

```typescript
export const towerBuilder = (nFloors: number): string[] => {
  let output: string[] = [];
  for(let i: number = 1; i <= nFloors; i++) {
    output.push(" ".repeat(nFloors - i) 
                + "*".repeat(i * 2 - 1) 
                + " ".repeat(nFloors - i));
  }
  return output;
}
```

**2. Meeting exercise, using** *typescript*

John has invited some friends. His list is:

    s = "Fred:Corwill;Wilfred:Corwill;Barney:Tornbull;Betty:Tornbull;Bjon:Tornbull;Raphael:Corwill;Alfred:Corwill";

Could you make a program that

* Mkes this string uppercase
* Gves it sorted in alphabetical order by last name.

When the last names are the same, sort them by first name. Last name and first name of a guest come in the result between parentheses separated by a comma.

So the result of function *meeting(s)* will be:

    "(CORWILL, ALFRED)(CORWILL, FRED)(CORWILL, RAPHAEL)(CORWILL, WILFRED)(TORNBULL, BARNEY)(TORNBULL, BETTY)(TORNBULL, BJON)"

It can happen that in two distinct families with the same family name two people have the same first name too.

***Solution***

```typescript
  export function meeting(s: string): string {

  let order_list: string = s.toUpperCase()
                  .split(';')
                  .map(n => '(' + n.split(':').reverse().join(', ') +')')
                  .sort() 
                  .join('');

  return order_list
}

```

</details>







<details>
  <summary>Thursday</summary>

</details>
