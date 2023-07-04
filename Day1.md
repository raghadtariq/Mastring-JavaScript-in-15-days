
# Day1 : DOM

This README file summarizes the JavaScript lesson on DOM (Document Object Model) . DOM is a programming interface for HTML(HyperText Markup Language) and XML(Extensible markup language) documents. It defines the logical structure of documents and the way a document is accessed and manipulated.
## Lesson Summary

Some commands I've learned:
- document.title : the page (document) title.
- document.body : the body elemnt.
- document.body.children : all the elemnts within the body.
- document.getElementById("board") / document.querySelector("board") : the (first) element with id = "board".
- document.getElementsByTagName("h1") / document.querySelectorAll("h1") :all the h1 elements.
- document.getElementsByClassName("player") / document.querySelectorAll(".player") : all the elemnts with class ="player".
- document.getElementsByClassName("player").length / document.querySelectorAll(".player").length : the number of elements with class ="player".
- document.getElementById("p1-name").textContent : the text inside the element with id= "p1-name".

### Editing the DOM with JS :
- document.title ="My Page" : change the page title .
- document.getElementById("#p1-name").textContent="Sofia": replace the text of the #p1-name element.
- document.getElementById("p1-name").append(" & friend"): add to the end of the elements current text.

## Coding Examples

- Type commands in the console to retrieve:

1- all the p elements
2- the text "X"
3- the number of squares in the board
4- the text "A game you know
```
document.getElementsByTagName("p")
document.getElementById("p1-symbol").textContent 
document.querySelectorAll(".square").length
document.querySelector("h2").textContent
```
## Coding Exercises

### [Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)

#### My Solution
```
let a = 5;
let b = 12;
let c = 4.6;

a *= 5;
b *= 3 ;
c *= 10;
```

### [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

#### My Solution
```
let myStr="This is the first sentence";
myStr+="This is the second sentence.";
```

### [Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)

#### My Solution
```
const lastName = "Lovelace";
const secondToLastLetterOfLastName = lastName[lastName.length -2];
```
