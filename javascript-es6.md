# Javascript ES6

## Functions Overview
* `Object.freeze` Ensure that data in an object will not be changed/mutated
* `const myFunc = () =>` Arrow notation that replaces `const myFunc = function()`
* arrow functions take parameters in the () in its statement, separate parameters with ,
## Let and Const
Two variables created to deal with the problems of "var"

### let
* cannot be overwritten
* can be declared globally and locally
* when declared inside a block statement, its scope is limited to that statement
* a global and local variable of the same name can exist

An improvement over var is made with let as it will not be overwritten beyond its intention

#### An example of let in a for loop
`let variableName;
for (let i = 0; i < 3; i++) {
if (i === 2) {
variableName = function() {
return i;
};
}
}
console.log(variableName(());
// returns 2
console.log(i);
//returns i is not defined`

### Const
A read only variable
* const variables should be written in all caps
* objects are still mutable with const (such as arrays and functions)

#### When to use const
* Const prevents reassignment of variable identifier
* if you need a stable object with data entries that are able to change
NOTE: Remember to select const array entires individually

## Destructuring Assignment for objects and values
use this syntax to simplify assignment
`const {propertyName, propertyname} = varName;`
* This can be used for multiple levels of variables. see these examples
1. Create values
`const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};`
2. access and assign values
`  const {today: {low: lowToday, high: highToday}} = LOCAL_FORECAST;`

* TODO Look up more information on destructuring. especially for arrays
* example:
`const [a, b, ...arr]= list;`
- This will take the first two points in an array that is called and assign them to a and b and put the rest of the array into an array called arr
* destructuring assignment can pass an object as a function parameter

## Template Literals
A type of string that allow for multiline and complex string interpolation
* wrap strings in \`\ backticks (ignore \)
* write placeholders like macros ${placeholderName}

### Free code camp example
* Goal populate an array with failure values from const result
* create a failure Items array
* **push** items in a list from the results object

`const result = {
  success: ["max-length", "no-amd", "prefer-arrow-functions"],
  failure: ["no-var", "var-on-top", "linebreak"],
  skipped: ["no-extra-semi", "no-dup-keys"]
};
function makeList(arr) {
  // Only change code below this line
  const failureItems = [];
  for (let i = 0; i < arr.length; i++) {
    failureItems.push(`<li class="text-warning">${arr[i]}</li>`)
  }
  // Only change code above this line

  return failureItems;
}

const failuresList = makeList(result.failure);`

## the rest parameter
* allows your to create functions that take a variable number of arguments and stores them in an array to access them from within a function later

### Benefits of rest
Allows your to apply:
* map()
* filter()
* reduce(): subtract the numbers in the array, starting from the beginning

## spread operator
Expand arrays and other expressions 
* Just like  with rest, use [...varName] to spread another array into the contents of the new array

** Modules
Allows JS to share code among files
* `<script type="module" src="filename.js"></script></script>` -- place this code into your html to load a module

### Exporting and Importing

#### Exporting
* Export a function so that it can be used by other files
`const add = (x, y) => {
  return x + y;
}

export { add };`

* fallback functions can be exported with **export default function**

#### Importing
* Import a function from another file like so 
`import { add, subtract } from './math_functions.js';`

- where add and subtract are the functions set to export in math_function.js and math_function.js is the file from which they are exported

* import everything from a file with * instead of specifying with {functionName}. remember to specify what they are imported as:
`import * as stringFunctions from "./string_functions.js";`

*importing defaults. you don't use curly braces `import functionName from "./fileName.js";`

## Promise
This is a construct type in javascript.It has 3 states: **pending**, **fulfilled**, and **rejected**. 
* Set these parameters in order to stop a promise from being stuck in the pending state
`const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer represents a response from a server
  let responseFromServer;
    
  if(responseFromServer) {
    resolve("We got the data")// Change this line
  } else {  
    reject("Data not received")// Change this line
  }
        makeServerRequest.then(result => {
      console.log(result);
});`
* This provides a resolve with statement for the if statement being true and a reject statement for false
* the **then** statement explains what to do when the promise is successfully resolved
