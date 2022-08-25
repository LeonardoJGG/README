# WEEK5
<details>
  
<summary>Tuesday</summary>
  
**1. Complete the square sum function so that it squares each number passed into it and then sums the results together.**

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
  let wolf = queue.indexOf('wolf');
  
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
</details>
