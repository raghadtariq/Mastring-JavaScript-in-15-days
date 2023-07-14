# Day7: 
This README file summarizes the JavaScript lesson on Modules & Debugging.

## Lesson Summary:
###  Modules
- Modules let us split big codebases across multiple files.
- - use import && export.
- IF `<script type = "text/javascript">`: they are still accessible to global scope.
-  IF `<script type = "module">`: not able to access any of these variables that declare in " local scope".

```javaScript
<script type="module">
    //...
</script>

// JS modules work differently from JS scripts-> One difference is that we can't use await outside of a function in a script
```
### Debugging: 
We can console.log() (or .warn() or .error()) is one way to understand what's happening when your program runs

```javaScript
function whyIsntThisWorking(input) {
    console.log("Well at least we got this far");
    console.log(input);
    return thingThatDoesntWork(input);
}
```

<br>
You can also use the browser's debugger to pause JS and inspect what's happening

```javaScript
function whyIsntThisWorking(input) {
    debugger;
    return thingThatDoesntWork(input);
}
```
The debugger statement creates a breakpoint where JS will pause and let you look around

   
 
