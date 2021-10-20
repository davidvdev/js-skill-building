---
tags: algo
---

### [Highest Scoring Word](https://www.codewars.com/kata/57eb8fcdf670e99d9b000272/train/javascript)

> Given a string of words, you need to find the highest scoring word.
>
Each letter of a word scores points according to its position in the alphabet: `a = 1, b = 2, c = 3` etc.
>
You need to return the highest scoring word as a string.
>
If two words score the same, return the word that appears earliest in the original string.
>
All letters will be lowercase and all inputs will be valid.

#### Pseudo Code
```js
function high(x){
// init key obj {a:1, b:2 ...}
// init score & word obj
//   split high string to array of words
//   loop over array
//   loop over each word and tabulate score
//   compare word score to score obj
//     if score is higher, replace score value and add word value to obj
//   return score obj.word
}
```

#### My Solution Code
```js
function high(x){
  const l = {
    a:1,b:2,c:3,d:4,e:5,f:6,g:7,h:8,i:9,j:10,k:11,l:12,m:13,n:14,
    o:15,p:16,q:17,r:18,s:19,t:20,u:21,v:22,w:23,x:24,y:25,z:26        
    }
  const h = {score: 0, word: ""}
  
  const words = x.split(" ")
  
  for(let i = 0; i < words.length; i++ ){
    let score = 0
    for (const letter of words[i]) score += l[letter]
    if (score > h.score){
      h.score = score
      h.word = words[i]
    }
  }
  
  return h.word
}
```

#### Other Solutions
```js
function high(s){
  let as = s.split(' ').map(s=>[...s].reduce((a,b)=>a+b.charCodeAt(0)-96,0));
  return s.split(' ')[as.indexOf(Math.max(...as))];
}
```

#### Helpful Info