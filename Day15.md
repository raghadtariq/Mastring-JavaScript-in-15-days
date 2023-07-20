# Day 15:

## Lesson Summary:


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
