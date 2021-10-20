---
tags: algo
---

### [IQ Test](https://www.codewars.com/kata/552c028c030765286c00007d/train/javascript)

> Bob is preparing to pass IQ test. The most frequent task in this test is `to find out which one of the given numbers differs from the others`. Bob observed that one number usually differs from the others in **evenness**. Help Bob — to check his answers, he needs a program that among the given numbers finds one that is different in evenness, and return a position of this number.
>
`!` Keep in mind that your task is to help Bob solve a `real IQ test`, which means indexes of the elements start from `1 (not 0)`
>
Examples:
>
> ```javascript
iqTest("2 4 7 8 10") => 3 // Third number is odd, while the rest of the numbers are even
>
iqTest("1 2 1 1") => 2 // Second number is even, while the rest of the numbers are odd
>```

#### Pseudo Code
```js
function iqTest(numbers){
  // check if the first 2 numbers in the string are even
//   loop over the array and test the evenness of every subsequent number
//   return the position of the different number
}
```

#### My Solution Code
```js
function iqTest(numbers){
  let position = 0
  const numArr = numbers.split(" ").map(n => Number(n))
  const isEven = numArr[0] % 2 === 0 && numArr[1] % 2 === 0 ? true : false
  console.log('isEven: ', isEven)
  
  for (let i = 0; i < numArr.length; i++ ){
    if (isEven){
      if (numArr[i] % 2 !== 0) position = i
    } else {
      if (numArr[i] % 2 === 0) position = i
    }
  }
  console.log('numbers: ', numbers)
  console.log('numArr: ', numArr)
  console.log('position: ', position + 1)
  return position + 1
}
```
- this solution did not ultimately work. I eventually tried to refactor to check a third number, but that made things worse. The solution below is the one I'll dopt going forward.


#### Other Solutions
```js
function iqTest(numbers){
  numbers = numbers.split(" ").map(function(el){return parseInt(el)});
  
  var odd = numbers.filter(function(el){ return el % 2 === 1});
  var even = numbers.filter(function(el){ return el % 2 === 0});
  
  return odd.length < even.length ? (numbers.indexOf(odd[0]) + 1) : (numbers.indexOf(even[0]) + 1);
}
```
- really smart. I wish I had thought to do this one this way.

#### Helpful Info