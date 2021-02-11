# Svg in HTML
* Svg importing (3 ways)
* svg editing

## viewbox and svg anatomy
* If you need to edit the viewbox, then edit the svg in vector editor

### Importing
1. As an html image`
`img src=../images/circle.svg alt="svg"
* can be sized and edited the way you would any img. but it will always be sharp and not distor.
* generally add display block to this
2. As a css image
* create as a background image in css
* stylize with css
3. as an inline svg
* Allows styling attributes
* properties change when you use it this way

* Note: There are no stroke shorthand properties for svgs

* anything made in svgs can be overridden with css. It's normal to create styling attributes with attributes.
* They can be removed and added back with css in inline svg

* NOTE: take away width and height attributes from svg to make them responsive

* NOTE: If your having trouble with the viewbox, export the frame instead of the object

## Editing Svg files with svgomg
*  select remove width and height to make svg responsive
* don't remove xmlns
* the percision can be cut down a bit to reduce the filesize
*

