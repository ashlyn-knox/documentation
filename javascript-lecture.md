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
* syntax error: spelling errors in the code
* logic error: when your syntax is good but it's programmed to actually do something different from what you intended
* variable: a javascript value
* operator: symbol for performing operation, such as * + - = < >
* Operand: values that are acted upon
* primitive value types: undefined, null, boolean, string, number
* expression: a piece of code that does something
* 
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
**NOTE: Remember to use onclick when calling. like target.onclick**
When the mouse moves over or clicks an event. These actions respond differently for touch screen devices.
* click: user clicks or presses enter when element is focused. On touch screen, single tap is like a left click
* dblclick: double click. touch screen is a double tap
* mouseup: when user releases a mouse button. for touch screen use a touchend event
* [mousedown](https://developer.mozilla.org/en-US/docs/Web/API/Element/mousedown_event): when user clicks down on a mouse button
* mouseover: when user moves cursor over the element from outside the element boundary
* mouseout: when user moves cursor that was inside the element boundary to outside of it
* mousemove: fires when teh user moves the cursor around the element. triggers frequently.
* onclick: triggers on mouse click
* ondrag: triggers when element is dragged
* onfocus: triggers when a window gets focused


### Keyboard Events
* remember to use syntax like .onkeydown to call 
* [input](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event): fires when the value of an <input> or <textarea> changes. for older browsers, keydown works as a fallback
* keydown: fires when user presses a key, if the user holds a key down, it fires rapidly.
* keypress: fires when user presses a key taht results in printing a character on the screen.
* keyup: fires when user releases a key on the keyboard

### Form Events
These are useful when using forms on a webpage.
* submit: fires when the user submits a form
* change: fires when the status of form elements change. **better than using click event because clicking isn't the only way that a user interacts with the form**
* [input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Input): common with forms. focus and blur are sometimes used with forms in conjunction with elements like **links**

### HTML5 Events
* **TODO adjust this as I use different events**
Page Level events. **Useful to this course**
* [DOMContentLoaded](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event): Triggers when the Dom tree forms. attach to the window or document objects. **NOTE: Link provided is to document DOM content loaded, there is also documentation on** [Window: DOMContentLoaded](https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event)
* hashchange: fires when URL hash changes without refreshing the entire window. It works on teh window object and fires with **anchors** as they are hashes.
* beforeunload: fires on window object before the page unloads

### CSS Events
* **TODO Adjust this as I use different events**
Some Common css events are
* transitioned: when a css transition ends a program. notifies teh script of the end of transition.
* animationstart: fires when a css animation starts in the program
* animationiteration: occurs when an animation repeats
* animationend: occurs when an animation finished. Good for notifications to the user that need to happen in relation to a finished animation

### Mutation events and observers
**Not very relevant to the course at time of writing**
When the structure of the DOM tree changes, it triggers a mutation event. 
* DOMNodeInserted: when script inserts a new node in the DOM tree with: **appendChild()**, **replaceChild()**, **insertBefore()** etc.
* DomNodeRemoved: when a script removes an existing node
* DomSubtreeModified: when structure fo Dom tree changes

