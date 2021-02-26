# Arrays in Javascript
Arrays are datastructures. Unlike objects, they use indices.

* Declare an array like so:
`const arrayName = ['array-value', 'array-value2', 'array-value3']`

##  Array Manipulation

### Reading content

* `arrayName.length`
 How many items are in an array

* `arrayName[1]`
Access content from a known index position

### Add to Arrays
* Add element to the **end** of the array:
`arrayName.push('content')`
* Add element to the **beginning** of the array
`arrayName.unshift('content')`

### Remove items from an array
NOTE: These can be used to assign the value from an array to a variable
* Remove an element from the **end** of the array.
`arrayName.pop()`
* Remove an item from the **start** of the array
`arrayName.shift()`

### Joining and Splitting Arrays
* `const arrayName3 = arrayName1.concat(arrayName2)`
Merge two or more arrays together
* `arrayName.splice(start-number, delete-number, 'content')`
Remove or replace existing elements or add new elements at the index of the start-number. **if the delete number is set to 0**, it will just input the new content at whatever index point you specify with the start number

### Finding index of something in an array
* `arrayName.indexOf('item-name');`
This will give you the index position of an array item. works well with splice for when you want to find where something is to replace it.
