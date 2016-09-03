###2016/08/29 
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
###2016/09/01
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
