### [Ones and Zeros](jsAlgo)

> Given an array of ones and zeroes, convert the equivalent binary value to an integer.

Eg: `[0, 0, 0, 1]` is treated as `0001` which is the binary representation of `1`.

Examples:

```
Testing: [0, 0, 0, 1] ==> 1
Testing: [0, 0, 1, 0] ==> 2
Testing: [0, 1, 0, 1] ==> 5
Testing: [1, 0, 0, 1] ==> 9
Testing: [0, 0, 1, 0] ==> 2
Testing: [0, 1, 1, 0] ==> 6
Testing: [1, 1, 1, 1] ==> 15
Testing: [1, 0, 1, 1] ==> 11
```

However, the arrays can have varying lengths, not just limited to `4`.

#### Pseudo Code
```js
const binaryArrayToNumber = arr => {
  // init sum variable
//   loop over the array
//   for each value use (arr[i] * 2<Math.exponenet(arr.length-i))
//   add the result to the sum variable
//   exit loop and return sum variable
};
```

#### My Solution Code
```js
const binaryArrayToNumber = arr => {
  let num = 0
  for(let i = 1; i <= arr.length; i++){
    num += (arr[i-1] * Math.pow(2, (arr.length - i) ))
  }
  return num
};
```

#### Other Solutions
```js
const binaryArrayToNumber = arr => {
  return parseInt(arr.join(""), 2)
};
```


#### Helpful Info
[Counting in Binary](https://en.wikipedia.org/wiki/Binary_number#Counting_in_binary)

<iframe src="https://en.wikipedia.org/wiki/Binary_number#Counting_in_binary" height="500px" width="100%" />