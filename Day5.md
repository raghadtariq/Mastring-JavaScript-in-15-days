# Day 5:

## Lesson summary:
### ** Events & Handlers: **
-  `.addEventListener()` method lets us listen for events on a DOM element.
-  `event.target` is the element the event fired on.

- `.addEventListener()` takes 2 parameters:
1. The name of the event to listen to (e.g. "click")
2. A handler function that JS calls when that event is fired on this element

```javascript 
document.addEventListener("click", () => {
    console.log("clicked")
});
```
#### Some events: 
1. **["click"]**
2. **["dblclick"]** 
3. **["mouseover"]**
4. **["mouseout"]**

### ** map & filter: **

#### map : 
 Calls a function on each item in an array to create a new array
```javascript
const numbers = [65, 44, 12, 4];
const newArr = numbers.map(myFunction)

function myFunction(num) {
  return num * 10;
}
```

#### filter :
it calls a true/false function on each item and creates a new array with only the items where the function values true.
```javascript
const ages = [32, 33, 16, 40];
const result = ages.filter(checkAdult);

function checkAdult(age) {
  return age >= 18;
}
```

### spread `...` :
- another neat trick for iterating over arrays.
- We can use it to put all the items from one array inside another array.
- We can also use it to pass all the items from an array as arguments to a function or method.

```javascript
const skills = ["HTML", "CSS", "JS"];
const newSkills = ["React", "TypeScript", "Node"]
skills.push(...newSkills);
console.log(...skills);
```

---------------------------------------------------
## Day 5 project:

#### ("https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/styles.css")

```javascript
const characterList = document.getElementById("characterList");

async function fetchCharacters() {
  try {
    const response = await fetch("https://rickandmortyapi.com/api/character?status=alive");
    if (!response.ok) {
      throw new Error("Error fetching character data");
    }
    const data = await response.json();
    const characters = data.results.slice(0, 50);

    characters.forEach((character) => {
      const li = document.createElement("li");
      const img = document.createElement("img");
      const name = document.createElement("p");
      const location = document.createElement("p");
      const species = document.createElement("p");
      const gender = document.createElement("p");

      img.src = character.image;
      name.textContent = `Name: ${character.name}`;
      location.textContent = `Location: ${character.location.name}`;
      species.textContent = `Species: ${character.species}`;
      gender.textContent = `Gender: ${character.gender}`;

      li.appendChild(img);
      li.appendChild(name);
      li.appendChild(location);
      li.appendChild(species);
      li.appendChild(gender);

      characterList.appendChild(li);
    });
  } catch (error) {
    const errorMessage = document.createElement("p");
    errorMessage.textContent = "Error fetching character data";
    characterList.appendChild(errorMessage);
  }
}

window.onload = fetchCharacters;
```

```CSS
* {
  padding: 0px;
  margin: 0px;
}

body {
  background-color: gainsboro;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

.title {
  color:black;
  font-size: 48px;
  text-align: center;
  margin: 40px;
}

h1 {
  text-align: center;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: flex;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}

img {
  width: 50px;
  height: 50px;
  margin-right: 10px;
}

p {
  margin: 0;
}
```

