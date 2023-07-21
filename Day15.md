# Day 15:

## Lesson Summary:
**Const**: 
- value doesn`t change
- can`t be reassigned
- Reassign in array is alowed.
- only use the const with one of the primitive immutable values.
  <br>
 <br>

  **Hoisting**:
- We can use hoisting to try to describe something without needing to get into the nitty-gritty details.
>  Let dosen't hoist ? -> false.
- Lets and consts still hoist but there is a difference between how they hoist:
  1. let's and consts only hoist to a block, whereas vars hoist to a function.
  2. var when scope starts, initialize it to undefined. let create a location but don't initialize it.
      <br>
 <br>

**Closure** is  when a function “remembers” its lexical scope even when the function is executed outside that lexical scope.
- We use closure for asynchronous AJAX, and all sort of different things.
- Modules: encapsulate data and behavior (methods) together. The state (data) of a module is held by its methods via closure.
- **encapsulation** is a fancy solution CS word (idea of hiding data & behavior).
>  so you can`t have a module, if u don`t have a clouser.





## Coding Exercises :
##### [Questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md
##### QUESTION 1:

```javascript
for (var i = 0; i < 5; i++) {
  (function (index) {
    setTimeout(function () {
      console.log("value of [i] is: ", index);
    }, 100);
  })(i);
}
```

##### QUESTION 2:

```javascript
let array = []; 
for (let i = 0; i < 5; i++) {
   array.push(i); 
   console.log("Current array is: ", array);
}
```

##### QUESTION 3:
##### My solution :

```javascript
let functions = [];

for (let i = 0; i < 5; i++) { 
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```

##### Question 4:

```javascript
const privateCounter = () => {
  let count = 0;

  const increment = () => {
    count++;
  };

  const getCount = () => {
    return count;
  };

  return {
    increment,
    getCount,
  };
};


const counter = privateCounter();

counter.increment();
counter.increment();
console.log(counter.getCount()); 
```

##### Question 5:
```javascript
const generateFibonacci = (count) => {
  let current = 0;
  let next = 1;
  let index = 0;

  const fibonacci = () => {
    if (index < count) {
      const result = current;
      [current, next] = [next, current + next];
      index++;
      return result;
    } else {
      return undefined; 
    }
  };

  return fibonacci;
};
```
