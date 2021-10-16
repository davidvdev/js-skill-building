---
tags: algo
---

### [Sort the Odd](https://www.codewars.com/kata/578aa45ee9fd15ff4600090d/train/javascript)

> You will be given an array of numbers. You have to sort the odd numbers in ascending order while leaving the even numbers at their original positions.

Examples
```
[7, 1]  =>  [1, 7]
[5, 8, 6, 3, 4]  =>  [3, 8, 6, 5, 4]
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]  =>  [1, 8, 3, 6, 5, 4, 7, 2, 9, 0]
```

#### Pseudo Code
```js
function sortArray(array) {
// create a new arr that is length of input array
//   create an odds arr
//   loop through input arr checking even or odd
//   if even, splice into new arr at correct position
//   if odd, add to odds array
//   exit first loop
//   loop through odds array and rearrange in ascending order
//   loop through final array and replace 0s with items from odds array
}
```
- totally brute forcing it today, but whatever

#### My Solution Code
```js
function sortArray(array) {
  const finalArr = []
  const oddsArr = []
  
  for (let i = 0; i < array.length ; i++){
    if( array[i] % 2 === 0){
      finalArr.push(array[i])
    } else {
      finalArr.push(null)
      oddsArr.push(array[i])
    }
  }
  
  oddsArr.sort((a, b) => a-b)
  for (let i = 0; i < oddsArr.length; i++){
    finalArr.splice(finalArr.findIndex(item => item === null), 1, oddsArr[i])
  }
  
  return finalArr
  
}
```

#### Other Solutions
```js
function sortArray(array) {
  const odd = array.filter((x) => x % 2).sort((a,b) => a - b);
  return array.map((x) => x % 2 ? odd.shift() : x);
}
```