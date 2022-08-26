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
