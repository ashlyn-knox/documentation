# Checkbox Hack

Hack your css for fabulous functionality

---

## Method 1

### HTML | Setup items

1. Code hierarchy
   
   - `<div class="wrapper"></div>`
     
     - `<input type="checkbox" id="selectMe">`
     
     - `<label for="selectMe">put your icon here</label>`
     
     - `<div class="content-container">put stuff here</div>`

### CSS | Manipulate display

2. Hide stuff Display method -- You can use visibility: hidden/visible if you don't want the wrapper space to adjust.
   
   * `.content-container: { display: none; }` -- Make items invisible
   
   * `.wrapper input:checked { display: none;}` -- make the checkbox invisible

3. Make it work
   
   * `.selectMe:checked ~ * ~ .content-container { display: block; }` -- display anything but none is fine
   
* **Not necessary Step** | customize unchecking interaction
   - `.wrapper input:not(:checked) ~ * ~ .content-container {}` 
   
#### Styling
   
   * Style the label when checked -- `.wrapper input:checked ~ label {}`
   
   * Style `.wrapper` for general position and layout
   
   * Style `.content-container` for your content
   
   * **IMPORTANT** If you want to add animations, make sure you  use the :checked class declarations.

--- 

## Method 2 | Animations!

This method is sneaky. Essentially you are just making a big invisible checkbox and placing it over your icon. The icon is never actually clicked - that's the trick.

* **Why would you do this?**
  
  * To give the icon animation like turning a hamburger into a X

### HTML Setup

Code hierarchy

- `<div class="wrapper"></div>`
  
  - `<input type="checkbox" id="selectMe">`
  
  - `<span></span><span></span>` -- To make a 2 row hamburger
  
  - `<div class="content-container">put stuff here</div>`


### CSS Setup

Very similar to the first method. but stylizing and positioning the checkboxes is essential.

1. Layout and Layer of Elements
   
   * `.wrapper {z-index: 1}` 
   
   * `.wrapper input {position: absolute; opacity: 0; cursor:pointer; z-index:10; width; height;}`
     
     * **IMPORTANT**: width and height need to overlap with your clickable element. 
     
     * z-index just needs to be higher than anything else.
     
     * set the opacity to 0 **after** aligning under the icon.
   
   * `.wrapper span {position: relative; z-index:1; width; height; background-color;}`
     
     * you will need to manually set the checkbox and icon location so they overlap.
   
   * `content-container {margin, opacity, padding}`
     
     * Specify start margin if you want to slide off screen or something.

2. Hoverable Icon
   
   * `.wrapper input:hover ~ span {animation-name:input-hover; animation-duration; animation-fill-mode-forwards;}`
   
   * `@keyframes input-hover {100% {opacity: 0.6;}}`

### CSS Functionality

1. Make it work
   
   * `.wrapper input:checked ~ .content-container {animations}` -- Set how things will animate when you check the checkbox
   
   * `.wrapper input:not(:checked) ~.content-container {animations}` -- Set how things will animate when you uncheck the checkbox

2. Make your span icon do stuff
   
   * `.wrapper input:checked ~ span {transform; opacity; etc}` -- This selects the first span
   
   * `.wrapper input:checked ~ span:nth-child(2) {transform; opacity; etc}` -- This selects the second span

### Why do this method?
This method gives you greater control. Erik Terwan's example in the attributions below shows how to use transitions and margins effectively to achieve a smooth interaction. However for a lot of stuff the 1st method will get the job done just fine.

---

## Attributions

* [CSS Tricks Article](https://css-tricks.com/the-checkbox-hack/)

* [Erik Terwan Codepen](https://codepen.io/erikterwan/pen/EVzeRP)

## Extra Reading
* [MDN Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [MDN Transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [MDN Keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
