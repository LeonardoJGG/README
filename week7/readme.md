# WEEK7

<details>
  <summary>Monday</summary>

**OOP glossary**

**1. Abstraction**


**2. Inheritance**


**3. Polymorphism**


**4. Encapsulation**


**5. Class**


**6. Object**


**7. Instance**


**8. Interface**


**9. Access Modifiers**


**10. Constructors**


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
