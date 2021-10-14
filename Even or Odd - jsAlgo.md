---
tags: algo
---
### [Even or Odd](https://www.codewars.com/kata/53da3dbb4a5168369a0000fe/train/javascript)

>Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.

#### Pseudo Code
```js
function even_or_odd(number) {
//   set up a test to check that input is a number
//     if NaN, return "Please submit a number"
  
//  ternary op number % 2
//   if TRUE, return Even
//   if FALSE, return Odd
}
```

#### My Solution Code
```js
function even_or_odd(number) {
  return typeof number === "number" ? 
    (number % 2 === 0 ? "Even": "Odd") : "please submit a number"
}
```