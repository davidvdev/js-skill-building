---
tags: algo
---

### [Break camelCase](https://www.codewars.com/kata/5208f99aee097e6552000148/train/javascript)

> Complete the solution so that the function will break up camel casing, using a space between words.
>
>### Example
>```
>"camelCasing"  =>  "camel Casing"
">identifier"   =>  "identifier"
>""             =>  ""
>```

#### Pseudo Code
```js
// complete the function
function solution(string) {
//     init spaces Arr
//     loop over string
//        start at i=1
//        check casing of each letter with charAt
//          if true record i to spacesArr
//   return spliced string with spaces inserted according to arr
}
```

#### My Solution Code
```js
// complete the function
function solution(string) {
  const spaces = []
  for (let i = 1; i < string.length; i++){
    const v = string.charCodeAt(i)
    if(v > 64 && v < 91) spaces.push(i)
  }

  const strArr = [...string]  

  spaces.map(s => strArr.splice(s + spaces.indexOf(s),0," "))
  
  return strArr.join("")
}
```

#### Other Solutions
```js
// complete the function
function solution(string) {
  return(string.replace(/([A-Z])/g, ' $1'));
}
```
- good use of regex

#### Helpful Info
- [helpful StackOverflow](https://stackoverflow.com/questions/4434076/best-way-to-alphanumeric-check-in-javascript)