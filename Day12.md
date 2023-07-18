# Day 12:

## Lesson Summary:
>  every thing in JS is an object is a false statement.
- Some primitive types that exist in JS:
- undefined, string, number, boolean, object, symbol
- Some types and subtypes:
- undeclared, null, function, array, bigint
- Objects: Object, function, array
- Not objects: undefined, string, number, boolean, object, symbol, null, bigint(future)
- In JavaScript, variables don't have types, values do.
  
<br>

 - **NaN** refers to ("not a number") , It's an invalid number becuause it comes from numeric operations  === failed in Nan & -0
- NaN is the only value in JavaScript that is not equal to itself
> **Object.is( , )** [it’s built in cheaker and a
better way for cheaking equality (better than ===)]

<br>

### Fundamental Objects:
aka: Built-In Objects
aka: Native Functions
- to use fundamental use **new**(to construct them):
Object(), Array(), Function(), Date(), RegExp(), Error()
- **NEVER** use new with:
 String(), Number(), Boolean()

<br>

## Coding Examples:
 - **Negative zero:** 
```javaScript
-0 === 0                // true
Object.is(-0 ,0 )       // false
```


  ## Coding Excercises:
  #### [Questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/146299d463da8ad3a5dfeb926ad8153c2c6a11bd/learning-sprint-1/week3-day1-tasks/tasks.md)

  #### Question 1::
  ```javascript
function convertStringToNumber(input) {
 if (typeof input === 'string') {
    return +input;
  } else {
    return { value: input, type: typeof input };
  }
}
```
  
#### Question 2:

```javascript
const checkNaN = (value) => {
  return Number.isNaN(value);
}
```


#### Question 3:

```javascript
function isEmptyValue(value) {
  return value === undefined || value === null || value === "";
}
```
#### Question 4:

```javascript
function compareObjects(input1, input2) {
  if (typeof input1 !== 'object' || typeof input2 !== 'object') {
    return [input1, input2];
  }

  const keys1 = Object.keys(input1);
  const keys2 = Object.keys(input2);

  if (keys1.length !== keys2.length) {
    return false;
  }

  for (let key of keys1) {
    if (!input2.hasOwnProperty(key) || input1[key] !== input2[key]) {
      return false;
    }
  }

  return true;
}
```

#### Question 5:

```javascript
const complexCoercion = (input) => {
  if (typeof input === 'number') {
    return Boolean(input.toString());
  } else if (typeof input === 'string') {
    return Boolean(input);
  } else if (input === null || input === undefined) {
    return false;
  } else {
    return input;
  }
};
```
