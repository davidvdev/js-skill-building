---
tags: algo
---

### [Vasya Clerk](https://www.codewars.com/kata/555615a77ebc7c2c8a0000b8/train/javascript)

> The new "Avengers" movie has just been released! There are a lot of people at the cinema box office standing in a huge line. Each of them has a single `100`, `50` or `25` dollar bill. An "Avengers" ticket costs `25 dollars`.
>
>Vasya is currently working as a clerk. He wants to sell a ticket to every single person in this line.
>
>Can Vasya sell a ticket to every person and give change if he initially has no money and sells the tickets strictly in the order people queue?
>
>Return `YES`, if Vasya can sell a ticket to every person and give change with the bills he has at hand at that moment. Otherwise return `NO`.

Examples:
```javascript
tickets([25, 25, 50]) // => YES 
tickets([25, 100]) // => NO. Vasya will not have enough money to give change to 100 dollars
tickets([25, 25, 50, 50, 100]) // => NO. Vasya will not have the right bills to give 75 dollars of change (you can't make two bills of 25 from one of 50)
```

#### Pseudo Code
```js
function tickets(peopleInLine){
//   INIT cashDrawer arr
  // Loop over peopleInLine array
//   SWITCH statement
//   if arr[i] === 25, PASS proceed to next value
//   if arr[i] === 50, find & remove a 25 in cashDrawer arr
//   if arr[i] === 100, find & remove 3 25s or 1 50 and 1 25 in cashDrawer arr
//   if any step fails, return "NO"
//   if all steps pass, return "YES"
}
```

#### My Solution Code
```js
function tickets(peopleInLine){
  const cashDrawer = []
  let paid = "YES"
  for(let i = 0; i < peopleInLine.length; i++){
    if (paid === "NO") return paid
    switch(peopleInLine[i]){
      case 25:
        cashDrawer.push(peopleInLine[i])
        break;
      case 50:
        if(cashDrawer.filter(bill => bill === 25).length >= 1){
          cashDrawer.splice(cashDrawer.indexOf(25), 1)
          cashDrawer.push(peopleInLine[i])
        } else {
          paid = "NO"
        }
        break;
      case 100:
        if(cashDrawer.filter(bill => bill === 25).length >= 1 && cashDrawer.filter(bill => bill === 50).length >= 1){
          cashDrawer.splice(cashDrawer.indexOf(25), 1)
          cashDrawer.splice(cashDrawer.indexOf(50), 1)
          cashDrawer.push(peopleInLine[i])
        } else if (cashDrawer.filter(bill => bill === 25).length >= 3){
          for (let j=0; j < 3; j++) cashDrawer.splice(cashDrawer.indexOf(25), 1)
          cashDrawer.push(peopleInLine[i])
        } else {
          paid = "NO"
        }
        break;
    }
  }
  return paid
}
```

#### Other Solutions
```js
function tickets(peopleInLine){
  let [c25,c50,c100] = [0,0,0];
  for(let v of peopleInLine) {
    if(v===25) c25++;
    else if(v===50) {c50++; c25--;}
    else if(v===100) {c25--; c50>0?c50--:c25-=2;}
    if(c25<0||c50<0) return 'NO'
  }
  return 'YES'
}
```
- Not the top solution, but I think this is the most elegant. It handles it in the same way that I was trying to, but much more straightforward and legible.
#### Helpful Info