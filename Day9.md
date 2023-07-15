
## Day 9:
This README file summarizes the JavaScript lesson on closures.

## Lesson Summary:
## Closure 
- A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment).
- In other words, a closure gives you access to an outer function's scope from an inner function. 
- In JavaScript, closures are created every time a function is created, at function creation time.


-  When our functions get called, we create a live store of data (local
memory/variable environment/state) for that function’s execution context.
-  When the function finishes executing, its local memory is deleted (except the
returned value)
-  But what if our functions could hold on to live data between executions?
-  This would let our function definitions have an associated cache/persistent
memory
- But it all starts with us returning a function from another function

### The backpack or Closure: 

The data that my inner function used from the outer function

> The inner fun data will be brought wherever the function goes


#### Other names forthis backpack:
* Closed Over `Variable Environment` (C.O.V.E.)
* Persistent Lexical Scope Referenced Data (P.L.S.R.D.)
* `Backpack`
* `Closure`

*Practical Applications:*  
> * Closure gives our functions persistent memories and entirely new toolkit for writing professional code

1. Helper functions: Everyday professional helper functions like ‘once’ and ‘memoize’
2. Iterators and generators: Which use lexical scoping and closure to achieve the
most contemporary patterns for handling data in JavaScript
3. Module pattern: Preserve state for the life of an application without polluting the
global namespace
4. Asynchronous JavaScript: Callbacks and Promises rely on closure to persist state
in an asynchronous environment
----------------------------------------------------------


## Coding Examples:

```javaScript
function createFunction() {
	 function multiplyBy2 (num){
		  return num*2;
	 }
	 return multiplyBy2;
}
const generatedFunc = createFunction();
const result = generatedFunc(3); // 6

```
```javaScript
//  all the variables in the outer fun that the inner fun used iy, my res can
//  also access it, because it is attached to my fun

let outer = ()=>{
    const x = 5;
    const  inner = ()=>{
        return x
    }
    return inner()
}

const res = outer()
console.log(res)
```

----------------------------------------------------------------------------
## Coding Exercises:

#### [Questions for closure](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/f1770252e28aab81cc91fe65db1ef2cf1dca6b37/learning-sprint-1/week2-day2-tasks/tasks.md)

#### [Question 1] 
##### my solution:

```javascript
function createCounter(start) {
   let counter = start;
      function incrementCounter(){
        counter++;
        return counter;
    }
    return incrementCounter
}

const increment = createCounter(5);
```

#### [Question 2]
##### my solution:

```javascript
function calculateAverage (array){
        let sum = 0;
        for( let i = 0 ; i < array.length ; i++ ){
            sum += array[i];
         }
        function average() {
            return sum / array.length;
        }

        return average;
}


const Avg = calculateAverage([1,2,3,4,5,6] );
```

#### [Question 3]
##### my solution:

```javascript
function powerOf(base) {
    return function(exp) {
      return Math.pow(base, exp);
    };
  }
  
  const powerOfTwo = powerOf(3);
  console.log(powerOfTwo(4)); 
  ```

#### [Question 4]
##### my solution 

```javascript
function compose(...functions) {
    return function(input) {
      let result = input;
  
      for (let i = functions.length - 1; i >= 0; i--) {
        result = functions[i](result);
      }
  
      return result;
    }
  }
```

