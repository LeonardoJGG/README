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

var myCar = new Car('Ford', 'GT', 2022, 'Grey', 1460, 350, 669);
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


**5. Encapsulation**


**6. Inheritance**


**7. Instance**


**8. Interface**


**9. Object**


**10. Polymorphism**


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
