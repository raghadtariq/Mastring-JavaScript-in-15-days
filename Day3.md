
# Day3 : Arrays

This README file summarizes the JavaScript lesson on Arrays in JS.

## Lesson Summary
**Arrays:**
 - arrays let us keep multiple values together in a single collection.
 - arrays can be empty, or hold a single item.
 - arrays can hold any type of item, or mix & match!

**Method that used in Arrays:**
length, includes, push, sort, join, concat,...

**mutable vs. immutable:**
- "Mutable" data can be edited (e.g. Arrays).
- "Immutable" data always stays the same (e.g. strings & other primitives).
- Variables themselves can also be (im)mutable (by using const to declare it).
- Using immutable data is better.


  ## Coding Exercises

### [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)

#### My Solution
```
function timesFive(num) {
    return num * 5;
  }
  
  const answer = timesFive(3);
```

### [Local Scope and Functions:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
#### My Solution
```
function myLocalScope() {
    // Only change code below this line
    const myVar = "anwar";
  
    console.log('inside myLocalScope', myVar);
  }
  myLocalScope();
  
  // Run and check the console
  // myVar is not defined outside of myLocalScope
  console.log('outside myLocalScope', myVar);
```

### [Global Scope and Functions:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)

#### My Solution
```
// Declare the myGlobal variable below this line
let myGlobal = 10;

function fun1() {
  oopsGlobal = 5;// Assign 5 to oopsGlobal here

}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```
### [Global vs. Local Scope in Functions:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)
#### My Solution
```
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  const outerWear = "sweater";

  // Only change code above this line
  return outerWear;
}

myOutfit();
```
### [Stand in Line:](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
#### My Solution
```
function nextInLine(arr, item) {
    // Only change code below this line
    arr.push(item);
    const value = arr.shift();
    return value;
    // Only change code above this line
  }
  
  // Setup
  let testArr = [1, 2, 3, 4, 5];
  
  // Display code
  console.log("Before: " + JSON.stringify(testArr));
  console.log(nextInLine(testArr, 6));
  console.log("After: " + JSON.stringify(testArr));
```

