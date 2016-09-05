####01 Use `last-of-type` to set the last type of this element.

```css
	img: last-of-type{
		//use this tag to set the last type of this element
	}
```
####02 Use funtion `calc()`make sure there is a space between each pixel number. 

```css
	img{
		width: calc(100% - 20px); /* Will work!*/
		width: calc(100%-20px); /* Will not!*/
	}
```
####03 Use unit `vh` and `vw` to set length and width of elements into the scale of percentage of viewport

```css
	element{
		height: 100vh; /*100vh stands for 100% of the view-port height*/
		width: 100wh; /*100vw stands for 100% of the view-port width*/ 
	}
``` 

####04 Notes: setting both the height and the width to `100vmax` or `100vmin` changes the image's aspect ratio? It'll compress your images to squares, so be careful if you want to maintain a different aspect ratio!

####05 Notes: For-in loop 

```js
myObj = {'country1':'Germany', 'country2':'Argentina'};
for (key in myObj){
    if (myObj.hasOwnProperty(key)) {
        console.log(myObj[key]);
    }
}
```
####05 Load JQuery
```html
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
```  
####06 filter funtion
```js
$( "li" )
  .filter(function( index ) {
    return $( "strong", this ).length === 1;
  })
    .css( "background-color", "red" );\
```
This code will alter the first list item only, as it contains exactly one \<strong> tag. Within the filter function, this refers to each DOM element in turn. The parameter passed to the function tells us the index of that DOM element within the set matched by the jQuery object.

####07 addclass() functioon can change DOM elemmnets' class attribute
####08 togggleClass() add class tag when the DOM does not have that class tag. Otherwise remove it.
####09 attr() TWO ways to call it (similar with css() method)<li> .attr( attributeName, value ) <li> .attr( attributeName ) 
Notes: attr('style', 'prop:val') replaces the entire inline style. css()
just replaces that property.

####10 remove() call this.remove() removes this; call this.remove(".selecter") remove all the selecter tag witin this 

####11 modify the content of html
<li>.append()
<li>.prepend()
<li>.insertBefore()
<li>.insertAfter() (put selector in the back toooo wired....use after() instead)
####12 on() method to set up the event listener
```js
on("String",function(callback){});