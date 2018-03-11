jQuery Form Adjustment Toggle
=============================

A jQuery plugin that makes it easy to show or hide and disabled elements based on the state of a checkbox, radio button, or select menu.

You can also pass callbacks and custom attributes when you initialize the plugin.

Although basic functionality like this is easy to write, it can quickly get complex in certain situations. This plugin properly sets up the initial page state based on a form that has already been filled out. 

### [View Demo](http://developers.rohitiuc.info/fa-toggle)

Basic usage
-----------
__Note:__ These apply all elements inside targeting element.

1. Show/Hide
```html
<input type="radio" fa-toggle="#id" name="radio" value="radio1">
<input type="checkbox" fa-toggle="element" name="checkbox" value="checkbox1">
<select fa-toggle=".class" fa-select="option2">
	<option value="option1">option1</option>
	<option value="option2">option2</option>
	<option value="option3">option3</option>
</select>
```

2. Disabled
```html
<input type="radio" fa-toggle="#id" fa-disable="true" name="radio" value="radio1">
<input type="checkbox" fa-toggle="element" fa-disable="true" name="checkbox" value="checkbox1">
<select fa-toggle=".class" fa-disable="true" fa-select="option2">
	<option value="option1">option1</option>
	<option value="option2">option2</option>
	<option value="option3">option3</option>
</select>
```

3. Reverse
```html
<input type="radio" fa-toggle="#id" fa-reverse="true" name="radio" value="radio1">
<input type="checkbox" fa-toggle="element" fa-reverse="true" name="checkbox" value="checkbox1">
<select fa-toggle=".class" fa-reverse="true" fa-select="option2">
	<option value="option1">option1</option>
	<option value="option2">option2</option>
	<option value="option3">option3</option>
</select>
```

4. Show/Hide and Disabled element(All elements apply)

```javascript
$(document).ready(function() {
	/* Hide element */
	$('your-select').insideDisable();
	
	/* Show element */
	$('your-select').insideEnable();
});
```

5. Disabled element(All elements apply)

```javascript
$(document).ready(function() {
	/* Disabled element */
	$('your-select').insideDisable(1);
	
	/* Disabled false element */
	$('your-select').insideEnable(1);
});
```

Form Toggle uses HTML data attributes to drive the configuration of the forms. There are two ways to define the elements you are targeting to show or hide and disabled true and false.

1. Any element can use its value attribute to help determine what elements you are targeting. To do this, you must define the fa-toggle to use with the value to create a jQuery selector.

2. In case of select Checkboxes and radio buttons can also simply use explicit jQuery selectors to define what elements they are targeting. Use `fa-toggle="your-selector(eg. #id, .class)"` to do this, is checked `your-selector` show and no-checked your-selector hide. Use disabled element `fa-disable="true"`is checked `your-selector` disabled false and `no-checked` `your-selector` disabled true these apply all element inside `your-selector`.

3. In case of select same as Checkboxes and radio buttons but these case not checked. So use attribute `fa-select` only for select. Use `fa-select="value of select"`.

4. These process in reverse order use attribute `fa-reverse` only for reverse toggling. Use `fa-reverse="true"`.

5. Other use for any form element pass callbacks for show/hide or disabled element.

 
Options
-------

There are a few ways in which you can configure faToggle. You can define a custom prefix for data attributes to add another instance of formToggle that is configured differently:

This will use the data attribute name `fa-toggle`, `fa-disable`, `fa-select`(In case of select) and the effect will be reversed `fa-reverse`.

This will pass callbacks insideDisable and insideEnable. 
