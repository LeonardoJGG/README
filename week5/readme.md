# WEEK5
<details>
  
<summary>Tuesday</summary>
  
Complete the square sum function so that it squares each number passed into it and then sums the results together.

For example, for [1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9.

```typescript
export function squareSum(numbers: number[]): number {
    let x:number = numbers.reduce(
    (previousValue: number, currentValue: number) => previousValue + Math.pow(currentValue, 2),0
    );
    return x;
}
```
</details>
