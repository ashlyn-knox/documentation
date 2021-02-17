# Javascript Basic String Manipulation
An overview of useful string methods, regular expressions, and how to access and apply them.

## String Methods

### charAt()
use this to check what char is located at what position. specify the index position
`stringName.charAt(1)`: Returns what character is at the second position in the string index

### charCodeAt(indexPosition)
Returns ascii value of the character at a specific index
`stringName.charCodeAt(1)`: if the letter at index 1 is "r" then it will give you 114
* Useful if you want to specifiy ranges of letters via ascii codes

### concat()
Joins two or more strings and returns thems
`stringOne.concat(stringTwo)`: Returns the two strings put together. Remember that this is space sensitive

### endsWith()
Checks if a string ends with a particular character and returns a boolean value
`stringOne.endsWith("to")`: Will return a true or false if the word "to" is in it

### fromCharCode(asciiCode)
Like charCodeAt() but this time you put in the asciivalue into it.
`stringName.fromCharCode(114)`: returns 'r'

### includes()
Checks if a specified value is in the string. returns a boolean
`stringName.includes("one")`: tells you if the word one is there

### indexOf() and lastIndexOf()

`stringName.indexOf()`: gives first index
`stringName.lastIndexOf()`: gives the index position of the last found

### match()
to be used with a regular expression. will return an array with all of the matches in it. Doesn't give the position though
`stringName.match(/end/g)`: will look through the whole string(g for global)for the word end

### repeat()
returns a string that comprises of the called string repeated of the specified number of times.
`stringName.repeat(5)`: will print out whatever is in stringName 5 times.
* useful if you have any repetitive text that needs to be displayed

### replace()
This also uses a regular expression **or** a specified value. and returns a new string.
`stringName.replace(/end/g, "END")`: this will replace all instances of the word end with END.

### search()
Returns the position of the first match of the specified value **or** regular expression.
`stringName.search("word")`: will look for the first instance of the word "word" and tell you what it's index position is

### slice()
Extract part of the string. You specify the beginning and end **index positions**
`stringName.slice(8,16)`: will return from index 9 to and including 16. it cuts to the right of 8

### split()
Great for finding words. It will return an **array** of substrings. Specify what you are to split it up based on
stringName.split(' ') This will cut based on the space. It's not perfect as many spaces and starting with spaces will cause errors

### startsWith()
Returns a boolean true or false if the string starts with the specified characters
`stringName.startsWith("who")`: will let you know if it starts with "who"

### substr()
Specify where the slice starts with the first number, and then the second number is how many index positions from your start point are cut.
`stringName.substr(4, 10)`: this will return anything from the 5th index point to the 15th index point

### substring()
Kind of like slice but for characters between two **specified indices**.
`stringName.substring(4, 10)`: will return whatever is in 5 10

### toLowerCase() and toUpperCase()
self explanatory. changes everything in the string to lower or uppercase
`stringName.toLowerCase()` and same for upper

### trim()
cut white space from front and end of a string. helpful to use with split for word finding.
`stringName.trim()`: will cut front and end space off. This can be specified futher.

## Regular Expressions
To be added

## Applications

### With a template literal in a function
1. outside the function specify your query selector for your template literal and any selectors for your functions
`const textInput = document.querySelector('#textarea-id');`
`const wordCount = document.querySelector('.word-count');`
2. create your function. This one is attached to a textarea input
`text.addEventListener('input', () => {

});`
3. add your variable to the event listener function. this will make it so that when the event is triggered, your value will update. This one will add text to the innerHTML of your word-count class. innerText also works here
`wordCount.innerHTML = ${text.value.split(' ').length} : Words`
* NOTE: the symbol used for template literals is also used for marking code in markdown. so the string literal ones aren't being used here but need to be.
4. end result
`text.addEventListener('input', () => {
wordCount.innerHTML = ${text.value.split(' ').length} : Words
});`

* use value to access the actual text within a variable

### Getting attributes
a bunch of attributes can accessed from strings. This example takes 'maxlength' which has been specified in the html already.
`const limit = text.getAttribute('maxlength');`
* Find more at [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)

