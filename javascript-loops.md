# Working with Loops

## Types of Loops
* for loop
* forEach loop
* join Loop

**NOTE** Update with while and do/while loops.

## for Loop
Manual looping method, most control of how the loop itself operates but not necesssary for a lot of looping approaches
`for (let i = 0; i < arrayName.length; i++) {
    // assign content per iteration
}`
* if the condition is true, it'll run the statement, if it's false it'll stop
* incrementation can be specified like `i += 10` to increment by 10s

### Down Staircase
This is much easier to code. you just add an extra * for every line
`for (let line = "*"; line.length <=5; line+="*") {
    console.log(line);
}`
* this can be made more dynamic by running it as a function like the staircase below and making the 5 a variable that the function takes
``*
**
***
****
*****`` 

### Inverted staircase
This uses arrays to create a staircase

`const stairCase = n => {
    // define array for each line. use .fill to set the starting content as blank spaces
    const line = Array(n+1).fill(' ');
    //for loop -- i starts at 1 less than n, iterate down to 0
    for (let i = n -1; i > 0; i--) {
        line[i] = "*";
        console.log(line.join(''));
    }
}`
* if n is 5 this will print
``    *
   **
  ***
 ****
*****``
* Review how to use the [fill method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill).

## forEach Loops
These are used with arrays

*  define an output variable. if it's a single string, specify = '';
`const main = document.querySelector('main')

arrayName.forEach(function(item, index) {
    // assign content to the output here. --example uses images and template literals
    // use create element 
    const img = document.createElement('img');

    //assign values 
    img.src = assets/images/md/#{item};
    img.alt = "describe image";

    //append to the containing element
    main.appendChild(img);
    });`
* There are a few different ways to do this, but this will create a gallery of images dynamically

### Example using objects
This exmaple uses definition objects organized in an array. **use the above notation to assign to the DOM**

`let output = '<dl>';

definitions.forEach(function(definition){
    output += <dt>${definition.term}</dt>;
    output += <dd>${definition.definition}</dd>\n;
})
output += '</dl>';
document.querySelector('main').append(output);`

### Example using templates

`const template = document.querySelector('#tlp')
const list = document.querySelector('dl');

definitions.forEach(function(definition) {
    const clone = template.content.cloneNode(true);
    clone.querySelector('dt').innerHTML = definition.term;
    clone.querySelector('dd').innerHTML = definition.definition

    list.appendChile(clone)
});`

## Join Loop
Join loops will connect array items together and give you control of the way that they are spaced. 
* Great for lists of text that need to be displayed in html or anything where you need complex control of how items are grouped
`//define within a function
function arrayListOutput () {
    // link items together between one another. ex: as a list
    let items = arrayName.join('</li><li>')
    // create the containing tags -- use template literal notation
    let itemContent = <ul></li>${item}</li></u>
    // assign to a DOM element
    let listOfThings = document.querySelector('.content-class')
    //
    }`
