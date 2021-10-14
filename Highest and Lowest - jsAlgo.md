---
tags: algo
---
### [Highest and Lowest](https://www.codewars.com/kata/554b4ac871d6813a03000035/train/javascript)

> In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

**Example:**

```javascript
highAndLow("1 2 3 4 5");  // return "5 1"
highAndLow("1 2 -3 4 5"); // return "5 -3"
highAndLow("1 9 3 4 -5"); // return "9 -5"
```

**Notes:**

-   All numbers are valid `Int32`, no _need_ to validate them.
-   There will always be at least one number in the input string.
-   Output string must be two numbers separated by a single space, and highest number is first.

#### Pseudo Code
```js
function highAndLow(numbers){
  // transform string into array
//   init "Lowest" variable
//   init "Highest" variable
//   loop over array checking i against Lowest and Highest
//   return a string with Lowest and Highest
}
```

#### My Solution Code
```js
function highAndLow(numbers){
  let h 
  let l 
  const numbersArr = numbers.split(" ").map(Number)
  
  for (let i = 0; i < numbersArr.length ; i++){
    let current = numbersArr[i]
    if ( current < l || l === undefined){
      l = current
    } 
    if (current > h || h === undefined){
      h = current
    }
  } 
  
  return `${h} ${l}`
}
```

#### Other Solutions
```js
function highAndLow(numbers){
  numbers = numbers.split(' ');
  return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
}
```