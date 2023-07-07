
# Day2 : Values & Data Type,Operators and Expressions
This README file summarizes the JavaScript lesson on Values & Data Type,Operators and Expressions.

## Lesson Summary
- JS has two kinds of data:
- Primitive types (e.g. strings, numbers)
- Objects (e.g. document & friends)

- I learn about typeOf (tells you the type of a value).
-  indexOf (What's the index of a specific character?).
-  includes (Does this string contains some other string?).
-  startWith ,toLowerCase,etc...

-I've learned what's the differences between strict and loosey-goosey operators and that I should almost always use the strict version.

- I've also learned what's the differences between statements and questions.


## Coding Exercises

### [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

#### My Solution
```
const contacts = [
    {
      firstName: "Akira",
      lastName: "Laine",
      number: "0543236543",
      likes: ["Pizza", "Coding", "Brownie Points"],
    },
    {
      firstName: "Harry",
      lastName: "Potter",
      number: "0994372684",
      likes: ["Hogwarts", "Magic", "Hagrid"],
    },
    {
      firstName: "Sherlock",
      lastName: "Holmes",
      number: "0487345643",
      likes: ["Intriguing Cases", "Violin"],
    },
    {
      firstName: "Kristian",
      lastName: "Vos",
      number: "unknown",
      likes: ["JavaScript", "Gaming", "Foxes"],
    },
  ];
  
  function lookUpProfile(name, prop) {
    // Only change code below this line
  
    for (let i = 0; i < contacts.length; i++) {
      if (contacts[i].firstName === name) {
        if (prop in contacts[i]) {
          return contacts[i][prop];
        } else {
          return "No such property";
        }
      }
    }
    return "No such contact";
  
    // Only change code above this line
  }
  
  lookUpProfile("Akira", "likes");
```

### [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)

#### My Solution
```
// Only change code below this line
  
    return arr.slice(2, 4);
  }
  // Only change code above this line
  console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```

### [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)

#### My Solution
```
function spreadOut() {
    let fragment = ['to', 'code'];
    let sentence = ['learning', ...fragment, 'is', 'fun']; // Change this line
    return sentence;
  }
  
  console.log(spreadOut());
```
