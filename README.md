## It can be edited after double clicking the text
#### HTML code
```html
<div class="box">		
    <div class="d1" id = "con_father">
        <h2 id = "con">Default content</h2>
    </div>
</div>
```
#### JS code
```javascript
$(function(){
    $("#con").dblclick(function(){
        var fatherElement = document.getElementById("con_father");
	var h1Element = document.getElementById("con");
        var inputElement = document.createElement("input");
	
	inputElement.value = h1Element.innerHTML;
	fatherElement.replaceChild(inputElement, h1Element);
	inputElement.className = "d1";  //Keep the style unchanged after the replacement
	inputElement.focus();  //The input frame automatically gets the focus after the replacement
	
	inputElement.onblur = function(){
	    h1Element.innerHTML = inputElement.value;
	    fatherElement.replaceChild(h1Element, inputElement);
        }
    });    
})
