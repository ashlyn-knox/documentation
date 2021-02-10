# Javascript 02-10-2021

## Key Terms
* Global: all code not in a function
* Global Execution Content: Environment available everywhere in app
* Lexical Environment: where something sits physically in the code that you write
* Syntax parser: a program that reads code and determines if your syntax is valid
* Document Object: where most work happens, top level under the window. Referred to as the DOM
* Window object: global object that contains everything
* Property: A variable that lives inside an object. access with dot notation
* A function that lives inside an object.

## Script Tags
* put scripts under tags that they affect so that the page can render first

## Query Selectors
* These select as type selector, class selectors, and id selectors
* use document.querySelector('varName'); to select a variable
* example:
`const h1 = document.querySelector('h1');`

* This can be used to select classes as well
* example:
`const circle = document.querySelector('.circle');` 

This creates variable called h1 and selects h1 from the dom and assigns it to it

## Selecting Things with .innerHTML, .innerText, and .textContent
### When to use .innerHTML
* This returns container elements like div, text elements, xml markup etc.
* Use this when you want to select everything. It will select & < and > as HTML entities &amp; &lt; and &gt; respectively

### When to use .innerText
* This will specifically return the text of a container. 
* retrieves text content as plain text instead of innerHTML retreiving content in HTML format

### When to use .textContent
* returns the content of all elements in the node including script and style elements. It is similar to .innerText but is not aware of the appearance of text.

## Selecting styling

### .getElementById()
* select an element based on its id name

### .getElementByClass()
* select an element by its Class

## Methods Functions Variables
`circle.classList.toggle('fancy');`
* classList is a property
* toggle is a function

### Methods
* A method is a function definition stored as a property value
* a js method is a propety containing a function definition

* Syntax
`objectName.methodName()`

### Functions
* Toggle is an example of a function
* 

## EventListeners
* attaches an event to an EventTarget. EventTarget's are elements, documents, and windows that you can attach events to.

### EventTarget()
* creates an EventTarget object
* doesn't seem to be needed so much
`const myEventTarget = new EventTarget();`

### addEventListener()
* add an event to the event target
`EventTarget.addEventListener(type, listener)`
* This is used a lot

### removeEventListener()
* remove a listener from a previously registered event. same syntax as addEventListener

## Event Types and Common Events
8 Types of events
[Javascript event types blog]https://data-flair.training/blogs/javascript-event-types/(

### User Interface events
Result of interaction with browser window **not with the HTML page**. Attach event listener to the window object instead of document object.
* load: load event starts when the page finishes loading. it can fire on nodes of elements like images, scripts, and objects
* unload: fires before users leave the page. For when a new page is requiested
* error: when browser encounters a JS error or when an asset doesnt exist
* resize: when browser window is being resized. Don't use this to trigger complicated code as you'll lose responsiveness
* scroll: event fires when user scrolls up and down the browser window.
- it can relate to the whole page or specific elements on the page

### Focus and Blur Events
Fire when html elements that the user interacts with gain or lose focus. 
useful for giving user feedback when they interact with an element. good for tips. good for triggering form validation
* focus: fires for a specific DOM node when the element **gains** focus
* blur: fires for a specific DOM node when element **looses** focus

### Mouse Events
When the mouse moves over or clicks an event. These actions respond differently for touch screen devices.
* click: user clicks or presses enter when element is focused. On touch screen, single tap is like a left click
* dblclick: double click. touch screen is a double tap
* 
