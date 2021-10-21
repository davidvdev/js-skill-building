---
tags: algo
---

### [Multiples of 3 or 5](https://www.codewars.com/kata/514b92a657cdc65150000006/train/javascript)

> If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
>
>Finish the solution so that it returns the sum of all the multiples of 3 or 5 **below** the number passed in. Additionally, if the number is negative, return 0 (for languages that do have them).
>
>**Note:** If the number is a multiple of **both** 3 and 5, only count it _once_.
>
>_**Courtesy of projecteuler.net** ([Problem 1](https://projecteuler.net/problem=1))_

#### Pseudo Code
```js
function solution(number){
//   check if num is negative ? return 0
//   init sum variable:number
//   ini values arr:number
//   start a loop where i < number
//   each iteration, check if i % 3 or 5 ? push to arr
//   return sum of values
}
```

#### My Solution Code
```js
function solution(number){
  if(number < 0) return 0
  const multiples = []
  for (let i = 0 ; i < number; i++){
    if (i % 3 === 0 && i % 5 !== 0 ||
		i % 5 === 0 && i % 3 !== 0 || 
		i % 5 === 0 && i % 3 === 0) multiples.push(i)
  }
  return multiples.length > 0 ? multiples.reduce((p,c) => p + c) : 0
}
```

#### Other Solutions
```js
function solution(number){
  var sum = 0;
  
  for(var i = 1;i< number; i++){
    if(i % 3 == 0 || i % 5 == 0){
      sum += i
    }
  }
  return sum;
}
```

#### Helpful Info