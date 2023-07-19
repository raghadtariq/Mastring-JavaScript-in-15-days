
# Day 13:

## Lesson Summary:
- **Benefits** of Typescript and Flow:
1. Catch type-related mistakes.
2. Communicate type intent.
3. Provide IDE feedback ( Integrated Development Environment).
- **Caveats** of Typescript and Flow:
1. Inferencing is best-guess, not a guarantee.
2. Annotations are optional.(TypeScript by default set any type for variables)
3. Any part of the application that isn't typed introduces uncertainty.


--------------------------------
## Scope:
lexical scope mechanism in JS:
- JavaScript organizes scopes with functions and blocks.
- **Shadowing** is adding two varibles with same name in different scopes 


### Undefined vs Undecleared:
- **Undefined** means a variable exists but at the moment it has no value .
- **Undecleared** means that it's never formally decleared in any scope that we have accessedto.

  
  
 ### Lexical scope Elevator:
 (The first floor is our current scope where the referenve is, and the top floor is the global scope)


 ## Coding Exercises:
  #### [Questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

  
  #### Question 1:
  ```javascript
interface HelloWorldPromise {
  (): Promise<string>;
}

interface BooleanCheckPromise {
  (boolean: boolean): Promise<boolean>;
}

interface ReturnObjPromise {
  (): Promise<{ x: string; y: number }>;
}

type PromisesArray = [HelloWorldPromise, BooleanCheckPromise, ReturnObjPromise];

const sayHelloWorld: HelloWorldPromise = () =>
  new Promise((resolve, reject) => {
    resolve("Hello world!");
  });

const checkBoolean: BooleanCheckPromise = (boolean) =>
  new Promise((resolve, reject) => {
    if (boolean) {
      resolve(boolean);
    } else {
      reject(`Input is false :(`);
    }
  });

const returnObj: ReturnObjPromise = () =>
  new Promise((resolve, reject) => {
    resolve({
      x: "meow",
      y: 45,
    });
  });

const promisesArray: PromisesArray = [sayHelloWorld, checkBoolean, returnObj];

const convertToObj = async (array: PromisesArray) => {
  const obj = {};
  for (const promise of array) {
    const result = await promise();
    Object.assign(obj, result);
  }
  return obj;
};
```
  #### Question 2:
  What will be the output of the following code snippet? Pick the right choice then justify your answer with an explanation.
  ```javascript
function testScope1() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
  console.log(a);
  console.log(b);
  console.log(c);
}

testScope1();
```
### The solution:
- C) 1, ReferenceError, ReferenceError
-  var has function scope, so it is accessible within the entire testScope1 function, let & const has block scope, It is only accessible within the if block.

  #### Question 3:
  What will be the output of the following code snippet? Pick the right choice then justify your answer with an explanation.
  ```javascript
function testScope2() {
  console.log(a);
  console.log(b);
  console.log(c);
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
}

testScope2();
```
### The solution:
- A) undefined, ReferenceError, ReferenceError
-  variable a (var) is hoisted to the top of the function scope, let and const have block scope, It is not hoisted to the top of the block.

  #### Question 4:
  What will be the output of the following code snippet? Pick the right choice then justify your answer with an explanation.
  ```javascript

function testScope3() {
  var a = 36;
  let b = 100;
  const c = 45;

  console.log([a, b, c]);

  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;

    console.log([a, b, c]);
  }

  console.log([a, b, c]);
}

testScope3();

```
### The solution:
- C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1,100, 45 ]
-  The first console.log refers to the outer variables, The second console.log inside the if block refers to the newly declared variables,The third console.log after the if block, the outer variables have been modified by the inner block
 
