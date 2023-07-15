
# Day 8 :

This README file summarizes the JavaScript lesson on JavaScript principles & Functions & Callbacks.

## Lesson Summary:

### JavaScript principles:
**Execution context:**

Created to run the code of a function - has 2 parts :
1. Goes through the code line-by-line and runs/ ’executes’ each line - known as the `thread of execution`.
2. Saves ‘data’ like strings and arrays so we can use that data later - in its `memory` - We can even save code (‘functions’).

### Call stack: 

It is a traditional way of storing information in a computer

JavaScript keeps track of what function is currently running (where’s the thread of execution)

* Run a function - add to call stack
* Finish running the function - JS removes it from call stack
* Whatever is top of the call stack - that’s the function we’re   currently running


### Callbacks & Higher Order Functions:

- One of the most misunderstood concepts in JavaScript.
- Enables powerful pro-level functions like map, filter, and reduce.
- Makes our code more declarative and readable.

`Functions in javascript = first class objects`

Which is the `Higher Order` Function?
- The outer function that takes in a function is a higher-order function.

Which is the `Callback` Function?
- The function we insert is the callback function

### Arrow function:
- Shorted way to save functions.

--------------------------------------------------------------

## Coding Exercises:
#### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)

##### my solution:
```javascript
const squareList = arr => {
  // Only change code below this line
  return arr.filter(num => num > 0 && num % parseInt(num) ===0).map(num=> Math.pow(num,2));
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

#### [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

##### my solution:
```javascript
const urlSlug= title => {
  return title.split(" ")
    .filter(substr => substr !== "")
    .join("-")
    .toLowerCase();
}
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```

#### [Functions and Callbacks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
Implement a JavaScript function called mapAsync that takes an array and a callback function. The function should map each element of the array to a new value using the callback function asynchronously.

The final result should be returned as a Promise.


##### my soluyion 
```javascript
function mapAsync(array, callback) {
  return new Promise((resolve, reject) => {
    const results = [];
    let done = 0;

    for (let i = 0; i < array.length; i++) {
      callback(array[i])
        .then(result => {
          results[i] = result;
          done++;

          if (done === array.length) {
            resolve(results);
          }
        })
        .catch(error => {
          reject(error);
        });
    }
  });
}
```

#### [Call Stack and Recursion](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
Write a JavaScript function called sumRange that calculates the sum of all integers in a given range. The function should use recursion to handle the calculation and demonstrate understanding of the call stack.

##### my solution 
```javascript
function sumRange(start, end) {
  if (start === end) {
    return start; 
  } else if (start > end) {
    return 0; 
  } else {
    return start + sumRange(start + 1, end); 
  }
}
```
