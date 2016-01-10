# jquery.pinBox
Pin any element within a container . for examples go to http://nezamy.com/pinBox.

# Usage

## 1. Load jQuery and include pinBox plugin file
To use pinBox, you’ll need to make sure both the pinBox and jQuery 1.7 or higher scripts are included.
```html
  <!--  jQuery  -->
  <script src="jquery-1.9.1.min.js"></script>
  <!--  Include pinBox plugin  -->
  <script src="js/jquery.pinBox.min.js"></script>
```

## 2. Set up your HTML
You don't need any special markup. All you need is to wrap your divs inside the container for example #pinBoxContainer and add class to your div for example .pinBox . read the code comments.
```html
<!-- container with id -->
<div class="container" id="pinBoxContainer">
<!-- if you don't use bootstrap.css make sure to add [position:relative] if div parent have float property.  -->
	<div class="col-sm-4">
	<!-- box you want to pin inside [id="pinBoxContainer"] have class or id -->
		<div class="pinBox">
			<h2 class="headColor">Example box</h2>
			<p>some text</p>
		</div>
	</div>
	
	<div class="col-sm-8">
		<h2 class="headColor">Example box</h2>
		<p>some text</p>
	</div>
</div>
```

## 3. Call the plugin
To make a pinned element stay within an outer container, use the Container option
```js
$(document).ready(function() {
 
	$(".pinBox").pinBox({
		Top : '50px',
		Container : '#pinBoxContainer',
	});
 
});
```

## Call the plugin with options
```js
$(document).ready(function() {
 
	$(".pinBox").pinBox({
		//default 0px
		Top : '50px',
		//default '.container' 
		Container : '#pinBoxContainer',
		//default 20 
		ZIndex : 20,
		//default '767px' if you disable pinBox in mobile or tablet
		MinWidth : '767px',
		//events if scrolled or window resized  
		Events : function(e){
			console.log(e);
			// e.current => current scroll top [number]
			// e.direction => scroll down or up [up,down]
			// e.width => window width [number]
			// e.active => if pinBox active [true,false]
			// e.disabled => if window width < MinWidth pinBox will disabled [true, false]
		}
	});
 
});
```

## Examples

examples [Here](http://nezamy.com/pinBox/).

## The MIT License (MIT)

Copyright (c) 2016 Mahmoud Elnezamy

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
