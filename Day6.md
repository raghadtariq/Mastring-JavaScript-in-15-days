# Day6:

## Lesson summary:

### Data Fetching & Promises:
> **URLs** point to resources on the web
> **APIs (Application Programming Interface)** services that are exposing a whole bunch of data at acertin URLs**,** provide URLs that point at data we care about

### fetching data
`fetch()` is a built-in function witch let us use javaScript to load data from APIs, ex. `fetch('https://getemoji.com/');`, and it returns a **promise**.
 
### .json() :
It's body contains the data we care about
it stands for javaScript object notation.
But we have to read the body somehow
- Note:
> json() is async fun

### promise
promises promise us that it will give us the data we want, but it does not hava it yet.
- promises can be in three states:
1. pending: still waiting for the value.
2. fulfilled (resolved): got the value successfully.
3. rejected: could not get the value.

### await 
await let us tell javaScript to stop and wait for an asynchronous operation to finish.
```javascript
//example
let response = await fetch("URL")
// it will wait for it to resolve before continuing with our code.
```
- `response.json()` to parse the body of response as a JSON object, and will return another promise, so we will use await again.
```javascript
let response = await fetch("URL");
let body = await response.json();
```
### Destructuring Data
- Destructuring is a fancy way of declaring multiple variables at once.
  ```
  let {name, nickname} = spices[0];
  ```
- We can destructure, ignore, and use commas to "skip" values n the array.
- and we can apply it on arrays.
- the order does not matter in objects destructuring, but it matter in array destructuring.

### Async Functions
- If we try to await something in a regular function, JS doesn't allow it, so we need to make it an async function.
```javascript
  async function fetchResponse(url) {
    const response = await fetch(url);
    return response;
}
```
