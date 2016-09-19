#Front-End-Notes
<hr>
####01 Use `last-of-type` to set the last type of this element.

```css
	img: last-of-type{
		//use this tag to set the last type of this element
	}
```
--
####02 Use funtion `calc()`make sure there is a space between each pixel number. 

```css
	img{
		width: calc(100% - 20px); /* Will work!*/
		width: calc(100%-20px); /* Will not!*/
	}
```
--
####03 Use unit `vh` and `vw` to set length and width of elements into the scale of percentage of viewport

```css
	element{
		height: 100vh; /*100vh stands for 100% of the view-port height*/
		width: 100wh; /*100vw stands for 100% of the view-port width*/ 
	}
``` 
--
####04 Notes: setting both the height and the width to `100vmax` or `100vmin` changes the image's aspect ratio? It'll compress your images to squares, so be careful if you want to maintain a different aspect ratio!
--
####05 Notes: For-in loop 

```js
myObj = {'country1':'Germany', 'country2':'Argentina'};
for (key in myObj){
    if (myObj.hasOwnProperty(key)) {
        console.log(myObj[key]);
    }
}
```
--
####05 Load JQuery
```html
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
```  
--
####06 filter funtion
```js
$( "li" )
  .filter(function( index ) {
    return $( "strong", this ).length === 1;
  })
    .css( "background-color", "red" );\
```
This code will alter the first list item only, as it contains exactly one \<strong> tag. Within the filter function, this refers to each DOM element in turn. The parameter passed to the function tells us the index of that DOM element within the set matched by the jQuery object.

--
####07 addclass() functioon can change DOM elemmnets' class attribute
--
####08 togggleClass() add class tag when the DOM does not have that class tag. Otherwise remove it.
--
####09 attr() TWO ways to call it (similar with css() method)<li> .attr( attributeName, value ) <li> .attr( attributeName ) 
Notes: attr('style', 'prop:val') replaces the entire inline style. css()
just replaces that property.

--
####10 remove() call this.remove() removes this; call this.remove(".selecter") remove all the selecter tag witin this 
--
####11 modify the content of html
<li>.append()
<li>.prepend()
<li>.insertBefore()
<li>.insertAfter() (put selector in the back toooo wired....use after() instead)

--
####12 on() method to set up the event listener
```js
on("String",function(callback){});
```
--
####13 event
<li>event.keyCode to learn what key was pressed - invaluable if you need to listen for a specific key
<li>event.pageX and event.pageY to know where on the page the click occurred - helpful for analytics tracking
<li>event.type to find what event happened - useful if listening to a target for multiple events
<li>event.target

--
####14 .keypress() is the shortcut for on("target",callback)
<li>keyup
	<li>mouseover
	<li>change
	<li>click
	<li>hover is special it is a chortcut for
	
```js
	$( selector ).mouseenter( handlerIn ).mouseleave( handlerOut );
```
--
####15 foreign language display 
```html
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
```
--
####16 google map image API
```js
$body.append('<img class="bgimg" src="http://maps.googleapis.com/maps/api/streetview?size=600x300&location='+$st.val()+', '+$city.val()+'">');
```
--
####17 New york times article API 
```js
$.getJSON("https://api.nytimes.com/svc/search/v2/articlesearch.json?q='"+$city.val()+"'&sort=newest&api-key=ec3224643f234d9984ac5d32ba2c0399", function(data){
    // console.log("https://api.nytimesssss.com/svc/search/v2/articlesearch.json?q="+$city.val()+"&api-key=ec3224643f234d9984ac5d32ba2c0399");
        var article = data.response.docs;
        // console.log(article);
        article.forEach(function(entry){
            $nyList.append('<li class = "article">'+
                '<a href = "'+ entry.web_url+'">'+entry.headline.main+'</a>'+
                '<p>'+ entry.lead_paragraph+'</p></li>');
        });
    }).fail(function(e){
        $nytHeaderElem.text("BAD request for New York times articles");
    }
    );
```
--
####18 use `jason p` when cross source API (JSONP shells the response in a function)
--
####19 jasonp does not support error handlind so use a time-out function to shoot the failure 
```js
setTimeout(function(){}, 8000/*time*/)
```
and then add 

```js
clearTimeout(function);
```
function to stop the timeout in your code 
######OR 
use this chained function to handle the error 

```js
$.ajax({
   //stuff
}).done(function(){
   //do math
});
```
--
####20 200 means OK
--
####21 defining function to make the iterator i a local variable insode the each iteration closure instide a global variable Use `let `
```js
var cats = [{"name":"Tom"},{"name":"Lorry"}];

var click = [];


for(let i = 1; i<= cats.length;i++){
    $("#name"+i).text(cats[i-1].name);
    click.push(0);
    $("#cat"+i).click(function(){
        console.log(i);
        click[i-1]++;
        $("#counts"+i).text("You clicked cat for "+ click[i-1] + " times");});
}
```
--
####22 use scope to capture iterating variables
The num variable changes, so we have to somehow connect it to our event listener function. Here's one way of doing it. First take a look at this code, then I'll explain how it works.

```js

elem.addEventListener('click', (function(numCopy) {
    return function() {
        alert(numCopy)
    };
})(num));
```
The bolded part is the outer function. We immediately invoke it by wrapping it in parentheses and calling it right away, passing in num. This method of wrapping an anonymous function in parentheses and calling it right away is called an IIFE (Immediately-Invoked Function Expression, pronounced like "iffy"). This is where the "magical" part happens.

We're passing the value of num into our outer function. Inside that outer function, the value is known as numCopy -- aptly named, since it's a copy of num in that instant. Now it doesn't matter that num changes later down the line. We stored the value of num in numCopy inside our outer function.

--
####23 JQuery function `hide()` and `show()` to set display to none ; to display;
--
####24 MVC (model view controlor) MVP (model view presenter)
model: capture the data 
view: user interface

--
####25 Basic knowledge of JQuery

```js 
$(function(){...})
``` 
is a shortcut for

```js
$(document).ready(function(){...});
```