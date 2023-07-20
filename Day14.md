# Day 14:

## Lesson Summary:
- If the word function is not the first thing in the statement ( variable, operator, parentheses , ...) => It's not a decleration ,It's an expression (Named function expression).
- Anonymous function : function expression but with no name.
- Why we always prefer named funstion Expressions?
 1. Reliable function self-reference (recursion, etc)
2. More debuggable stack traces
3. More self-documenting code
- An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.
- Blocks are not scopes until they have a let or const inside of them.
 

## Coding Exercises:
  #### [Questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)

  
  #### Question 1:

```javascript
const arrowHOF = (normalFunc) => {
  return (...args) => {
    return (...multiplierArgs) => {
      return normalFunc(...args) * multiplierArgs.length;
    };
  };
};
```
  #### Question 2:
```javascript
const preserveThis = (func) => {
  return (...args) => {
    return func.apply(func, args);
  };
};
```

  #### Question 3:
##### Example 1:
var declaration in the global scope.
##### Example 2 :
var declaration in global & local scope, but when console there is var declaration in local scope.
