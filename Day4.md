
# Day4 : 

## Lesson Summary:

**Objects**

- An object is a group of values; unlike arrays, we can do sth better them:
- Objects collect multiple values together to describe more complex data.

**Functions:**
> values are things,
> vatiables point to things,
> functions do things.
- we have two perspective when we talk about functions:
1. creation:
```javascript
function funName(paras) {
 //the body
}
```
2. using:
```javascript
funName(args);
```
**Arrow fun =>:**

For one-parameter functions, parentheses are optional, but for multiple parameters, parentheses are required.

**let vs. var**

- let: re-assignable, block-scoped, can`t declare let variable with the same name in the same scope & hoisted to the top to block scope.
- var: re-assignable, globally scoped & hoisted to the top.

 
## Coding Examples:
**Objects:**

```
const person = {
  name: ["Amy", "Hanry"],
  age: 30,
  introduceSelf: function () {
    console.log(`Hi! I'm ${this.name[0]}.`);
  },
};
```
-------------------------------------------------------------
**Functions:**

1. given 2 numbers, return their product

```
function multiply(a,b){
return a*b;
}
```

2. given a lowercase string, log it in all caps to the console

```
const yell = function(word){
   return word.toUpperCase();
}
```

3. longerThan: given 2 arrays, return whether the first is longer than the second

```
function largerThan(ar1,ar2){
  return ar1.length > ar2.length;
}
```
-----------------------------------------------------------
**Arrow fun =>:**

 1. given 2 numbers, return the first divided by the second

  ```
 const divide = (a,b) => a / b;
```

 2. given an uppercase string, log it in all lowercase to the console

```
const toLower = (word) => console.log(word.toLowerCase());
```

 3. given 2 arrays, return whether the first is shorter than the second

```
const shorterThan = (ar1 , ar2) => ar1.length < ar2.length;
```


## Coding Exercises:
### [Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)
#### my solution:
```
function checkSign(num) {
    return (num > 0) ? "positive" : (num < 0) ? "negative" : "zero";
    }
  
  checkSign(10);
```
### [Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)
#### my solution:
```
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  return strokes === 1 ? names[0] : strokes <= par - 2 ? names[1] : strokes === par - 1 ? names[2] : strokes === par ? names[3] : strokes === par+1 ? names[4] : strokes === par +2 ? names[5] : names[6] ;
}
golfScore(5, 4);
```
### [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)
#### my solution:
```
const ratings = watchList.map(item => ({
  title: item["Title"],
  rating: item["imdbRating"]
}));
console.log(JSON.stringify(ratings));
```
### [Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)
#### my solution:
```
const filteredList = watchList
  .filter(movie => {
    return parseFloat(movie.imdbRating) >= 8.0;
  })
  .map(movie => {
    return {
      title: movie.Title,
      rating: movie.imdbRating
    };
  });
console.log(filteredList);
```
